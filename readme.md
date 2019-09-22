# Building Skeleton of a Modern Single Page Application (SPA)
## What you will Learn 
- CSS
- Flex
- Grid
- CSS Transitions
- CSS Animations
- Responsiveness using Media Query

## How It Looks Like?

<img src="https://i.imgur.com/8ruoUtv.png" alt="drawing" width="400"/>
<img src="https://i.imgur.com/0NNogq2.png" alt="drawing" width="400"/>

## Tutorial
- Give BACKGROUND-COLOR to ALL BOXES
    <details><summary>How?</summary>
    <p>

    ```scss
     body {
         background-color: aqua;
         font-family: "Open Sans Condensed"; //better font
     }
     .container {
         // Any child element of div.cotainer will have a different background, and also have margin-bottom so that we can see the area taken by each box
        * {
            background-color: rgb(18, 22, 87);
            color: white;
            margin-bottom: 10px;
        }
     }
    ```
    </p>
    </details>


- BODY has only children div.container which is always in center
    <details><summary>How?</summary>
    <p>

    ```scss
     .container {
    // We stop our website witdth to max 1200px. On devices with even bigger screens, we don't want the website to grow more in width
         max-width: 1200px; 
    //any extra space is distributed to the left and right, keeping our div in center
         margin: 0 auto; 
    //shorthand variations of margin
    //margin: top right bottom left 
    //margin: top-botton right-left
    //margin: all
     }
    ```
    </p>
    </details>

- Add SASS watcher
  ```bash
  sass scss:css
  #sass inputfolder:outputfolder
  #will compile ./scss/style.css to ./css/style.css
  ```
- Link CSS in your HTML
  ```html
    <link rel="stylesheet" type="text/css" href="./css/style.css" />
    <!-- Using a better font -->
    <link
        href="https://fonts.googleapis.com/css?family=Open+Sans+Condensed:300&display=swap"
        rel="stylesheet"
    />
  ```

- Edit CSS to make things look better
  ```scss
    body {
    // background-color: aqua;
    font-family: "Open Sans Condensed";
    font-size: 3rem;
    margin: 0;
    padding: 0;
    }

    .container {
        display: flex;
        flex-direction: column;
        // max-width: 1200px;
        //any extra space is distributed to the left and right, keeping our div in center
        margin: 0 auto;

        // Any child element of div.cotainer will have a different background
        * {
            // background-color: rgb(18, 22, 87);
            margin-bottom: 10px;
        }

        header {
            color: white;
            background-color: rgb(18, 22, 87);
            display: flex;
            //reason why all links were wrapped in one div
            //header has two divs as children, one for logo, one for links
            //space-between pushes links to right
            justify-content: space-between;
            margin-bottom: 0;
            padding: 0px 20px;

            .navbar-logo {
                animation: attention 2s infinite ease;
            }

            .navbar-links {
                a {
                    color: white;
                    text-decoration: none;
                    border-bottom: 1px solid transparent;
                    transition: border-bottom 1s;
                    font-size: 1.8rem;
                    padding: 0 10px;

                    &:hover {
                        border-bottom: 1px solid white;
                    }
                }
            }
        }

        .jumbotron {
            color: white;
            background-color: rgb(18, 22, 87);
            height: 500px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .stats {
            height: 400px;
            text-align: center;
            display: grid;
            grid-template-columns: 1fr;
            grid-template-rows: min-content 1fr;
            align-items: center;

            .statslist {
                display: grid;
                grid-template-columns: 1fr 1fr 1fr 1fr;
                grid-auto-rows: auto;

                .statsitem {
                    margin: 5px;
                    display: flex;
                    flex-direction: column;
                    background-color: rgb(140, 171, 192);
                    color: #000;
                    padding: 30px;
                    * {
                        color: #000;
                        background-color: rgb(140, 171, 192);
                    }
                }
            }
        }

        .testimonials {
            height: 30vh;
            text-align: center;
        }

        .paynow {
            text-align: center;

            a {
                text-decoration: none;
                color: white;

                i.fa {
                    background-color: #cc1414;
                    padding: 10px 50px;
                }
            }
            width: max-content;
            align-self: center;
            background-color: rgb(18, 22, 87);
            color: white;
            padding: 20px;
        }

        footer {
            background-color: rgb(18, 22, 87);
            color: white;
            text-align: center;
            font-size: 1.5rem;
            margin-bottom: 0px;
            i.fa {
                color: #cc1414;
            }
        }
        .fab {
            width: max-content;
            //sticking it always to bottom right of the view
            //view is the current dimension of the browser screen
            position: fixed;
            bottom: 0;
            right: 0;
            margin-bottom: 10px;
            margin-right: 10px;
            padding: 10px 20px;

            //styling other things
            background-color: white;
            color: black;
            border: 1px solid black;
            transition: all 0.3s;

            &:hover {
                cursor: pointer;
                transform: rotateZ(360deg);
                background-color: #000;
                color: #fff;
            }
        }
    }

    @keyframes attention {
        0% {
            margin-top: 0px;
        }
        50% {
            margin-top: -10px;
            font-size: 2.5rem;
        }
        100% {
            margin-top: 0px;
        }
    }

    @media only screen and (max-width: 920px) {
        .container .stats {
            height: 600px;
            .statslist {
                grid-template-columns: 1fr 1fr;
                grid-auto-rows: 1fr 1fr;
            }
        }
    }
  ```

## How it looked at start?
<img src="https://i.imgur.com/PgG5nj5.png" alt="drawing" width="400"/>
