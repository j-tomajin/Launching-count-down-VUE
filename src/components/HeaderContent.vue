<script>
    export default {
        name: 'HeaderContent',
        props: {
            text: {
                type: String,
                default: 'This is header',
            },
        }
    }
</script>

<template>
    <header>
        <h1 class="header">{{ text }}</h1>
    </header>
</template>

<style lang="scss" scoped>
    @use '../assets/scss/utilities/' as *;

    .header {
        text-align: center;
    }
</style>