<template>
  <div class="form-horizontal">

    <div class="form-group">
      <div class="col-sm-6">
        <label>Date</label>
        <input
          type="date"
          class="form-control"
          v-model="timeEntry.date"
          placeholder="Date">
      </div>

      <div class="col-sm-6">
        <label>Hours</label>
        <input
          type="number"
          class="form-control"
          v-model="timeEntry.totalTime"
          placeholder="Hours">
      </div>
    </div>

    <div class="form-group">
      <div class="col-sm-12">
        <label>Comment</label>
        <input
          type="text"
          class="form-control"
          v-model="timeEntry.comment"
          placeholder="Comment">
      </div>
    </div>

    <button class="btn btn-primary" @click="save()">Save</button>
    <button v-link="'/time-entries'" class="btn btn-danger">Cancel</button>
    <hr>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        timeEntry: {
          user: {
            firstName: 'Doğan',
            lastName: 'Öztürk',
            email: 'doganozturk2005@gmail.com',
            image: 'https://en.gravatar.com/userimage/82252212/688187d4e45e9c0e9041e420ddd6b017.jpeg',
          },
        },
      };
    },
    methods: {
      save() {
        const timeEntry = this.timeEntry;
        this.$dispatch('timeUpdate', timeEntry);
        this.timeEntry = {};
      },
    },
  };
</script>
