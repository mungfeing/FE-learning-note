# FE-learning-note
##### Css Units

###### percentage

- use % for width to make the website more responsive
- A percentage is always based on the width of its parent.
- and the parent block element has default width percentage of 100%
- the image is usually its size 

###### Min-width and Max-width

###### The em Unit

- The em and rem are considered relative, because they are relative to the font-size of other elements

- em are relative to their parent's font-size
- Font-size is an inherited property, so if you don't declare it anywhere, it's getting it from the body (or the default, which is normally 16px)
- Problem: cascading effect 
- em is relative to the font-size of this element, it won't scale out of control, but scales according to the parent element. 

###### rem

- The `rem` unit is short for **R**oot **em** because it is always relative to the `font-size` of the root of our page.
  In an HTML document, the root is always our `html` element. So when we use `rem`s we can keep the nice scaling for font-sizes like we saw with `em`, but because it is always relative to one single elment, there is no risk of cascading font-sizes that go out of control.

  ```javascript
  html {
      font-size: 10px;
  }
  ```

###### My general rule of thumb:

- Font-size = rem
- Padding and margin= em
- Widths= em or percentage
  -


- for `span` people often use compound selector `h1 span`

- classify the the general styling and specific styling

- there could be several container 

  ```javascript
   <body>
         <header>
              <div class="container">
                  <h1>CSS is a lot of fun</h1>
              </div>
          </header>    
          <section class="section-one">
              <div class="container">
                  <h2>Section One Title.</h2>
              </div>
          </section>        
          <section class="section-two">
              <div class="container">
              </div>
          </section>
      </body>
  
  ```



######  order(generic)

- body（font-size，margin）
- Typography
- Layout

###### media queries

> Media queries let us target differnt media types, as well as specific conditions within those types in our CSS.

- ```
  @media [media type] ([media condition]) { ... }
  ```

- An example
  In this below example, the background of the `body` will only be red when using a device that has a screen, and which has a width of 600px or bigger.

- `we need to write selector again!!`

  ```
  @media screen and (min-width: 600px) {
      body {
          background: red;
      }
  }
  ```

- media types

  - Screen @media screen {...}
  - Print @media print {...}
  - Speech @media speech

- The media condition let's us target specific conditions within that media type

  - Widths @media (min-width: 600px) {...}

  - Orientation @media (orientation: landscape){...}

    > - `landscape`
    >   The viewport is in a landscape orientation, i.e., the width is greater than the height.
    > - `portrait`
    >   The viewport is in a portrait orientation, i.e., the height is greater than or equal to the width.


  - Specific features  @media (hover){...}

    - `none`

      >The primary input mechanism cannot hover at all or cannot conveniently hover (e.g., many mobile devices emulate hovering when the user performs an inconvenient long tap), or there is no primary pointing input mechanism.
      >`hover`
      >The primary input mechanism can conveniently hover over elements.


- Using `and` to combine type and condition

  ```javascript
  @media screen and (mid-width:960px){...}
  ```


##### Navigation

>  Navigations are traditionally marked up using an unordered list, which is placed inside a ` <nav>`
>
>  element.

###### `object-fit`

- `object-fit` is such a cool property.
  To use it, an image needs to have both a `width` and `height` explicity set. Normally when we do that, unless it's the exact aspect ratio of the image, it will squish the image and make it look terrible. By using `object-fit:cover`, it will instead crop the image.

- remember the selector should specifically target the image. 

- ```js
  .work {
          display: flex;
          justify-content: space-between;
      }
    
  /*there is only image in the portfolio-item. and the width here is different from the width in the https://scrimba.com/learn/frontend/responsive-design-solution-11-horizontal-alignment-cQRqLzh8 */
      .portfolio-item {
          width: 28%;
      }
      
      .portfolio-item img {
          width: 100%;
          height: 15em;
          object-fit: cover;
          
      }
  ```

- 

- Along with `object-fit` we also have `object-position` which will control how cropped image is positioned. By defauly, it will stay with the center of the image.
  We can change this to, say, `object-position: top right;`, which will keep the top right of the image always in frame, and crop from the left and bottom instead. You can also specify a pixel value if you know the exact location that you want to lock into place.

- To ensure that all devices render our pages correctly, we want to include this meta tag in all of our pages
  `<meta name="viewport" content="width=device-width, initial-scale=1">`



###### responsive

- ```js
  .container {
      max-width: 570px;
      margin: 0 auto;
  }
  
  ```

###### Solution to the 'Some breathing room' challenge

- Width: 90% 
- or
- Padding 

###### prevent image overflow 

- ```js
  img {
      max-width: 100%;
  }
  ```
