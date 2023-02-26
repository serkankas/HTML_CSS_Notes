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

> Chapter 6: Typography

>> Typography is the way that text is arranged and represented.

As far as I understood, this is the topic that shape the appearance of texts. For checking and learning more about it, style.css folder contains some examples. Also, uploading non-default font family is a well-known thing. Peope usually use [google fonts](https://fonts.google.com/) for it.

> Chapter 7: Styling Links

The link properties almost same with text properties. But they are classified in different tag, aka. __\<a>__ tag. These links, have different properties what people call, psuedo classes. For example, if the link clicked before, aka. __visited__.

I found the [mozilla](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)'s link is useful once again! 

The order of pseudo-classes should be like in this order.

1. element (alone)
1. visited
1. hover
1. active

The order doesn't that much matter. However, some of the properties might overwrite the others. Logical order should be used.

> Chapter 8: List Styles
