<template>
  <div>
    <h1>{{ message }}</h1>
    <h2>{{ display }}</h2>
  </div>
</template>
<script>
  import moment from 'moment'

  export default {
    props: {
      message: {
        type: String,
        default: 'Hello!',
      },
    },
    data () {
      return {
        time: Date.now(),
      }
    },
    computed: {
      display () {
        return moment(this.time).format('HH:mm:ss')
      },
    },
    created () {
      setInterval(() => {
        this.time = Date.now()
      }, 1000)
    },
  }
</script>
