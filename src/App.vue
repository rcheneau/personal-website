<template>
    <div id="app">
        <div id="main">
            <Navigation></Navigation>
            <div class="panel">
                <TransitionExpand>
                    <router-view></router-view>
                </TransitionExpand>
            </div>
            <div id="copyright">
                <ul>
                    <li>© Untitled.</li>
                    <li>Design: <a href="http://html5up.net" target="_blank">HTML5 UP</a></li>
                </ul>
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
        color: #454545;
        font-size: 3em;
        margin-top: 0;
        text-align: center;

        @include md {
            text-align: left;
        }
    }

    h2 {
        font-weight: 200;
        color: #737373;
        font-size: 2em;
        text-align: center;

        @include md {
            text-align: left;
        }
    }

    a {
        color: #0077aa;
    }

    .row {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        width: 100%;
    }

    .col {
        display: flex;
        flex-direction: column;
        flex-basis: 100%;

        @include md {
            flex: 1;
        }
    }

    #app {
        display: flex;
        justify-content: center;
        align-items: center;
        background: linear-gradient(to right, #348AC7, #7474BF);
    }

    #main {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        width: 95%;
        margin-top: 2.25em;
        margin-bottom: 2.25em;

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

     #copyright {
         padding: 1em 0 0 0;
         color: rgba(255, 255, 255, 0.45);
         font-size: 0.8em;

         ul {
             list-style: none;
             padding-left: 0;

             li {
                 display: inline-block;
                 padding-left: 1em;
                 margin-left: 1em;
                 border-left: solid 1px
                 rgba(255, 255, 255, 0.25);
                 line-height: 1;

                 a {
                     color: rgba(255, 255, 255, 0.45);
                 }

                 &:first-child {
                     padding-left: 0;
                     margin-left: 0;
                     border-left: 0;
                 }
             }
         }
     }
</style>
