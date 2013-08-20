## It's Dangerous to Go Alone. Take This!
#### Some things you will need with you on this journey are:
*   A code editor of your choice (we recommend Sublime Text 2+)
*   A decent knowledge of HTML/CSS
*   A willingness to learn
*   [Google](https://google.com) or comparable search engine.

#### Some optional things that we recommend include:
*   A web server (Apache or similar)
*   Some knowledge in programming (variables, functions)
*   General knowledge of the terminal

#### Things that are **NOT** required are:
*   Any specific web framework such as Rails, Codeigniter, etc.

##[Some Options with Gumby](id:options)
You have several options when working with Gumby. We'll walk you through how we would use it but this isn't a definitive guide on how fit Gumby into your workflow.

###GUI's
There are several GUI's out there that take the fear/mystery/fun out of using the terminal. Some of these include, Scout App(Cross Platform), Codekit(OSX), and Compass.app.

###Vanilla CSS
You don't need to use Sass[^1] if you're all about retro things and living in the past. The world needs historians after all! But you're free to use Gumby as an add-on to your project. Link it in and off you go! You can even customize Gumby to only include the grid or typography if that's what you need. Gumby is as flexible as you need it to be.

###Terminal (It's not scary!)
The preferred option around these parts is to use the terminal and compile our CSS that way. It can be much easier than most people think and with a few basic commands, you can be right at home in the terminal.

## Installing Ruby
While it's [not entirely necessary](#options) to have Ruby and use Sass with Gumby, it is highly suggested. Sass has become an invaluable tool to not only us, but many other developers all over the world. Don't take our word for it though. Check out the [Sass website](http://sass-lang.com/) to learn more.

Anyways, assuming you're still with us you'll need to install Ruby. I'll break the next section up by operating systems for ease of use. If you have Ruby >1.8.7 installed already, go ahead and skip to the next steps of [installing the gems](#gems).

### Mac
Using [Brew](http://mxcl.github.io/homebrew/)[^2] or your package manager of choice, install RVM, Ruby Version Manager.

```
# install with brew package manager
$ brew install rvm
# or install with Ruby
$ \curl -L https://get.rvm.io | bash -s stable --ruby
```

Then go into terminal and run `ruby -v`. If it returns something along the lines of `ruby 1.9.2p312 (2012-01-16 revision 34318) [x86_64-darwin11.2.0]` you're in the clear! Anything greater than 1.8.7 is ideal. One last step is to run: `rvm use <version> --default`
to ensure that your gems and Ruby version will be the same every time.

You can also utilize a tool called [Jewelery Box](http://jewelrybox.unfiniti.com/). Though it requires you be on 10.7+. And be using 

**Make sure you input the proper version you installed in <version> above.**

### PC
We recommend heading over to [RubyInstaller](http://rubyinstaller.org/)'s website to get Ruby setup on your machine. Download an installer and run it. That's it! To double check that everything is all set up, open up Command Prompt and run `ruby -v`. If it returns something along the lines of `ruby 1.9.2p312` you're set!

### Linux
For you Linux folk, there's a few options here. You can use [RVM](https://rvm.io/), apt-get or just build it from source. Because, you know, you can do those things. In terminal run: `$ \curl -L https://get.rvm.io | bash -s stable`. This will download, build, and install the latest Ruby version for your machine. Then run: `ruby -v`. If it returns something along the lines of `ruby 1.9.2p312 (2012-01-16 revision 34318)` you're good! Anything greater than 1.8.7 ideal. One last step is to run:`rvm use <version>; --default`to ensure that your gems and Ruby version will be the same every time.

**Make sure you input the proper version you installed in <version> above.**

## [Installing Gem Dependencies](id:gems)
Gumby relies on some friends to make the magic happen. Gumby utilizes modular-scale, Compass and Sass specifically. You can read up on them if you would like. I'll wait here.

To install these gems you'll need to run:
`$ gem install compass modular-scale sass`

Let that do it's thing and you should be all set. 

## Compiling Gumby for the First Time
Now that you have a proper home environment for Gumby and your creations to blossom, let's compile the Sass out. We recommend that you utilize an [external scss file](#partials) to add your Sass to and not edit the gumby.css file.

You'll want to move into your working directory. Let's assume we're working out of the directory `/project`

Our project folders include a `public_html` folder inside it. That's where Gumby should live. You should be in `/project/public_html/` now. Here's where the magic of Compass and Sass happens: Run `compass compile`.

Boom. If there was a change in the SCSS, the is CSS compiled out to the `/css` directory. Wasn't that easy?

But wait, there's more! If you type `compass watch` into the terminal in the next 10 minutes, Compass will watch your Sass files for any changes and automagically compile your Sass out to CSS. There really isn't a time limit on this deal but with the `compass watch` command running, you're free to edit your SCSS and have it compiled as soon as you save.

#### But why not use regular Sass?
This is a common question to newer users to Sass. Why use Compass? As we explained before, Compass provides numerous mixins and features to the Sass language that makes it an indispensable tool. [Read more](#sass)

## Writing Your First Sassy Sass
Look at you. You've come all this way. They grow up so fast. Anyways, now that you're better than everyone else, go ahead and open up your _custom.scss. In here is where you'll keep all your custom Sass stuff. Gumby automatically includes this upon compilation. Convenient!

With your code editor in hand, it's time to get our hands dirty.

Sass has numerous features that we could talk about for days, but here's an extremely basic tutorial on writing your first Sass. In _custom.scss let's create a variable called "color" and how about we give it a soup related color. Mmm soup.

```
$color: bisque;

body{background: $color;}
```

Now, in terminal you'll need to run `compass watch` in order for the Sass to be compiled. You should see that there was a change to a file and that gumby.css was overwritten. Leave that terminal window open and everything you do in your Sass files will be compiled shortly after each save. It's also worth noting that if you mess up and make a syntax error of some sort, Sass will let you know which line and where the infraction took place. Now if you look at your gumby.css file, way down at the bottom you should see that the CSS was outputted. Then, back in your browser you should see that the body is now deliciously colored. Success!

### [Partially Partial Partials, Partialing](id:partials)
In an effort to keep your code more organized, we suggest you use partials when styling your site. We currently have that single _custom.scss partial file in the framework, but you can create as many as you need.


## Best Practices
Here are some tips that we've compiled while using our own framework and listening to other users.

###[Learn, Love, Live Sass](id:sass)
We can't stress enough how awesome Sass really is. It speeds up our workflow, makes updating things like colors super simple, and so many other things. If you aren't 100% comfortable with it, read the [tutorial](http://sass-lang.com/tutorial.html), everything on [The Sass Way](http://thesassway.com/), and [Sass Official Docs](http://sass-lang.com/docs/yardoc/file.SASS_REFERENCE.html). Sass has proved extremely valuable to our team and we're sure it'll be a perfect fit for yours.

### Use the provided _custom.scss partial
Gumby allows you to build right into the framework with the custom partial. We recommend you utilize this function.

### Don't change the gumby.css on your own
While it's [not required](#options), it is always suggested that you use the _custom.scss partial included with the framework. You can always make more and have them included in the gumby.scss file.

###Keep it DRY
You can still take your laptop whitewater rafting, but we suggest following the DRY principle of Don't Repeat Yourself. Creating mixins and using variables to simplify your CSS is definitely something you should practice. But at the same time, don't abuse Sass' functionality. There's a healthy balance you should try to achieve.

###Bower.
We included [Bower](http://bower.io/) in Gumby v2 to make your life and lives of developers everywhere simpler. Bower is a package manager that allows you stay up to date with frameworks and the like. Running `bower update` while in the folder where bower.json is will pull in the latest Gumby files from Github.

###Stay active in our community!
Our [Google+ community](https://plus.google.com/communities/108760896951473344451) could always use some friendly faces. Similarly…

###Add Features to Gumby
Want to really make your parents proud? If in the course of your project, you create a really cool add-on for Gumby, send us a pull request. We'd love to add your work to our framework. Who knows, maybe we'll print it out and put it on our fridge!

* * *
## Help! I'm Stuck!
Hopefully you won't run into any issues getting setup with Ruby, Compass and friends. But it's quite possible you did. For starters, [Google](https://google.com) your problem. Chances are hundreds if not thousands of other people have already as well. Stackoverflow.com is a great place for asking questions and getting answers.

### Can't find modular-scale gem
```
Syntax error: File to import not found or unreadable: modular-scale.
              Load path: /Users/gumbycss/sources/Gumby/sass
        on line 19 of gumby.scss
  Use --trace for backtrace.
```

A common issue for new users. Often times this is caused by using the `sass` command rather than the `compass compile` command.

Also, if you were so advanced that you skipped the steps to install the necessary gems, go back up a few paragraphs.

### I can't get Ruby to work.
RVM is a great tool but also a fickle beast. If you're getting any specific errors try pasting the human readable parts into Google. You're bound to find the answer there.

### My Google Fonts aren't loading
This usually happens when you are attempting to develop from your desktop and opening an HTML file instead of setting up a local http server, like Apache2. Simply put your browser can't load these fonts because they are from a different origin. Check out [Bitnami's free XAMP stacks](http://bitnami.com/stacks/infrastructure) to get started on a web server.

### My problem still isn't solved.
First step should always be to Google your error or problem. If that doesn't work, post to our [Google+ community](https://plus.google.com/communities/108760896951473344451). It's specifically set up for users issues and questions. Please try to keep the Github issues page for framework issues only.


[^1]: Sass is a meta-language on top of CSS that’s used to describe the style of a document cleanly and structurally, with more power than flat CSS allows. Sass both provides a simpler, more elegant syntax for CSS and implements various features that are useful for creating manageable stylesheets. The power of Sass lets you use Gumby the way you want, and the way that best fits the needs and requirements of your project. Gumby 2 uses the SCSS syntax to give you more control over your project than ever before. Check out the [Sass website](http://sass-lang.com/) to learn more.

[^2]: Brew is a package manager for Mac.