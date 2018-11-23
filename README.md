# Stratos iconic font

Extra Icons:

- GitLab - https://raw.githubusercontent.com/encharm/Font-Awesome-SVG-PNG/master/black/svg/gitlab.svg

License: https://github.com/encharm/Font-Awesome-SVG-PNG#license



This is the iconic font used in the EOS Design System. The official SUSE Linux Design System, and for all open source projects to use and re-use.

To view the EOS Design System project check gitlab https://gitlab.com/SUSE-UIUX/eos

# Installing with npm

`npm install eos-icons --save`

# Using EOS icons in your projects

Just like in any other iconic font, you need to add the Fonts and CSS files in your project:

1- Add the `eos-icons.css` file available under the `dist/css` folder into your projects `<head>`:

`<link rel="stylesheet" href="assets/eos-icons.css">`

2- Make sure the font files available in the `dist/fonts` folder are placed under your `assets/fonts` folder so the .css file can read them correctly.

3- Use the icons in your html as follows:

```
<i class="eos-icons"> LIGATURE_OF_THE_ICON</i>
```

Where the LIGATURE_OF_THE_ICON is the name of the icon. Use our online tool to see the icon's name: https://suse-uiux.gitlab.io/eos-icons/, or simply run `open dist/index.html` to see it locally.

# Adding your icons to the iconic font

If you want to create your own icons and add them to this library, follow the next steps:

### What do you need to build the fonts locally?

This project uses Webfont for Grunt to build. More info about the project: https://www.npmjs.com/package/grunt-webfont

We use Fontforge to render our icons since the quality is better than using plain node, and it supports Ligatures.
Our icons follow Google Material Icons guidelines one-to-one. This is the main reason for us to use ligatures as well. We made a perfectly compatible icon font for those already using MD icons.
If you want to know more about all the standards we follow for the EOS, visit our public wiki, which is our main internal guideline: https://gitlab.com/SUSE-UIUX/eos/wikis/home

### Installing dependencies

- Clone this repository and go to the folder:

```
git clone git@gitlab.com:SUSE-UIUX/eos-icons.git
cd eos-icons
```

- Make sure you have NODE.js installed, if not:

```
brew install node
```

- Install Grunt globally:

```
npm install -g grunt-cli
```

- Install npm dependencies:

```
npm install
```

Install the dependencies:

- OSX

```
brew install ttfautohint fontforge --with-python
```

You will need to have Xcode installed. First install the command line tool:

```
xcode-select --install
```

And then download the latest version from:

https://developer.apple.com/xcode/

- Linux

```
sudo apt-get install fontforge ttfautohint
```

### Design and add your SVG icons

Add your icons into the `svg/` folder. All our icons have been designed with Illustrator, but designing with any tool like Inkscape will work just fine, just make sure the exported SVG code is as clean as possible.

SVG file names with more than one word in it should not have a minus character separating the words (e.g.: some-name.svg), instead, use an underscore (e.g.: some_name.svg). The use of spaces in the filename also creates conflicts in the resulting iconic font.

Then all you need to do, is run

```
grunt
```
This will build the assets under the `dist/` folder.

Open the `index.html` in your browser to easily navigate the iconic font and check the look of the icons in different sizes.

```
open dist/index.html
```

We added the recommended sizes MD icons use: 18, 24, 36, and 48 pixels, plus 16px which is our minimum allowed size at EOS Design System.

**That's it!!.. easy as pie**
