# Learn Tachyons

![tachyons-intro-image](https://cloud.githubusercontent.com/assets/194400/25710569/87726714-30e4-11e7-9532-4a447bd61629.png)


_**Learn** how to use **Tachyons**
to **craft beautiful, 100% responsive, <br />
functional** and **fast User Interface/Experience** (UI/UX)
with **minimal CSS**_!

## _Why_?

The User Interface (UI) or User Experience (UX)
is the part of your application that
the ***people*** ("_end users_")
_**see** and **interact** with_.
Ensuring that the **UI/UX** is the _**best** it **can be**_,
is _easily_ the ***top priority*** for our Web/Mobile projects.

Without ~~good~~ ***great UI/UX***
["_**nothing `else` matters**_"](https://youtu.be/tAGnKpE4NCI)
to the person _using_ your app.
The **UI/UX** is what _**matters**_,
**not** the **programming language**,
what type of **server**,
which "***front-end framework***"
or "**backend infrastructure**" you are using;
***Nobody cares*** about the "_boring technical details_",
they care about their own _experience_ using the it.

### _30 Second Summary_

Through _experience_
(_building **many web/mobile** apps large and small
  in teams ranging from 2 - **200 people**_),
we have found that:
+ _**Hand-writing CSS**_ is _**tedious** and **repetitive**_
+ Using (_most_) CSS "_frameworks_" results in:
  + Lots of **Duplication** _where people re-create styles over-and-over_
  + "**_Zombie_ Code**" _unused styles that nobody will risk removing_
  + **Bloated** apps/sites that take _much_ longer
  to develop, load and maintain than they _neeD_ to.
+ **_Functional_ CSS** _ensures_:
  + UI is **100% _Predictable_, Consistent**
  and _free from_ (_unwanted_) "***Side Effects***"
  (_where a change in one place "breaks" something else!_)
  + It is ***immdeiately clear*** from reading ***one***
  block of code what the component _does_ and what it looks like.
  + **_Updates_** to UI are made in ***One Place/File***. (_see diagram below_)
**Time** to _develop_ your App's UI ***scales proportionally***
  instead of increasing ***exponentially*** the way it does

Tachyons is a "_feature complete_" CSS System that has ***all***
the ***building blocks*** <br />
you (_your team_) need(s) to
[_build **anything** you can **imagine**_](https://youtu.be/Um-PlX6oPBQ?t=12s
  "The LEGO Movie Scene "I am a Master Builder!").



## What?

![what-section-header](https://cloud.githubusercontent.com/assets/194400/25712542/da21aace-30e9-11e7-98b1-b09848a62cbc.png)

Tachyons is a **CSS _Design System_** anyone can learn/use
to craft beautiful, responsive & fast UIs with minimal CSS!

Tachyons embraces a different style than many popular CSS
frameworks known as `Functional CSS`. But how is it different?

Here's a some CSS for a bootstrap `primary` button:

![btn](https://cloud.githubusercontent.com/assets/14013616/20070844/eec73158-a519-11e6-9011-5b8cc14f73ac.png)

```css
.btn-primary {
  color: #fff;
  background-color: #337ab7;
  border-color: #2e6da4;
}

.btn {
  display: inline-block;
  padding: 6px 12px;
  margin-bottom: 0;
  font-size: 14px;
  font-weight: 400;
  line-height: 1.42857143; /* who needs this level of decimal precision in CSS?! */
  text-align: center;
  white-space: nowrap;
  vertical-align: middle;
  -ms-touch-action: manipulation;
  touch-action: manipulation;
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 4px;
}
```
Visit: http://getbootstrap.com/css/#buttons inspect one of the buttons and see for yourself:
![image](https://cloud.githubusercontent.com/assets/194400/25717024/190df58a-30f9-11e7-8d14-522a3d3853a1.png "Twitter Bootstrap buttons - click to enlarge")



What a monolith! There's a lot of CSS attributes there;
Bootstrap is quite ***opinionated*** about how a button should
look and function.

What if we wanted a button that looks a little different?
We'd most likely need to add another class. e.g:

```html
<button type="button" class="btn btn-dwyl">do what you love</button>
```
Which requires us to write quite a lot of custom CSS:

```css
.btn-dwyl {
  background-color: #46B6AC;
  border-color: #46B6AC;
  padding: 10px;
  text-transform: uppercase;
  letter-spacing: 4px;
  font-weight: 300;
}
```

![btn-dwyl](https://cloud.githubusercontent.com/assets/14013616/20138059/1501dfb4-a676-11e6-8c74-750b5be89d88.png)

Tachyons approaches this with `single utility classes` (classes that do one thing). Change the `html`, not the `stylesheet`:

```html
<button class="bw0 br2 bg-dwyl-teal pa2 white fw1 tc ttu tracked">do what you love</button>
```

Each class has one responsibility:
+ `bw0` - "border width 0" see:
+ `br2` - "border radius 2" see:
+ `bg-dwyl-teal` - "background color dwyl teal" (_this is an example of a custom color_)
+ `pa2` - "padding all 2"
+ `white` - "text color white"
+ `fw1` - "font weight 1"
+ `tc` - "text align center"
+ `ttu` - "text transform uppercase"
+ `tracked` - "with letter spacing"

see: `/examples/buttons.html`

**Note**: Tachyons does not have _all_-the-colors, hence we had to define our one.
However given that there is a clear format for defining colors
we defined our own as `bg-dwyl-teal`:
```css
.bg-dwyl-teal {
  background-color: #4DB6AC;
}
```
This is "_OK_" because it's still a _single-purpose_ class
which we can re-use for any elements that require the teal background.

### What is "_Functional_" CSS?

![fcss](https://cloud.githubusercontent.com/assets/194400/25713667/64c64ac4-30ed-11e7-8962-86a773923549.png)



You may be thinking:
+ Just how does this make my CSS better?
+ Why use this approach when CSS has been written like the bootstrap example for years?
+ Isn't this just like using inline styles? ([considered by many to be bad practice in CSS](http://stackoverflow.com/questions/2612483/whats-so-bad-about-in-line-css))
+ Won't I end up repeating myself in the html?

Let's have a look at some of the core features and ideas of `Functional CSS` and see if we can answer some of those questions:

## Functional CSS is:

### Functional :innocent:

Small, clear, easy to read classes that are easy to apply and do one thing. Having small classes means it's easy to make a set of consistent spacing and type rules - you end up forcing a beautiful type scale & rhythm on your design.

> "Good design (my preferred school of good design, at least) is mathsy, rational and pure —and CSS is design— so it follows that there are a bunch of lessons we can bring back from FP land into design." - [Jon Gold](http://www.jon.gold/2015/07/functional-css/)

### Composable :musical_score: :notes: :musical_keyboard:

In Functional Programming you combine (or compose) a bunch of tiny functions together to do bigger things (like lots of notes to make music!). You end up reusing a lot of your code which is great for performance and consistency! Just like the button example:

```html
<button class="pa2 br2 bg-green tc tracked"> <!--VS--> <button class="btn btn-dwyl">
```

We'll end up reusing :recycle: nearly all of those classes, whereas the button classes will only be used for buttons.

Be green! Recycle your classes!

![recycle-your-classes](https://cloud.githubusercontent.com/assets/14013616/20142303/10aeccc2-a68c-11e6-98dc-f082242d617d.jpg)

> "Doing one thing extremely well promotes reusability and reduces repetition." - [Adam Morse](https://github.com/tachyons-css/tachyons/)

### Immutable :gem: :gem: :gem:

In Functional languages declaring a property means it will never get overwritten, something known as `Immutability` - i.e It can't ever be changed (or `mutated`). A huge benefit you gain from  immutability is that code is easier to reason about (you don't have to go on a hunt to find where something might have been changed).

CSS on the other hand is inherently mutable (it's the "C" in CSS - the `Cascade`)! But because `fcss` classes are `single responsibility`, they aren't at risk of overriding each other. This almost eliminates the problems of the cascade (Changing a property somewhere won't break your code elsewhere).

Another extremely useful property you gain from immutability is something called **Referential Transparency** : In other words: A thing does exactly what it says on the tin!

We know with a fair amount of confidence what our button will look like just from reading the classes:

```html
<button class="pa2 br2 bg-green tc tracked">
```

but for all we know our `.btn` & `.btn-dwyl` classes could look like:

![questionable](https://cloud.githubusercontent.com/assets/14013616/20143859/88f29ac8-a692-11e6-9980-012d3c5d1738.png)

Yikes! :open_mouth:

And what if we wanted to change it? Do we change our "monolithic" button classes and pray :pray: that they don't break other buttons elsewhere? :boom: On a BIG project?!

![lol](https://media1.giphy.com/media/sjfefACqq2BUc/200_s.gif)

Be realistic, we're likely to add more and more classes to avoid this from happening. This gets more and more wasteful over time, adding bloat to our CSS files:

> In [the monolith] model, you will never stop writing css. Refactoring css is hard and time consuming. Deleting unused css is hard and time consuming. And more often than not - it’s not work people are excited to do. So what happens? People keep writing more and more css - [Adam Morse](http://mrmrs.io/writing/2016/03/24/scalable-css/).


## Why Tachyons?

What else does Tachyons specifically give us?

### Easy to Understand and Use

A great thing about tachyons is how quickly and easily you can get up and running. The classes are easy to understand (once you get used to them), If you know CSS, you know tachyons!

If you find the names too terse you can use the [verbose version](https://github.com/tachyons-css/tachyons-display-verbose).

### Mobile First Responsive Design

By far one of the most useful features is that almost all classes have "responsive suffix" versions:

for example the "padding all 4" class `pa4` also has 3 other versions:

```css
.pa4-ns { ... }
.pa4-m { ... }
.pa4-l { ... }
```

`ns`, `m`, and `l` are short for "not small", "medium" and "large"

Tachyons gives you incredible flexibility to change your design at different screen sizes. And by default the "non suffixed" class **is** the mobile class! This encourages you to design for mobile first and expand outwards. All of this without writing a line of css! Tachyons has the referential transparency of inline styles coupled with the power of media queries!

### A Natural Workflow

Using Tachyon's styles in this way also seems to encourages a more natural workflow when building UIs

> Styles are localized at the HTML template level, rather than being controlled by central CSS files. This fits my workflow because I usually work through a website's design one page at time... - [Jason Li](http://notebook.hongkonggong.com/2016/04/21/is-tachyons-the-right-css-framework-for-me/)

Jason Li illustrates this perfectly:

![tachyonsexplanationnow](https://cloud.githubusercontent.com/assets/14013616/20149576/d5bae650-a6a9-11e6-87b2-dcb65f1dc882.png)

![tachyonsexplanationbefore](https://cloud.githubusercontent.com/assets/14013616/20149566/caf62b80-a6a9-11e6-95a9-f06af3e8413f.png)

### Works well with component based UIs

Using a templating engine or framework (such as `Rails`, `React`, `Elm`, `Angular`) means you can reduce the repetition of classes in your html by reusing them as components.

### Great Performance that Scales

As your project grows larger, your stylesheet doesn't (or only grows very minimally). This has benefits for the user as there's less CSS to download and the browser has to register less styles overall (it can cache the result of already computed styles).

> "Inline styles are 1 to 1 for the browser. i.e an inline style can only style one element at a time. While a class has a 1 to many relationship. This has non-trivial deltas in rendering speed and can greatly reduce jank in a complicated ui." - [Adam Morse](https://github.com/tachyons-css/tachyons/issues/12)

## How?

You can get up and running by just adding a link tag in your html

```html
<link rel="stylesheet" href="https://unpkg.com/tachyons@4.5.4/css/tachyons.min.css">
```

Or grab the latest version

```html
<link rel="stylesheet" href="https://unpkg.com/tachyons/css/tachyons.min.css">
```

If you want to customise the styles you can clone the tachyons repo locally and install the dependencies

```sh
$ git clone https://github.com/tachyons-css/tachyons.git
$ cd tachyons
$ npm install
```

Make the changes that you'd like to the css files and then run

```sh
$ npm run build
```

This will output both an unminified and minified css file to the `/css` directory

Check out [this video](https://vimeo.com/174698456) for a guide to setting up.

### Resources

+ [Tachyons.io](http://tachyons.io/)
+ [Tachyons Table of Styles](http://tachyons.io/docs/table-of-styles/) : http://tachyons.io/docs/table-of-styles/
+ [Tachyons Github Repo](https://github.com/tachyons-css/tachyons/) : https://github.com/tachyons-css/tachyons/
+ [Tachyons Verbose Version](https://github.com/tachyons-css/tachyons-display-verbose) : https://github.com/tachyons-css/tachyons-display-verbose
+ [Setting up Custom Tachyons Build](https://vimeo.com/174698456)

#### Articles

+ [CSS and Scalability](http://mrmrs.io/writing/2016/03/24/scalable-css/)
+ [Functional Programming, CSS, and your Sanity](http://www.jon.gold/2015/07/functional-css/) : http://www.jon.gold/2015/07/functional-css/
+ [Rationalizing Functional CSS](https://marcelosomers.com/writing/rationalizing-functional-css/) : https://marcelosomers.com/writing/rationalizing-functional-css/
+ [Building and Shipping Functional CSS](https://blog.colepeters.com/building-and-shipping-functional-css/) : https://blog.colepeters.com/building-and-shipping-functional-css/
+ [Is Tachyons the right CSS framework for me?](http://notebook.hongkonggong.com/2016/04/21/is-tachyons-the-right-css-framework-for-me/) : http://notebook.hongkonggong.com/2016/04/21/is-tachyons-the-right-css-framework-for-me/
+ [FCSS](http://eng.wealthfront.com/2013/08/20/functional-css-fcss/) : http://eng.wealthfront.com/2013/08/20/functional-css-fcss/

#### Questions and Discussions

+ [How is Tachyons different from inline styles?](https://github.com/tachyons-css/tachyons/issues/12) : https://github.com/tachyons-css/tachyons/issues/12
+ [What's so bad about inline css?](http://stackoverflow.com/questions/2612483/whats-so-bad-about-in-line-css) : http://stackoverflow.com/questions/2612483/whats-so-bad-about-in-line-css

### Future of Tachyons

Watch Adam Morse (_creator of Tachyons_) describe the Future of Tachyons:

[![future-of-tachyons](https://cloud.githubusercontent.com/assets/194400/25709019/085b636c-30e0-11e7-9da4-6bb77a9b33d5.png)](https://youtu.be/XX47atVcVZE?t=1h1m11s "Future of Tachyons Talk @dwyl HQ - Click to Watch!")
https://youtu.be/XX47atVcVZE?t=1h1m11s


### Does My App _Need_ To Be "_Beautiful_" for People to Use it?
