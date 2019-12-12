<template>
    <div id="work">

        <div class="row">
            <div class="col"><h1>Mon parcours</h1></div>
            <div class="col"></div>
            <div class="col download"><a href="#" class="btn">Télécharger le CV</a></div>
        </div>

        <section>
            <ul>
                <li v-bind:key="e.id"
                    v-for="e in $options.experiences"
                    v-bind:data-date-from="e.from"
                    v-bind:data-date-to="e.to"
                >
                    <h3>{{e.title}}</h3>
                    <p v-html="e.description"/>
                </li>
            </ul>
        </section>
    </div>
</template>

<script>
    import json from '../data/work';
    export default {
        experiences: json,
    }
</script>

<style scoped lang="scss">
    @import '../assets/breakpoints';

    $color-primary: #7474BF;
    $color-secondary: #181834;

    $spacing-xs: 10px;
    $spacing: 20px;
    $date: 120px;
    $dotborder: 4px;
    $dot: 11px;
    $line: 4px;

    p {
        color: #aaa;
        font-size: 1em;
    }

    .keyword {
        font-weight: bold;
    }

    h1 {
        white-space: nowrap;

        &::before {
            content: '';
            display: block;
            height: 0;
            width: 0;
            margin-top: -12px;
        }
    }


    .download {
        white-space: nowrap;

        .btn {
            color: #7474BF !important;
            text-transform: uppercase;
            text-decoration: none;
            background: #ffffff;
            padding: 10px;
            font-size: 0.8em;
            border: 4px solid #7474BF !important;
            transition: all 0.4s ease 0s;
            text-align: center;

            &:hover {
                color: #ffffff !important;
                background: #7474BF;
                border-color: #7474BF !important;
                transition: all 0.4s ease 0s;
            }
        }
    }

    section {
        padding-left: 50px;
        margin-top: 30px;

        @include sm {
            padding-left: 100px;
        }

        @include md {
            margin-top: 0;
            padding-left: 120px;
        }
    }

    ul {
        border-left: 4px solid $color-primary;
        border-top-right-radius: 5px;
        border-bottom-right-radius: 5px;
        position: relative;
        padding: $spacing-xs;
        margin: $spacing-xs auto;
        background-color: #f1f1f8;

        @include md {
            padding: $spacing;
            margin: $spacing auto;
        }

        li {
            border-bottom: 1px dashed $color-secondary;
            padding-bottom: ($spacing-xs * 0.5);
            margin-bottom: $spacing-xs;
            position: relative;
            list-style: none;

            @include md {
                padding-bottom: ($spacing * 0.5);
                margin-bottom: $spacing;
            }

            &::before, &::after {
                position: absolute;
                display: block;
                top: 0;
            }

            &::before {
                left: ((($date * 0.6) + $spacing-xs + $line + $dot + ($dotborder * 2)) * 1.5) * -1;
                content: attr(data-date-from) '\A-   \A' attr(data-date-to);
                color: #7474bf;
                text-align: right;
                font-weight: 100;
                font-size: 0.9em;
                width: $date;
                white-space: pre;

                @include sm {
                    content: attr(data-date-from) ' - ' attr(data-date-to);
                }

                @include md {
                    left: ((($date * 0.6) + $spacing + $line + $dot + ($dotborder * 2)) * 1.5) * -1;
                }
            }

            &::after {
                box-shadow: 0 0 0 $dotborder $color-primary;
                left: ($spacing-xs + $line + ($dot * 0.35)) * -1;
                background: lighten($color-secondary, 5%);
                border-radius: 50%;
                height: $dot;
                width: $dot;
                content: "";
                top: 5px;

                @include md {
                    left: ($spacing + $line + ($dot * 0.35)) * -1;
                }
            }

            &:last-of-type {
                padding-bottom: 0;
                margin-bottom: 0;
                border: none;
            }
        }
    }

</style>