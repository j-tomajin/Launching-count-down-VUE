<script>
  import HeaderContent from './components/HeaderContent.vue';
  import CountDate from './components/CountDate.vue';
  import FooterContent from './components/FooterContent.vue';

  export default {
    name: 'App',
    components: {
      HeaderContent,
      CountDate,
      FooterContent,
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

        let interval = setInterval(() => {
          this.countDown()

          if(gap === 0) {
            clearInterval(interval)
          }
        }, 1000);

        if(gap === 0) {
          alert("WE'RE OPEN!")
        }
      }
    },
  }
</script>

<template>
  
  <HeaderContent
    class="header"
    text="WE'RE LAUNCHING SOON!"
  />
  <main>
    <CountDate
      :day="day"
      :hour="hour"
      :minute="minute"
      :second="second"
      @count-down="countDown"
    />
  </main>
  
  <FooterContent />
</template>

<style lang="scss" scoped>
  @use './assets/scss/utilities/' as *;

  .header {
    color: var(--clr-neutral-white);
    margin-block: clampf(75, 800, 100)
  }
</style>