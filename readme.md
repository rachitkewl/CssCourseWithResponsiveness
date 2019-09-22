# Building Skeleton of a Modern Single Page Application (SPA)

![skeleton of modern SPA](https://i.imgur.com/PgG5nj5.png)

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