# Root One Portfolio Header

Now that we have narrowed the focus of our planning to individual sections, let's begin working on the first section of our application, the header:

<p align="center">
  <img src="assets/readme_assets/header.png" alt="Portfolio page wireframe">
</p>

In the structure of the header, we have four text elements, with one placed against the left side of the row, and three placed against the right side of the row with a little space between them. There are multiple different ways we could accomplish this layout, but we want to find the [path of least resistance](https://en.wikipedia.org/wiki/Path_of_least_resistance).

Rather than trying to force this layout using margin, padding, positioning, or other forceful ways to push an element around, we want to create a design that achieves this effect based on sizing the elements appropriately and consistently. One of the best ways we can accomplish this is using a [grid system](https://github.com/Learning-Fuze/lfz-lessons/tree/master/exercises/css-basic-grid). Let's start by breaking up the internal elements of this section into the containers we want to group our elements into.

Viewing our model for this section, we can see one distinct groupings of elements that would be a perfect use of a container to surround them:

<p align="center">
  <img src="assets/readme_assets/nav_section.png" alt="Portfolio page navigation grouping">
</p>

These nav elements are all going to be distinct elements, but they have all been moved as a group towards the right-hand side of the section. We could position each of these elements individually, but that would make this a much more intense task. If we consider the group of elements as one whole, however, we now have a situation where we need one element to sit against the left edge of the row, and one container to sit against the right edge of the section. This is much easier!

<p align="center">
  <img src="assets/readme_assets/header_sizing.png" alt="Portfolio header sizing and placement">
</p>

For the sake of our application, we will be using a grid system with **12 columns**. As such, we can now start to consider the size our elements should take up. The "Student Name" headline and nav element container do not take up all of the available space on the row, so we should be leaving some extra space in their sizing. The nav container is taking up about half of the row, so it should take up **6 columns** of the total twelve columns. Finally, the headline with your name will take **4 columns**, which leaves us with **2 columns** left over to use as **space between** the elements. Now that we have a plan of action, we can begin coding this section out!!

# Feature Set 1 - Basic HTML structure

In your `root-one-portfolio` folder, please do the following:

1. Create an empty `style.css` file and an empty `index.html` file.
1. Add an HTML skeleton to your `index.html`.
1. In the `head` element of your `index.html`, add a `link` element linking to the `grid.css` file included with the content for this project, as well as a link to your `style.css` file.
    - **NOTE**: Please make sure that your `style.css` is being linked below the `grid.css` file.
1. Look at the contents of the `grid.css` file. You will notice that this is the same grid provided by us for the grid exercise you completed previously.
1. Within the `body` element, add a `div` element with a class of `container`. This element will serve as the wrapper for all of the content of the page.
1. Within the `div`, please add a `header` element with a class of `row`. This element is a [semantic element](https://www.w3schools.com/html/html5_semantic_elements.asp) which describes its content as "header" content. This element will serve as the container for all of our header content, and the `row` class will declare this element to be a row in the grid system of our document.
1. Give the `header` element a child `h1` element.
    - The text content of the `h1` should be your full name.
1. Give the `h1` element you just created the class `col-4`. This will set up the name headline to take up the four columns we determined it should take up in its row.
1. Give the `header` element another child of a [`nav` element](https://www.w3schools.com/tags/tag_nav.asp).
    - The `nav` element here will serve as the container for our group of anchor tags to link to sections in the document. Since these elements are being used for navigation, a `nav` element is the proper semantic choice of element to describe its purpose as well as a proper choice of element to contain these elements.
1. Give the `nav` element four child `a` elements. These elements should have the following configurations:
    - First `a` element:
      - text content: `About`
      - attributes:
        - href: `"#about"`
    - Second `a` element:
      - text content: `Technologies`
      - attributes:
        - href: `"#tech"`
    - Third `a` element:
      - text content: `Projects`
      - attributes:
        - href: `"#projects"`
    - Fourth `a` element:
      - text content: `Contact`
      - attributes:
        - href: `"#contact"`
    - **NOTE:** The `href` attribute values in the `a` elements we just created do not link to an external location, but actually scrolls the page to the `id` provided. These `id`s do not exist yet, but we will make them as we continue with this project.

And that's it for the HTML we need to write for this section! Now we can move into preparing for the CSS we will be applying.

# Feature Set 1 - CSS Basic Setup

To begin our CSS, we will start by creating some [utility classes](https://github.com/Learning-Fuze/lfz-root1-lessons/tree/master/exercises/css-utility-classes).

1. In your `style.css` document, create a new CSS rule selecting all elements with a class of `text-center`. Within that rule, set the `text-align` property to have a value of `center`.
    - This is an example of a "utility class". Notice that the class name does not describe what element will receive this styling, but rather describes the styling applied to that class, so that the class can be applied to any element we want to use that styling on and immediately understand what that class is doing.
1. Below the rule you created in the above step, create a new CSS rule selecting all elements with a class of `white-text`. Within that rule, set the `color` property to have a value of `white`.
1. Create a new CSS rule selecting all elements with a class of `pb-50`. Within that rule, set the `padding-bottom` property to have a value of `50px`.
    - This is an example of a utility class designed to make use of an abbreviation to describe the property and value being set. Alternatively, we could make the class name something like `padding-bottom-50`, but that is getting pretty lengthy, so by using the abbreviation `pb-50`, we can provide the same information describing the class' effect in far fewer characters.

The rest of the utility classes we will make for this section are meant to work in conjunction with our grid system, which is built using "flexbox". While the grid system provides all of the classes we will need for sizing, we will need some classes for positioning items using "flexbox" within their rows in the grid.

1. Create a new CSS rule selecting all elements with a class of `justify-center`. Within that rule, set the `justify-content` property to have a value of `center`.
1. Create a new CSS rule selecting all elements with a class of `justify-evenly`. Within that rule, set the `justify-content` property to have a value of `space-evenly`.
