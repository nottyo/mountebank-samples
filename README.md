# mountebank-samples
Example configuration files for [Mountebank](http://www.mbtest.org/)

## Mountebank
> Mountebank is the first open source tool to provide cross-platform, multi-protocol test double over the wire. Simply point your application under test to mountebank instead of the real dependency, and test like you would with traditional stubs and mocks. 

## Install Mountebank
`cmd$ npm install -g mountebank@latest`

## Config Files
You can load your configuration files to Mountebank with an option `--configfile` It supports a set of complex configurations for multiple imposters using [EJS](https://github.com/tj/ejs) templates, which allow you to put contents into separate files and use an EJS include directive to merge the contents into one file.

Personally, I recommend you to use [Atom](http://atom.io/) as an editor for EJS files. I also created Atom snippets for Mountebank which can help you to create your configuration files easier. You can copy the `snippets.cson` file into `~/.atom/` (You'll see an example usage below) Make sure that you've installed the [language-ejs](https://atom.io/packages/language-ejs) plugin into your Atom app.


