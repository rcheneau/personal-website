<template>
    <div id="home">
        <div>
            <h1>Raphaël Cheneau</h1>
            <p>Développeur web</p>
        </div>
        <div></div>
    </div>
</template>

<script>
    export default {
        name: 'Home',
        props: {}
    }
</script>

<style scoped lang="scss">
    @import "../assets/breakpoints";

    #home {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;

        @include sm {
            align-items: center;
            justify-content: flex-start;
        }


    }
</style>
