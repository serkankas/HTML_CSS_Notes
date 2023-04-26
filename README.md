# This course will be related with CSS notes.

It will be seperated into files, if need more explanation than feel free to do your own research. As the notes are taken in time, I'll gave resources that I found useful.

The original video course will be given in the [link](https://www.youtube.com/watch?v=OXGznpKZ_sA). The files will be set based on the codes which will be written in this page. The content may not be enough for you. In these cases, feel free to do your own search.<br>
Happy Learning!
<hr>

CSS is short version of Cascading Style Sheets. The more detailed explanation can be found in this [link](https://developer.mozilla.org/en-US/docs/Web/CSS).<br>
However, I am going to explain whait is CSS and what is simple front-end stack like the person who has no idea.<br>
Front end is based on three simple element we could say, ~~simply~~.
1. Content (Structure)
1. Style (Presentation)
1. Functionality.

![Picture](/Pics/1.jpg 'HTML - CSS - JS terminology')

As I mention above, you could see that if we think human body as front-end application. The scheme should look something like this. Content/Structure is ___HTML___. You can only have this in order to present something. However, it'll not be pleasent to look at it if it doesn't have style on top of it. For that purposes, you could style your HTML with ___CSS___. Most of the pretty website can be made with HTML + CSS. However for more functionality, or may more advance styling, ~~I currently doesn't have the necessary information~~, you could add ___JavaScript___. Also there are well-known JavaScript frameworks like Vue, React, etc. that makes your job easier, ~~as far as I've been told~~, but that's another topic that I am not aware of.

Then, Let's dive into the course and the chapters.

1. [Chapter 1: Start Here](#chapter1)
1. [Chapter 2: CSS Selectors](#chapter2)
1. [Chapter 3: Colors](#chapter3)
1. [Chapter 4: Units & Sizes](#chapter4)
1. [Chapter 5: Box Model](#chapter5)
1. [Chapter 6: Typography](#chapter6)
1. [Chapter 7: Stylink Links](#chapter7)
1. [Chapter 8: List Styles](#chapter8)
1. [Chapter 9: Mini Project](#chapter9)
1. [Chapter 10: Display](#chapter10)
1. [Chapter 11: Floats](#chapter11)
1. [Chapter 12: Columns](#chapter12)
1. [Chapter 13: Positions](#chapter13)
1. [Chapter 14: Flexbox](#chapter14)
1. [Chapter 15: Grid Layout](#chapter15)
1. [Chapter 16: Images](#chapter16)
1. [Chapter 17: Media Queries](#chapter17)
1. [Chapter 18: Card Project](#chapter18)
1. [Chapter 19: Pseudo Classes & Elements](#chapter19)
1. [Chapter 20: Variables](#chapter20)
1. [Chapter 21: Functions](#chapter21)
1. [Chapter 22: Animation and Transformation]

<section id="chapter1"></section>

> Chapter 1: Start Here

There are 3 common way to apply your CSS to HTML.
1. Inline Styling Sheet
1. Internal Styling Sheet
1. External Styling Sheet

I will quickly demonstrate the examples. But then, I'll apply all my CSS through the External Styling Sheet as much as possible. That's the way that I prefer since, everything seems more organized.

__index.html__
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lesson 1</title>
    <link rel="stylesheet" href="style.css">
    <style>
        h2 {color: #aaa;}
    </style>
</head>
<body>

    <h1>This is line from External Styling Sheet</h1>
    <h2>This is line from Internal Styling Sheet</h2>
    <h3 style="color: #ccc;">This is line from Inline Styling Sheet</h3>
    
</body>
</html>
```
__style.css__
```css
h1 {color: #bbb;}
```

Now, let's dive into which section means what. Inside ```<head>``` tag you'll see ```<link>``` tag. That's the way we link our external styling sheet to our HTML page. Just one line later, we create ```<style>``` tag. That's our internal styling sheet tag. And lastly, inside the ```<body>``` tag, you will see the tag ```<h3>```. As you can see I put another style parameter inside of it. That our inline styling sheet. The result will look like this.

![Picture](/Pics/2.png)

Styling is happen in CASCADE. OR simple term, it'll overwrite until the last code. Let's say you write one rule in external CSS file, but then you write inline CSS to a specific tag. The CSS file still be applied to all other tags but written with inline. Written with inline will be compiled last in inline CSS, which makes the that styling works for that specific tag.

For further explanation for basic rules, you can follow the mozillas official [link](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics) here. Also in the course it mentions that, there is a [CSS Validation Service](https://jigsaw.w3.org/css-validator/). Feel free to check and use in your own purposes with your own responsibility.

<section id="chapter2"></section>

> Chapter 2: CSS Selectors

For further of this course, I am going use dummy text generator what I call from this [link](https://www.blindtextgenerator.com/lorem-ipsum). Feel free to check and use.

I am going to write the explanation in here, but feel free to check the written document in the relevant files. Chapters will be stored in ```env/L{chapter number}```. For instance, If you want to reach chapter 2 codes, you'll open the __env/L2__ folder.

Firstly, we create body element styling. Every HTML contains 1 body element per page. The manipulated element properties are usually the ones that either inheritable or the effect will be happens in the whole body.

We see three different selector in css
1. Element
1. Class
1. Id

Element is basically tag that will manipulated for all the tags.
<br>Class is used for grouping some content. If you use one specific group of tag has certain property, you can use class/es.
<br>Ids has to be unique for each element. Not recommended to use most of the time.

Priority Order will be like:

Ids > Classes > Elements

Bigger priority always erase the lower ones.

We can apply multiple element with group selection like
```css
h1, h2 {
    /* Some CSS Properties, etc. */
}
```

It doesn't has to be elements only, it can be class, element, id and combination of all.

```css
p span {
    background-color: goldenrod;
}
```

As you can see here, when we remove the comma symbol ```,``` it will search for span tag inside the p tag.

There is another concept call CSS Reset / Universal Selector. However, it's not that common to use it.

```css
* {
    font-family: monospace;
}
```

 _Inheritance can only be importing from parent tag. When I mean parent tag, it's simply shown as this. The example below p tag is parent tag of span tag. Lastly, Inheritance not apply the all properties. The properties like font, font-size, etc. can be inherited. However, the border, for example, cannot be inherited. Should've been applied all the tags seperately. Here's the [link](https://web.dev/learn/css/inheritance/) that properties can be inheritable._

```html
<p>
    <span>
        text
    </span>
</p>
```

Not recommended to use it but, there is ```!important``` keyword that you can put any properties end like ```color: gray!important;``` With that, all the rules will be regardless of any situation mentioned before.

<section id="chapter3"></section>

> Chapter 3: Colors

There couple way to present color in CSS.

```css
<element> {
    color: blue;
    color: #00f;
    color: #0000ff;
    color: rgb(0, 0, 255);
    color: rgba(0, 0, 255, 1);
    color: hsl(240, 100%, 50%);
}
```

Now let's start from original. Blue is simple color which can be obtained from RGB color combination. The ones who don't know RGB is stands for, Red - Green - Blue. When we gave 0 red, 0 green, and 255 blue. It will return the Blue. 255 decimal is equvelent of FF in hexadecimal.<br>
The second explanation is, ```00F``` which is originally stands for ```0000FF```. It's short version of like this ```a```a```b```b```c```c. It duplicate the all values next to it. If you want to conver for example 0022FF, you can write 02F. However you can't duplicate 808080 since there is no pairing next to it. __EVEN__ 888880 cannot be written with short version.<br>
We already mention the first 4 declaration. Now, the RGBA is similar to RGB however A is stands for Alpha channel which is using for transparency. Instead of 0 - 255, it's used between 0 to 1. 1 For fully shown and 0 is completely disappear.<br>
Lastly, HSL is used. However, I don't know how it's used. I, probably, not going to use it. But feel free to do your research. Also, there is hsla same deal with hls but transparency.

<section id="chapter4"></section>

> Chapter 4: Units & Sizes

There are way more units for sizing than what we need. The units will be shown whichs most used in daily basis according to instructor in the link. So, I am going to stick with that. At the end, we want to focus on whats mostly popular in daily uses.

The sizes is given in the mozillas official [link](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units#numbers_lengths_and_percentages). _As far as he says, the one absolute size that front-end uses is pixels._ Default page font-size for paragraph is 16px, aka. 16 pixels.

width parameter is gots it's scaling from parent tag if the percentage is used. For example, Let's say body is parent tag and h2 is child tag. With that matter, if you construct like

```css
body {
    width: 50%;
}

h2 {
    width: 50%;
}
```

The ```h2.width = .5 * body.width```. Which is ultimately, makes h2 size __0.25%__. That's what we call relative-length unit. The reverse is absolute-length unit. You can also check those from mozillas-link.

| shortcut | description/stands for
|--- |---
| rem | Root Element
| px | Pixel/s
| em | Element (looks for parent, not root.), not recommended to use that often.
| ch | Character, before we wrap the line, we put that amount of character. Like so
| vw | view width

The __vw__ does not recommended to use since, it doesn't count the scroll-bar at left (if any), but % counts for that. Which makes the pages look better.

<section id="chapter5"></section>

> Chapter 5: Box Model

>> Quick Note: <br>
Turning box into an circle. You could use element property called border-radius. If you add half of the height, it will turn your box into cicrle. If you use less, it will turn elipse shape. If you use more, seems like nothing happens.

To have more control and understand over the CSS on your project. You should know and get familiar with the Dev Tools of Browsers. __CTRL + ALT + I__ should open your dev tools in chrome. If that doesn't worked. Right click the browser content, and select the option called __inspect__. Either of that should work. When you access the pages, there are multiple layer/section that help you to understand what is going on with your css & html. What we are going to focus, ~~initally~~, is computed section.

![Picture](/Pics/3.PNG)

When you access to that section, we will see 4 layer of our design. We can select/manipulate/see the layer of element in here. From outside to inside:

1. Margin: Shown with dark brown~ish color: This is the space between our model and the next coming model.
1. Border: Shown with light brown/orange~ish color. That's show the border-lines of our element.
1.  Padding: Shown with Light green color. This is space between your border lines and content. If you have border tag used with dash or solid let say, this is the space will appear between your content and your border.
1. Content: Shown in blue. This is the property section that captures the style in your content.

__box-sizing__
|type|how it's works
|---|---
|content-box| This is make the width of content. That's might be faulty, since the padding, border, and margin is not included. So, it may hard to control over it.
|border-box| This is make the width or border. Apart from margin, all the total box size width set for border. Including, padding and content. It may much useful in some cases.

<section id="chapter6"></section>

> Chapter 6: Typography

>> Typography is the way that text is arranged and represented.

As far as I understood, this is the topic that shape the appearance of texts. For checking and learning more about it, style.css folder contains some examples. Also, uploading non-default font family is a well-known thing. Peope usually use [google fonts](https://fonts.google.com/) for it.

<section id="chapter7"></section>

> Chapter 7: Styling Links

The link properties almost same with text properties. But they are classified in different tag, aka. __\<a>__ tag. These links, have different properties what people call, psuedo classes. For example, if the link clicked before, aka. __visited__.

I found the [mozilla](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)'s link is useful once again! 

The order of pseudo-classes should be like in this order.

1. element (alone)
1. visited
1. hover
1. active

The order doesn't that much matter. However, some of the properties might overwrite the others. Logical order should be used.

<section id="chapter8"></section>

> Chapter 8: List Styles

The notes are provided in CSS and HTML. So you should check those, there is not much to tell about. Only thing that might be interesting is, [pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) next to [pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements). Also another interesting thing is, marker element. The [example](https://developer.mozilla.org/en-US/docs/Web/CSS/::marker) is shows the usage. but interesting thing is, even if you declare your list-style none, the content will appear 

<section id="chapter9"></section>

> Chapter 9: Mini Project

There is a small project that he made. I made a little different project. Instead of just making navbar, ~~which by the way was cool~~, I made a To Do kinda webpage. Feel free to check!

<section id="chapter10"></section>

> Chapter 10: Display

So, display is a property will show what kind of behaviour that html element will take. For example, \<p> tag is block type display element meanwhile, \<span> tag is inline type display element. Well, consider their boundries, we gave small CSS like this.

```css
@import url('https://fonts.googleapis.com/css2?family=Source+Code+Pro&display=swap');

body {
    font-size: 2rem;
    font-family: 'Source Code Pro', monospace;
}

p {
    background-color: lightgray;
}

span.opposite {
    background-color: blueviolet;
    padding: 3rem;
}
```

So with that being applied, the default image will look like this.

![Picture](/Pics/4.png)

As you see, __inline__ structure crushes the other line corresponds. When we gave property of __display: block;__ inside the span element it will look like this.

![Picture](/Pics/6.png)

Well that's not what we exactly wants sice, the paragraph itself broken into pieces. So there are more display types then what we learned so far. The one we looking for for that specific matter is __inline-block__. Which is combination of inline and block. That type actually saves your boundary, while it does not broke the whole block.

![Picture](/Pics/5.png)

More information can be found in official [mozilla's link](https://developer.mozilla.org/en-US/docs/Web/CSS/display), feel free to check and learn more!

<section id="chapter11"></section>

> Chapter 11: Floats

Float properties, makes the element put in html meanwhile the structure doesn't interrupt that much. It hard to explain, but it's easy when you see visually. Feel free to check [example](/env/L11/index.html). We add clear class to a div, to clear that float property. ~~You could see how the last line seperated from others.~~

There is a section where we should take attention in [video](https://www.youtube.com/watch?v=OXGznpKZ_sA&t=11321s). That's a think I can't explain verbally. Watch ___until end___ of that section!

<section id="chapter12"></section>

> Chapter 12: Columns

Column is basically another property that will divide you width into specific number that you wish.

<br>
<style>
    .columns {
        columns: 3;
        column-rule: 3px solid #333
    }

    .columns p {
        margin-top: 0;
    }
</style>
<hr>
<section class="columns">
    <p>
    Test Line that inside the columns. Some Random letters that fills some space with it. Please note how the text are seperated inside the columns
    </p>
    <p>
    Test Line that inside the columns. Some Random letters that fills some space with it. Please note how the text are seperated inside the columns
    </p>
    <p>
    Test Line that inside the columns. Some Random letters that fills some space with it. Please note how the text are seperated inside the columns
    </p>
    <p>
    Test Line that inside the columns. Some Random letters that fills some space with it. Please note how the text are seperated inside the columns
    </p>
</section>
<hr>
<p>
Test Line that outside of the columns. Some Random letters that fills some space with it. Please note how the text are seperated outside of the columns
</p>
<p>
Test Line that outside of the columns. Some Random letters that fills some space with it. Please note how the text are seperated outside of the columns
</p>
<p>
Test Line that outside of the columns. Some Random letters that fills some space with it. Please note how the text are seperated outside of the columns
</p>
<p>
Test Line that outside of the columns. Some Random letters that fills some space with it. Please note how the text are seperated outside of the columns
</p>
<hr>
<br>

There is also another point that mentioned inside this episode. Which is, margin collapce. Now let's assume that there are two different element stand on top of each other. Margin bottom of top element will be collapse with margin top of bottom element. That's what they called, margin collapsing. That's not a bad thing totally. You could use carefully and apply according to your needs.

There are some prevention that can be taken before the column rules apply. Let's assume that you put one header in middle of the text inside the columns section. You want that header to stay at top. Sometimes weird issues can be seen like mention in video. In order to prevent that, we could add two different parameter.

1. break-inside: avoid;<br>
What this does is, it'll prevent to break your header into multiple section. Which makes sense, since the header should be stayed at one piece.

However, header also should be at top right? 

2. break-before: column;<br>
That's a prevention that set your haeder to the top. However downside of this usage is, you cannot go for one line with resizing window. When you go for that low, it'll shrink your text, etc. Since this line is force you to make some column break in anyway.

___OQN___: You could find some useful symbol that could be usable inside html in the [link](https://old.unicode-table.com/en/).

Another property that might be useful for this page setup is column-span property. That property gives you full break through column, and continue with column as well. You can see the example usage inside the page.

<section id="chapter13"></section>

> Chapter 13: Positions

Positions of elements, this example will use some boxes to show what is exactly going on with it.

First thing that I realize in this lesson is, you can give multiple class to an element. Example usage would be like ```class="class-1 class-2 class-3"```. If you seperate them with space, it means it'll be different classes. That's a new information for my aspect.

Now, position property has multiple options. You can find some visual presentation in official mozillas [link](https://developer.mozilla.org/en-US/docs/Web/CSS/position) 

1. static: This one is default. Basicly put the position compared to its parent. I am not sure if it's much useful than that. It's put your object into static position where it doesn't change.
1. absolute: This one is obviously absolute position. If you gave any sort of reference to it, it will shown in that place. The problem with it, I believe, If your page is changing, it may have couple issues. It's also bind it's absolute position to nearest relative position.
1. relative: This one is relative to it's parrent classes. Doesn't matter if the parent container is relative or not like the siutation in absolute.
1. fixed: This one is fixed position. Which means that if you even scroll down, the placed element stays there. Fixed element stays at top of the elements that has been written previously. If you wrote element that's been written after fixed, it will overlay the fixed element
1. sticky: This one is similar to fixed one. But the boundary is binded to parent element instead of full page.

<section id="chapter14"></section>

> Chapter 14: Flexbox

Yet again one of the hard topic to explain. Displaying in Flexible property. What it does, ~~as far as I understand~~, lay the items the desired position. with different properties, you could start from right to left. You can place them centerwise, you could evenly distribute them. When I mean by laying, you could check from the mozillas official [link](https://developer.mozilla.org/en-US/docs/Web/CSS/display). example usage would be like this.

```css
.desired-class {
    display: flex;
    /* depends on your desired wishes, these properties might be usefull.
    gap
    flex-flow
        flex-direction
        flex-wrap
    justify-content
    align-content
    align-items
    flex
        flex-grow
        flex-shrink
        flex-basis
    order
    */
}
```

There's a small example that you could play. My suggestion is check the [game](https://flexboxfroggy.com/) with the help of [properties](https://developer.mozilla.org/en-US/docs/Web/CSS). The properties shown at Reference -> Properties.

<section id="chapter15"></section>

> Chapter 15: Grid Layout

This is a layout that we use for display options. That's basically divide your page into grid-like structure. Then, you can place your section as you wish. Here's the cool example from mozillas official [link](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout).

You can check the grid column/row with the dev-tools. Open dev-tools, elements tab, layout section. In that particular section, you'll see ___grid overlays: main container___ ~~or other grid layers~~. When you enable it, you'll able to see the grids of the page.

The ```grid-area``` properties is allows you to seperate as grid view as you wish. [Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout) and [Grid Areas](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Areas) example are hopefully clear for the usage. Example usage should be check in L15 inside the env.

<section id="chapter16"></section>

> Chapter 16: Images

Images can be classified as two different category.

1. Background Image
1. Foreground Image

The image as concept is very straightforward. However, there might be much useful things to learn. 

1. As a display element, it is not block element but it is inline element. Which means, it will not cover whole block in some cases.
2. Background image is repeating since it tries to fill the whole background. Some useful properties related with background is given in the [link](https://developer.mozilla.org/en-US/docs/Web/CSS/background).

One suggestion, if you want to fill your background image with complex images, you could use text-shadow. You can find example usage in the [link](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow)

Also I found a strange behaviour about images. Let say you set your image height and weight, expect to behave image based on that. However, that's not the case. If you plan to use your photo, cropped it first according to shape that you want.

There is also one other cool think called linear-gradient for background-image property. Check the example shown in [here](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/linear-gradient).

The __background__ property, ~~that contains multiple properties~~, is shown the order @5:32:07 in course. Feel free to check that part.

<section id="chapter17"></section>

> Chapter 17: Media Queries

There is specific writing rule of CSS for media queries. Here is an example usage of media query.

```css
@media media_type and (condition: breakpoint) {
    // css Rule
}
```

1. Start with __@media__ to tell CSS it's a media query.
1. Then point it out what type media/s that we will affected by that query.
1. In paranthesis, we gave condition and breakpoint.
1. Inside the curly braces, we override CSS properties again.

We can set condition based on min-width or max-width. They usually go for min-width based design since, they called the structure __Mobile_First__ kinda design.

Here's the reference [link](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) from mozilla's website. There some common breakpoint that has been published by author of this course. You can find the markdown from [link](https://github.com/gitdagray/css_course/blob/main/17_lesson_starter/notes.md).

<section id="chapter18"></section>

> Chapter 18: Cards Project

In this project, we will create a template for people and their cards. You can check the project it self for coding. I am not going to explain in this section. Check the relative files.

<section id="chapter19"></section>

> Chapter 19: Pseudo Classes

Difference between Pseudo Classes and Pseudo Elements

| Classes|Elements
|---|---
| Classes access the object with in states. Like if selected or hover it etc.| It acts like adding new element in to HTML codes.
| Uses one colon __:__ | Uses two colon __::__

This part is relatively verbal one. So you can either watch or check the mozillas official [link](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements).

<section id="chapter20"></section>

> Chapter 20: Variables

This is one of the main and simple chapter in programming overall. We, usually, want to build our designs, doesn't matter backend, frontend or other type of programs, based on variables. Since the variable can be replacable once, but will impact as many times as you used it.<br>
For example, let's say you use two different color for your front-end as main and secondary background color. You defined in your css once. Then, you can apply let say 50 different places. Whenever you want to change either or both color, you simple change the variable instead of changing all 50 places from beginning to end.<br>
It is also provides you to DRY (__Dont Repeat Yourself__) your code.

```css
/* Variables */

:root {
    /* Colors */
    --BGCOLOR: #475569;

    /* Font Related */
    --fontsize: 1.5rem;
    --font-type: sans-serif;

    /* General */
    --GRADIENT: radial-gradient(#123, #555);
    --BORDER-TYPE: border: 2px solid var(--BGCOLOR);
}

body {
    background-color: var(--BGCOLOR);
    background-image: var(--GRADIENT);
    border: var(--BORDER-TYPE);
    font: var(--fontsize) var(--font-type);
}

```

As you can see in here, we use __root__ pseudo-classes to declare our variables. The main reason behind its, Every element in html and css (including html tag as well), reference this pseudo-classes. Which means everything you wrote inside of it, can be accessable by other places as well.<br>
Accessing variable is also very easy. You can access with built-in css function called __var()__. This function look for parent classes or related classes that if this variable is defined in somewhere.

Variables contains from very basic color code or text sizes to, complex css function if you wish.

There are couple different naming for using variable. However, it's all preferences. I __HIGHLY__ suggest that you pick one styling, and stick with it. Since the consistency increase the code readability.

There is over-writing variable for css. You can check in video __@07:16:30__. That's an useful feature that you can apply.

Also, __@07:19:00__ it shows about dark mode application, etc. You can check that too if you wishes so.

<section id="chapter21"></section>

> Chapter 21: Functions

There are multiple functions that we already use in our previous example and so. You can check variety function in mozillas [link](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Functions). This part is also verbal one. That's why if interested, watch the source. There is almost nothing to watch about it.

<section id="chapter22"></section>

> Chapter 22: Animation and Transformation

This section is a topic that should be applied in css carefully. Since this is so powerful application, not doing may seem like not modern at all, but over doing may seen like overkill. You have to find the sweet-spot of the animation and transformation.

Let's dive into different varients.

```css
/* Transform is key property. */
div {
    transform: translateX(50%)
} 
```

The __50%__ mark basis on the container itself but not page itself. All the transform function can be found in the mozillas official [link](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function).

transform functions:
1.  translate
    1. translateX
    1. translateY
    1. translateZ
    1. translate3d
    1. translate
1. rotate
    1. rotateX
    1. rotateY
    1. rotateZ
    1. rotate3d
    1. rotate
1. scale
    1. scaleX
    1. scaleY
    1. scaleZ
    1. scale3d
    1. scale
1. skew
    1. skewX
    1. skewY
    1. skew

These functions used for transitions. When we have, 