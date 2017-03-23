## Evaluator: 
## Optional Notes: 

*  Refactor header to remove that extra markup (the div)
*  Potential refactor in button containers - maybe don't need them, or not both of them
*  Use percentages for box model props if you want relative units of measure. Save the em's for fonts and be sure to set a base font-size on your body
*  Consider refactor on the big if/else, research a switch statement in js

### Functional Expectations

* __Novice:__ Application meets all of the functional expectations in Phase One.
* __Advanced Beginner:__  Application meets all of the functional expectations in Phase Two.
* __Proficient:__ Application meets all of the functional expectations in Phase Three.
* __Exceptional__ You completed Phase Three and did something with Phase Four.

------------------------------------------------------------------

## HTML

#### Accessibility

* ____Novice:____ Knows what a semantic tag is and leverages the HTML5 structural tags to organize the content of their markup. 
* __Advanced Beginner:__ Leverages more precise semantic tags when applicable, and employs basic ARIA roles attributes for added clarity in structure, descriptive image alt attributes, title attributes for applicable anchor tags. 
* __Proficient:__ Employs detailed accessibility practices throughout markup, especially in forms and can speak to decisions made in accessibility choices as it relates to specific accessibility concerns. 
* __Exceptional__ Can run markup through a variety of online accessibility tools and score well for content, color, screen readers, etc. 

#### Style

* __Novice:__ Crafts markup with proper indentation and opening/closing tags. 
* __Advanced Beginner:__ Crafts markup with proper and logical nesting. 
* __Proficient:__ Crafts lean, efficient markup that is easy to read and follow across naming conventions, structure, and solid formatting that follows industry best practices. 
* __Exceptional__ Crafts lean, efficient markup and can speak directly to choices made to improve performance, including but not limited to, page load times, css/js optimizations, image optimizations. 

------------------------------------------------------------------

## CSS

#### Structure of Code

* __Novice:__ Can effectively target DOM elements via tag, class, and/or id and write CSS rules around each element to create the desired style. 
* __Advanced Beginner:__ Can cleanly and logically organize CSS rules according to similar categories (i.e. typography, layout, components), and then logically organize the remaining CSS rules based on flow of the markup. Organizes properties within rules alphabetically.
* Proficient : Leverages cascading styles and CSS specificity rules to create more complex targeting of elements in order to reduce, reuse, share styles across elements. Organizes properties within rules based upon industry standard principles of writing consistent, idiomatic CSS. 
* __Exceptional__ Understands the performance implications surrounding cascading/specificity and crafts CSS that is mindful of reducing complexity and increasing performance.

#### Implementation

* __Novice:__ Can articulate how the CSS box model works and apply it appropriately in a static layout.
* __Advanced Beginner:__ Can articulate the differences between the approaches of absolute/relative positioning, flex-box, floats, and can appropriately apply the approaches to solve a variety of layout problems.
* __Proficient:__ Develops layouts that work cross-browser, are responsive, and can logically defend the choices made in implementation approach for layout. 
* __Exceptional__ Can articulate rationale for all parts of the CSS implementation (each line of code/CSS rule) specifically in regards to the balance of: structure of code, design integrity, performance.

------------------------------------------------------------------

## JAVASCRIPT

#### Conditional Logic

* __Novice:__ Can understand when an expression evaluates to true or false.
* __Advanced Beginner:__ Uses if/else statements, but there are multiple levels of nesting, which makes the paths through the code difficult to follow. Understands what is "truthy" and "falsey" in JavaScript.
* __Proficient:__ Can use an if/esle statement to effectively handle multiple paths through the code. Writes if/else statements that only have one level of logic (no nesting). Can use logical operators instead of if/else statements where applicable.
* __Exceptional__ Can write conditional logic that is succinct and easy to read. Logic can handle all situations where user gives incorrect/unexpected input.

#### Functions & Scope

* Novice : Can write a simple function that takes at least one input argument.
* __Advanced Beginner:__ Developer is comfortable using multiple arguments to pass data into functions. Understands how variables are scoped at the function level and global level. Functions are named descriptively. Knows when and why to use return in a function.
* __Proficient:__ Functions have single responsibility. The entirety of the function is easy to read what functionality it contains. Function is generally shorter than 8 lines. Uses functions to eliminate repeated code. Comfortable refactoring any piece of code and extracting it to a function.
* __Exceptional__ Comfortable with using callback functions where applicable. Comfortable returning collections from functions (objects, arrays).

------------------------------------------------------------------

#### DOM Manipulation

* __Novice:__ Can articulate what the DOM is and can effectively target elements in vanilla JavaScript via class, id, or tag.
* __Advanced Beginner:__ Can add event listeners and create small functions that execute on events, can leverage the event object appropriately, and can articulate the what/why/how of jQuery.
* __Proficient:__ Able to extract information, modify attributes, or append/prepend data in the DOM easily regardless of whether they are employing vanilla JavaScript or jQuery. Understands how to harness event bubbling.
* __Exceptional__ Understands the potential performance impact imposed by leveraging vanilla JavaScript vs. jQuery in their implementation and will make choices accordingly based on the problem to solve.

#### Style

* __Novice:__ Can explain the choices made in the overall codebase and is able to articulate what every line of code is doing. Code is neatly formatted and easy to read with correct indentation.
* __Advanced Beginner:__ Code shows strong effort toward organization, but suffers from long functions, unnecessary or poorly named variables, and requires significant refactoring. Application may have some duplication and minor bugs. 
* __Proficient:__ Code is logically organized, such that reader can easily follow the progression of the app because variable and function names are descriptive and follow a single responsibility approach. There are no major bugs and minimal duplication.
* __Exceptional__ Application demonstrates excellent knowledge of JavaScript syntax, style, and refactoring. Application has exceptionally well-factored code with little or no duplication. 

------------------------------------------------------------------

## DESIGN

#### Comp Recreation

* __Novice:__ Can establish a complementary color palette, integrate font(s), and execute a handful of the large comp details. 
* __Advanced Beginner:__ Can accomplish about 50-75% of the large and small design details and can logically rework them on at least 1 breakpoint. 
* __Proficient:__ Developer captures the spirit and design intent of the comp. Some small details need polish to achieve a pixel-perfect match to the comp, but developer is clearly mindful of details and has made a conscious and careful effort to match the comp. Any design decisions left open to interpretation are handled thoughtfully and are well executed, but are more noticable and/or unintuative than they would be if the designer had provided the solution, or may not be totally seamless during screen-size transitions.
* __Exceptional__ Developer skillfully captures the spirit and design intent of all comp details. Execution is pixel-perfect and any design decisions left open to interpretation are solved intentionally, are as seamless as if the designer had provided the solution, are handled gracefully, and enhance the overall design.

