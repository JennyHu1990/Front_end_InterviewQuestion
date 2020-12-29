### 1. Customise framework(e.g Bootstrap)

1. ##### Concepts:

   - css framework: bootstrap, UIkit,semantic ui,bulma, animate.css

   - external css, internal css, inline css, 
   - css specificity

2. ##### simple CSS overrides

   - reference order

   - <head>
     <link rel="stylesheet" type="text/css" href="css/bootstrap.min.css">
     <link rel="stylesheet" type="text/css" href="css/custom.css">
     </head>

   - css specificity: type slector < class selector < ID selectors

     

3. ##### Sass

   - reason: boostrap written in sass

   - _variable.scss: sass variables

   - customization should be kept in a separate custom.css that lives outside Bootstrap SASS

   - ```
     |-- \bootstrap 
     | |-- \scss
     | | |-- \mixins 
     | | |-- \utilities 
     | | |-- (...more bootstrap .scss source files)| custom.scss <-- changes go here outside bootstrap's SASS source
     ```

     1. custom.css override variable that had !default values in _variable.scss

     2. Any additional custom classes that @extend Bootstrap classes can be defined after the `@import "bootstrap"`. These are added in the generated CSS after the customized Bootstrap classes

4. ##### Customize Bootstrap in web app

   1. Epic Boostrap. edit in visual, download css

      

### 2. CSS Methodologies

##### 1. Concept

- BEM: Block element Modifier  
- OOCSS: object-oriented css
- SMACSS: scalable and modular architecture for css
- Css: atomic css

##### 2. BEM: 

pros: modularity, reusability, structure



### 3. CSS pre-processor

1. ##### SASS, LESS,PostStyle

2. ##### Pros:

   ##### variables

   ```scss
   $font-size: 16px;
   
   div {
       font-size: $font-size;
   }
   ```

   ##### nesting

   ```scss
   $link-color: #999;
   $link-hover: #229ed3;
   
   ul {
       margin: 0;
   
       li {
           float: left;
       }
   
       a {
           color: $link-color;
   
           &:hover {
               color: $link-hover;
           }
       }
   }
   ```

   

   ##### mixins

   ```scss
   @mixin bordered($width) {
       border: $width solid #ddd;
   
       &:hover {
           border-color: #999;
       }
   }
   
   h1 {
       @include bordered(5px);
   }
   ```

   ##### extends

   ```scss
   .block { margin: 10px 5px; }
   
   p {
     @extend .block;
     border: 1px solid #eee;
   }
   
   ul, ol {
     @extend .block;
     color: #333;
     text-transform: uppercase;
   }
   ```

   ##### If/Else Statements

   ##### color operations

   ##### loops

   ##### math

3. ##### Cons

   Additional setup is needed to make a compiler work

   Any change require recompilation

   Compilation takes time 

   Source maps are required

   

### 4. Version Control

Git.

create repository

commit push pull

branch

remote git : Github

 

### 5. Device responsive

- Concept: design and development should respond to the user’s behavior and environment based on screen size, platform and orientation.

- How to deal

  ##### 1. ViewPort

  - Set the viewport
  - Ensure an accessible viewport
  - Size content to the viewport

  ##### 2. Use CSS media queries for responsiveness

  - Apply media queries based on viewport size
  - A note on `min-device-width`
  - Use `any-pointer` and `any-hover` for flexible interactions
  - use relative units

  ##### 3. Breakpoint

  - Pick major breakpoints by starting small, then working up

  ##### 5. Designer Ways

  - Design Patterns:

  - fluid ![mostly-fluid](https://developers.google.com/web/fundamentals/design-and-ux/responsive/imgs/mostly-fluid.svg)

  - Column Drop

    ![column-drop](https://developers.google.com/web/fundamentals/design-and-ux/responsive/imgs/column-drop.svg)

  - Layout Shifter

    ![layout-shifter](https://developers.google.com/web/fundamentals/design-and-ux/responsive/imgs/layout-shifter.svg)

  - Off canvas

    ![off-canvas](https://developers.google.com/web/fundamentals/design-and-ux/responsive/imgs/off-canvas.svg)

    ##### 5. Image: 

    - Responsive web design means that not only can our layouts change based on device characteristics, but content can change as wel





### 6.Browser Difference

##### what:

Making your website behave consistently across browsers

##### how:

1. validate the code- clean and w3c compliance
2. test according to requirement(customers)
3. using a framework 
4. reuse and reduce components
5. start with the difficult browser first



### 7. SEO Friendly

- identify crawl error
- mobile-friendly
- secure with https
- check loading speed
- Chunk Your Content to Maximize Readability
- Use Schema Markup



### 8. CSS flex box & grid

##### 8.1 Concept: container and item; main axis(horizon) cross-axios

container: 

- flex- direction: follow the article tour,

- flex-wrap: too large to display in one line
- flex-flow, justify-content, align-items,align-content

item:

- order

- flex-basis,flex-grow,flex-shrink,->combined in flex

- algin-self

##### 8.2 Grid

define  columns and rows: grid-template-rows and grid-template-columns

grid is a shorthand for grid-template-rows, column and areas

##### 8.3 Difference

Flex:One-dimensional space

grid:Two-dimensional space



### 9.CSS-in-JS

##### CSS lack of modules

##### Pros:

- bundles JavaScript component
- local scoping 
- encapsulation
- portability
- reusability



##### Cons

- extra layer of complexity
- code readability:generated selectors is hard to read
- When:
- A complex UX for a monolithic front-end