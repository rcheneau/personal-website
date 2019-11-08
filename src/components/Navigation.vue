<template>
    <nav id="nav">
        <router-link to="/">
            <font-awesome-icon icon="home"/>
            <span>Home</span>
        </router-link>
        <router-link to="/work">
            <font-awesome-icon icon="folder"/>
            <span>Work</span>
        </router-link>
        <router-link to="/contact">
            <font-awesome-icon icon="envelope"/>
            <span>Contact</span>
        </router-link>
        <a href="https://github.com/rcheneau" target="_blank">
            <font-awesome-icon v-bind:icon="['fab', 'github']" />
            <span>Github</span>
        </a>
    </nav>
</template>

<script>
    export default {
        name: "Navigation"
    }
</script>

<style scoped lang="scss">
    #nav {
        text-align: center;
        height: 4.25em;
        cursor: default;

        a {
            position: relative;
            display: inline-block;
            color: #ffffff;
            width: 1em;
            height: 1em;
            line-height: 0.9em;
            font-size: 2.5em;
            margin: 0 0.25em 0 0.25em;
            opacity: 0.35;
            outline: 0;

            &.icon:before {
                padding-right: 0;
            }

            &:before {
                font-size: 0.8em;
            }

            &:after {
                content: '';
                display: block;
                position: absolute;
                left: 50%;
                bottom: -0.75em;
                margin-left: -0.5em;
                border-bottom: solid 0em #ffffff;
                border-left: solid 0.5em transparent;
                border-right: solid 0.5em transparent;
            }

            span {
                display: block;
                position: absolute;
                background: #222222;
                color: #ffffff;
                top: -2.75em;
                font-size: 0.3em;
                height: 2.25em;
                line-height: 2.25em;
                left: 50%;
                opacity: 0;

                width: 5.5em;
                margin-left: -2.75em;

                &:after {
                    content: '';
                    display: block;
                    position: absolute;
                    bottom: -0.4em;
                    left: 50%;
                    margin-left: -0.6em;
                    border-top: solid 0.6em #222222;
                    border-left: solid 0.6em transparent;
                    border-right: solid 0.6em transparent;
                }
            }

            &:hover {
                opacity: 1.0;

                span {
                    opacity: 1.0;
                }
            }

            &.active {
                opacity: 1.0;

                &:after {
                    border-bottom-width: 0.5em;
                }
            }
        }


    }
</style>