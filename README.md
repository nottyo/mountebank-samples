# mountebank-samples
Example configuration files for [Mountebank](http://www.mbtest.org/)

## Mountebank
> Mountebank is the first open source tool to provide cross-platform, multi-protocol test double over the wire. Simply point your application under test to mountebank instead of the real dependency, and test like you would with traditional stubs and mocks. 

## Install Mountebank
`cmd$ npm install -g mountebank@latest`

## Config Files
You can load your configuration files to Mountebank with an option `--configfile` It supports a set of complex configurations for multiple imposters using [EJS](https://github.com/tj/ejs) templates, which allow you to put contents into separate files and use an EJS include directive to merge the contents into one file.

Personally, I recommend you to use [Atom](http://atom.io/) as an editor for EJS files. I also created Atom snippets for Mountebank which can help you to create your configuration files easier. You can copy the `snippets.cson` file into `~/.atom/` (You'll see an example usage below) Make sure that you've installed the [`language-ejs`](https://atom.io/packages/language-ejs) plugin into your Atom app.

![snippets](https://raw.githubusercontent.com/nottyo/mountebank-samples/master/mountebank_samples.gif "Mountebank Samples")

## Start Mountebank
`cmd$ mb --configfile imposters.ejs --allowInjection`

## How to use snippets
Just copy the `snippets.cson` file into `~/.atom/` directory, then restart Atom.

`cmd$ cp snippets.cson ~/.atom/`

When you want to use snippets, just type the `prefix` text then press `tab` to enable it.

| Prefix       | Description             | Example                                        |
| ------------ | ---------------------   | ---------------------------------------------- |
| imps         | create imposters        | { "imposters": [] }                            |
| imp          | create imposter         | { "port": 1234, "protocol": "http", ... }      |
| incl         | include directive       | <% include path/to/file.ejs %>                 |
| strfy        | stringify directive     | <%- stringify(filename, 'path/to/file.ejs') %> |
| stub         | create single stub pair | { "predicates": [], "responses": [] }          |
| pred         | create predicates       | { "equals": { "method": "POST", ... } }        |
| resp         | create responses        | { "is": { "statusCode": 200, ... }  }          |
| def_res      | default responses       | { "responses": [] }                            |
| behav        | set response behavior   | { "\_behaviors": { "wait": 5000, ... } }        |
| proxy        | set response proxy      | { "proxy": { "to": "http://origin.com", ... } }|
| resp_inj     | set response injection  | function(request, state, logger) { ... }       |
| pred_inj     | set predicates injection| function(request, logger) { ... }              |
