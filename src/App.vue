<script>
  import Header from './components/Header.vue';
  import CountDate from './components/CountDate.vue';
  import Footer from './components/Footer.vue';

  export default {
    name: 'App',
    components: {
      Header,
      CountDate,
      Footer,
    },
    data: function() {
      return {
        day: 0,
        hour: 0,
        minute: 0,
        second: 0,
      }
    },
    methods: {
      countDown() {
        const countDate = new Date('August 18, 2023 00:00:00').getTime()
        const date = new Date().getTime()
        const gap = countDate - date

        const second = 1000
        const minute = second * 60
        const hour = minute * 60
        const day = hour * 24
      
        this.day = Math.floor(gap / day)
        this.hour = Math.floor((gap % day) / hour)
        this.minute = Math.floor((gap % hour) / minute)
        this.second = Math.floor((gap % minute) / second)

        setInterval(() => {
          this.countDown()
        }, 1000);
      }
    },
  }
</script>

<template>
  <Header
    class="header"
    text="WE'RE LAUNCHING SOON!"
  />
  <CountDate
    :day="day"
    :hour="hour"
    :minute="minute"
    :second="second"
    @count-down="countDown"
  />
  <Footer />
</template>

<style lang="scss" scoped>
  @use './assets/scss/utilities/' as *;

  .header {
    color: var(--clr-neutral-white);
  }
</style>