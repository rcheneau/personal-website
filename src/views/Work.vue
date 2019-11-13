<template>
    <div id="work">

        <div class="header">
            <div class="title"><h1>Mon parcours</h1></div>
            <div class="download"><a href="#" class="btn">Télécharger le CV</a></div>
        </div>

        <section>
            <ul>
                <li data-date="2018 - 2019">
                    <h3>Sipartech</h3>
                    <p>
                        Développement et maintenance de l'ERP interne de la société,
                        <span class="keyword">PHP 7.3</span>
                        / <span class="keyword">Symfony 4</span>
                        / <span class="keyword">MySQL</span>
                        / <span class="keyword">PostgreSQL</span>.
                        <br>Développement d'extensions QGIS en <span class="keyword">python</span>.
                    </p>
                </li>
                <li data-date="2017 - 2018">
                    <h3>Imadiff</h3>
                    <p>
                        Mise en place de solutions WEB pour des clients externes en <span class="keyword">PHP</span>
                        / <span class="keyword">Drupal 7&8</span>
                        / <span class="keyword">MySQL</span>
                        / <span class="keyword">API REST</span>.
                        <br>Développement d'application desktop personalisées sous  <span class="keyword">FileMaker</span>.
                    </p>
                </li>
                <li data-date="2015 - 2017">
                    <h3>Master logiciel UPEM et alternance chez 3Ci Solutions</h3>
                    <p>
                        Alternance visant à développer un portail de collecte, d'analyse et de visualisation de données
                        d'encaissement via  / <span class="keyword">CodeIgniter</span>
                        / <span class="keyword">MySQL</span>
                        / <span class="keyword">Azure DocumentDB</span>
                        / <span class="keyword">MondoDB</span>
                        / <span class="keyword">D3.js</span>.
                    </p>
                </li>
                <li data-date="2012 - 2015">
                    <h3>License Maths / Informatique UPEM</h3>
                    <p>
                        License Mathématiques et Informatique à l'Université Paris-Est Marne-la-Vallée.
                    </p>
                </li>
            </ul>
        </section>
    </div>
</template>


<style scoped lang="scss">
    @import '../assets/breakpoints';

    @mixin lhCrop($line-height) {
        &::before {
            content: '';
            display: block;
            height: 0;
            width: 0;
            margin-top: calc((1 - #{$line-height}) * 0.5em);
        }
    }

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

    .header {
        display: flex;

        h1 {
            @include lhCrop(1.2);
        }

        .download {
            flex-grow: 1;
            text-align: right;

            .btn {
                color: #7474BF !important;
                text-transform: uppercase;
                text-decoration: none;
                background: #ffffff;
                padding: 10px;
                font-size: 0.8em;
                border: 4px solid #7474BF !important;
                display: inline-block;
                transition: all 0.4s ease 0s;

                &:hover {
                    color: #ffffff !important;
                    background: #7474BF;
                    border-color: #7474BF !important;
                    transition: all 0.4s ease 0s;
                }
            }
        }
    }

    section {
        padding-left: 100px;
        @include sm {
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
                color: #7474bf;
                text-align: right;
                font-weight: 100;
                font-size: 0.9em;
                width: $date;

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