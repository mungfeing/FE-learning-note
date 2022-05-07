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
  
  
 ### 7th May 
  
 ###### some concepts
 `line-height` For body:1.6 

`text-transform:uppercase/capitalize/lowercase`

`letter-spacing:1px-2px`

###### rgba

- `color: rgb()` and `rgba()`

- /* a = alpha */ /* alpha = opacity / transparency */
- a=[0,1]

#### Background

##### `background-position`

###### Numerical values

- A single value will move it that much on both the x and y axis
- If you include 2 values, the first will be on the x-axis, the second on the y-axis

###### Keywords

We can also assign keywords, such as `top left`, `bottom center`, `center right`, etc. This can be useful to control the position of the image when using `background-size: cover`.

##### Background-image

`background-image: url(folder/filename.jpg); or url(../images/my-image.jpg)`

- add a background-color to prevent once the image fails loading.

##### `Background-size`

When giving it numerical values, we can control the exact size of our image.

- `auto` is the default, nothing will change

- `contain` ensures that the *entire* image is visible. It might seem strange, but it can be used for something like a logo that's set as a background image, along with `no-repeat`
- `cover` will ensure that the image covers the entire space without repeating, but it will result in the image being cropped

##### `background-repeat`

We can prevent our image from repeating, either at all, or having it only repeat along a single axis.

###### Values

- `repeat` - the default
- `no-repeat` - the image will not repeat at all
- `repeat-x` - it will only repeat on the x-axis
- `repeat-y` - it will only repeat on the y-axis





#### The `+` combinator

This combinator will add a style if a selector is an adjacent sibling. So in this example, we see `h1 + p`. That means those styles will only apply to paragraphs that are directly after an h1.

#### The `~` combinator

This is the general sibling combinator. It will grab any selector that is a sibling to the first. So if we write `h1 ~ p` it will select all paragraphs that are siblings to the h1.



#### margin

- when the space between two line is too big and changing the margin to 0  doesn't work maybe try turning both lines' margin to 0.
