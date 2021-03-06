## What is this?

This project shows how you could use [webpack's css-modules](https://github.com/webpack/css-loader) in Elm's development. This is an alternative approach as compared to [elm-css](https://github.com/rtfeldman/elm-css), which is a more functional and pure approach towards declaring component styles.

This is not meant to be set-in-stone truth, but rather a proof-of-concept. Try it and adapt it to your needs!

## Benefits of this approach

- CSS Modules: Dynamically generated locally scoped namespaces for classes. 100% compatibility with doing animations / pseudo selectors and media queries, anything you could do with css. Use all the tooling developed on top of CSS like autoprefixer.

- Interop with existing projects: Projects using webpack + css modules could easily port all styles into Elm using this approach.


## How?

CSS modules get loaded into Elm via [ports and subscriptions](http://guide.elm-lang.org/interop/javascript.html). See [fetchClasses and receiveClasses](/src/Class.elm) and example usage in [Login.elm](/src/Login.elm). Webpack receives commands from elm and loads the css modules [here](/src/index.js). This goes through the Elm Architecture in the application and the css modules will eventually reach the component that needs it.

## Requirements

- Node 6.x.x

- Elm 0.17.0


## Installation

1. `elm package install`

2. `npm install`


## Development

- `npm start`
