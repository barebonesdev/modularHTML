# ModularHTML

Forked from [jeroentvb](https://github.com/jeroentvb/modularHTML), all credit to them!

This forked version is different in that it...

* Removes the "Must link to .html" requirement (assumes you'll be hosting site on a server that will resolve those)


This project uses ejs to allow building a static website from modular ejs (HTML) files.  
It's using ejs because you won't need to learn a new language, only a few new tags.  
More info on ejs [here](https://ejs.co/)

## Installation
Install using the following commands
```
git clone https://github.com/jeroentvb/modularHTML.git
cd modularhtml
npm install
```

## Usage
Build your website in the [src](src/) folder. The page templates should go in [src/pages](src/pages). The partials, such as the head and tail, should go in [src/partials](src/partials).

### Development
To develop the website, this app uses a simple [express](https://www.npmjs.com/package/express) server. You can run the server using `npm start`.  

#### Linking
Unlike the original repo, you can link by `/platforms` rather than `/platforms.html`... just make sure you host your static files on a server that resolves those.

#### CSS preprocessor
You can use your own css preprocessor if you so desire. Just make sure changes in your source file are being watched and compiled a css file and make sure it's linked in [head.ejs](src/partials/head.ejs). Otherwise changes won't show up or be included in the compiled website.  
CSS is minified on build.

#### JS minify/transpile
You can use your own js transpiler if you so desire. Just make sure it's compiled and linked in [tail.ejs](src/partials/tail.ejs) before compiling the website.  
JS is minified on build.

### New page
To create a new page use `npm run newpage pagename`. Where `pagename` would be the name of your page. This creates a new template with the head and tail already linked.

### Build the website
If you are done you can build the website using `npm run build`. This will copy the assets folder to a newly created `public` folder. It also compiles the ejs templates and creates an html file in the `public folder`.
