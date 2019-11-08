<template>
    <div id="work">
        <h1>CV</h1>


        <section>
            <ul>
                <li data-date="2018 - 2019">
                    <h3>Sipartech</h3>
                    <p>
                        Développeur PHP / Symphony 4
                    </p>
                </li>
                <li data-date="2017 - 2018">
                    <h3>Imadiff</h3>
                    <p>
                        Développeur web
                    </p>
                </li>
                <li data-date="2015 - 2017">
                    <h3>Master logiciel UPEM</h3>
                    <p>
                        Master logiciel à l'Université Paris-Est Marne-la-Vallée en alternance à 3Ci Solutions
                    </p>
                </li>
                <li data-date="2012 - 2015">
                    <h3>License Maths/Informatique UPEM</h3>
                    <p>
                        License Mathématiques et Informatique à l'Université Paris-Est Marne-la-Vallée
                    </p>
                </li>
            </ul>
        </section>
    </div>
</template>


<style scoped lang="scss">
    @import '../assets/breakpoints';

    $color-primary: #7474BF;
    $color-secondary: #348AC7;

    $spacing-xs: 20px;
    $spacing: 40px;
    $date: 120px;
    $dotborder: 4px;
    $dot: 11px;
    $line: 4px;

    section {
        padding-left: 100px;
        @include sm {
            padding-left: 120px;
        }
    }

    ul {
        border-left: 4px solid $color-primary;
        position: relative;
        padding: $spacing-xs;
        margin: $spacing-xs auto;

        @include sm {
            padding: $spacing;
            margin: $spacing auto;
        }

        li {
            border-bottom: 1px dashed $color-secondary;
            padding-bottom: ($spacing-xs * 0.5);
            margin-bottom: $spacing-xs;
            position: relative;
            list-style: none;

            @include sm {
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
                content: attr(data-date);
                color: grey;
                text-align: right;
                font-weight: 100;
                font-size: 0.9em;
                min-width: $date;

                @include sm {
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

                @include sm {
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