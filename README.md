# CSSEmbed

Available here, on [GitHub](https://github.com/scribenet/ScribeCssEmbedLibrary), and [Packagist](https://packagist.org/packages/scribe/cssembed-library)--and consumable by anything that understand a `composer.json` file.

## So, What is It?

CSSEmbed is a small Java library used to automate embedding of data URIs within CSS files.

### Everyone Needs to Stop Forking!

Yes, I can almost hear the incoherent ramblings of another open-source blogger as he slowly types out his depressing articles about the bleak future of open source--*and it's all because of forking!*

> "This recent fork of yours represents the uphill struggle of open source projects and their community.

"Why? If I may ask?"

> Todays programmers simply don't contribute to the original author's work anymore! Instead, they fork the project for their own benefit and within a short time, inevitably fall into a never-ending state of working in parallel with the original project--continually engineering the same core logic--but as two, independent groups. 
> Simply, such behavior doesn't benefit you, the original author, or the open source community."
> **-Unnamed Open Source Blogger**

### Sorry, But I Just Want Dependencies To Work

This is a direct fork of [nzakas/cssembed](https://github.com/nzakas/cssembed), a project which has not been touched by its author for over three years. It has been built and packaged per the most recent prior release, and registered with [Packagist](https://packagist.org/) so [Composer](https://getcomposer.org/) can call the dependency directly without me having to much about with horrible scripted workarounds.

As for the continued future of this project, I don't plan to contribute any new features in the near future, but ff you encounter any issues and are unable to contact the previous author, feel free to log them in [this repositories bug-tracker](https://github.com/scribenet/ScribeCssEmbedLibrary/issues)--I'll be sure to get back to you in a timely manner. Furthermore, if any new code is release [upstream](https://github.com/nzakas/cssembed) I plan to keep this repository current.

On the flip side, if you like getting your hands dirty, pull requests are graciously accepted as well.

### Well Then, Who Are You?

You can call me Rob--likely because that's my name. If you're the curious type, I'm sure my [GitHub handle](https://github.com/robfrawley) provides all the information you need on your way to pillaging my identity and credit (go ahead, [Google me](http://google.com/?q=rob+frawley+2nd) if you're looking for an unrewarding search). 

When I am not writing long-winded and meaningless [READMEs](https://github.com/nzakas/cssembed/blob/master/README.md), I'm employed as a Software Architect for [Scribe Inc](http://scribenet.com/), a company working to further publishing services and related technologies at-pace with the continually evolving trends and growing consumption devices and ecosystems.

I contribute to a range of projects scattered in different "tubes of the Internet" but am most recently proud to share the [wide array of code](http://scribenet.github.io/) the systems team at Scribe Inc has been able to open source this past year. 

## Enough Already; How Do I <insert-verb-here>

If you'd like to be able to use this binary within your [Symfony](http://symfony.com/) or other Composer-based project, it's dead simple. First, add the dependency to the `require` or `requireDev` section of your `composer.json` file: 

```json
{
	"require": {
        "scribe/cssembed-library": "~0.4"
	}
}
```

Lastly, and update your vendor packages:

```bash
php bin/composer.phar update
```

After composer has completed calculating and updating your project dependencies, a new executable will be available within your configured composer `bin` folder. For example, within a Symfony `~2.4` project, the executable is located `/at/your/project/root/bin/scribe-cssembed`.

### Assetic Filter Configuration

If you use [Assetic](https://github.com/kriswallsmith/assetic) for asset management with its corresponding [AsseticBundle](https://github.com/symfony/AsseticBundle) integration within the [Symfony](https://github.com/symfony/symfony) framework, you can easily create an "asset filter" using the `cssembed` jar file. 

Within your Symfony project, locate your configuration file (generally located `/at/your/project/root/app/config/config.yml`) and locate the `assetic` section. Within this section you can define filters that can be applied to any assets managed through Assetic. Here is a short snippet of the Symfony Assetic configuration to get you started:

```json
assetic:
  filters:
    cssembed:
      jar: '%kernel.root_dir%/../vendor/scribe/cssembed-library/dist/cssembed.jar'
```

For detailed information on available configuration options and more usage example, visit the [Assetic](https://github.com/kriswallsmith/assetic) and [AsseticBundle](https://github.com/symfony/AsseticBundle) pages.

## License

### The MIT License (MIT)

**Copyright (c) 2014 Scribe Inc. <opencode@scribenet.com>**
**Copyright (c) 2009 Nicholas C. Zakas.**

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.