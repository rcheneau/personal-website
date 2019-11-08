<template>
    <div id="app">
        <div id="main">
            <Navigation></Navigation>
            <div class="panel">
                <TransitionExpand>
                    <router-view></router-view>
                </TransitionExpand>
            </div>
        </div>
    </div>
</template>

<script>
    import Navigation from "./components/Navigation";
    import TransitionExpand from "./components/TransitionExpand";

    export default {
        name: 'app',
        components: {Navigation, TransitionExpand},
    };


</script>

<style lang="scss">
    @import "assets/breakpoints";

    html, body, #app {
        margin: 0;
        min-height: 100vh;
        font-family: 'Roboto Light', Helvetica, Arial, sans-serif;
    }

    h1 {
        font-weight: 400;
        color: #363636;
        font-size: 2em;

        @include sm {
            font-size: 3em;
        }
    }

    p {
        color: #aaa;
        font-size: 1em;

        @include sm {
            font-size: 1.5em;
        }
    }

    #app {
        display: flex;
        justify-content: center;
        align-items: center;
        background: rgb(116, 116, 191);
        background: linear-gradient(180deg, rgba(116, 116, 191, 1) 0%, rgba(52, 138, 199, 1) 100%);
    }

    #main {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        width: 95%;

        @include md {
            width: 80%;
        }

        @include lg {
            width: 60%;
        }

        @include xl {
            width: 50%;
        }
    }

    .panel {
        background-color: white;
        margin-bottom: 0;
        width: 100%;
        transition: opacity 0.25s ease-in-out;
        padding: 2.5em 1.5em 1.5em 1.5em;

        @include sm {
            padding: 3.5em 2.5em 2.5em 2.5em;
        }

        &.inactive {
            opacity: 0;
        }
    }
</style>
