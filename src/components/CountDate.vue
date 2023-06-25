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

        <!-- DAYS -->
        <div class="container">
            <h3 class="day">{{ day }}</h3>
            <p>DAYS</p>
        </div>

        <!-- HOUR -->
        <div class="container">
            <h3 class="hour">{{ hour }}</h3>
            <p>HOURS</p>
        </div>
        <!-- MINUTE -->
        <div class="container">
            <h3 class="minute">{{ minute }}</h3>
            <p>MINUTES</p>
        </div>
        <!-- SECOND -->
        <div class="container">
            <h3 class="second">{{ second }}</h3>
            <p>SECONDS</p>
        </div>
    </section>
</template>

<style lang="scss" scoped>
    @use '../assets/scss/utilities/' as *;
    
    .count-down {
        text-align: center;
        display: flex;
        align-items: center;
        justify-content: center;
        gap: rem(18);
    }
    
    .container {
        height: clampf(100, 800, 125);
        width: clampf(75, 800, 100);
        
        h3 {
            color: var(--clr-primary-soft-red);
            font-size: clampf(16, 800, 64);
            background-color: var(--clr-neutral-dark-blue);
            border-radius: .1em;
            margin-bottom: rem(16);
        }

        p {
            color: var(--clr-neutral-white);
            letter-spacing: 2px;
            font-size: rem(12);
        }
    }
</style>