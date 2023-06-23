<script>
    export default {
        name: 'CountDate',
        props: {
            day: Number,
            hour: Number,
            minute: Number,
            second: Number,
        },
        mounted() {
            this.$emit('count-down')
        },
    }
</script>

<template>
    <section class="count-down">
        <!-- DAY -->
        <div class="container-day">
            <h3 class="day">{{ day }}</h3>
            <p>Day</p>
        </div>
        <!-- HOUR -->
        <div class="container-hour">
            <h3 class="hour">{{ hour }}</h3>
            <p>Hour</p>
        </div>
        <!-- MINUTE -->
        <div class="container-minute">
            <h3 class="minute">{{ minute }}</h3>
            <p>Minute</p>
        </div>
        <!-- SECOND -->
        <div class="container-second">
            <h3 class="second">{{ second }}</h3>
            <p>second</p>
        </div>
    </section>
</template>

<style lang="scss" scoped>
    @use '../assets/scss/utilities/' as *;
    
    .count-down {
        text-align: center;
        display: flex;
        justify-content: space-around;
    }

    h3 {
        color: var(--clr-primary-soft-red);
    }

    p {
        color: var(--clr-neutral-white);
    }
</style>