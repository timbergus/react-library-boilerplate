# Library Builder Base Project

This project creates a library for React components.

## Scripts

* __clean:__ This script deletes the __dist__ folder. This folder contains the files needed for the library, that will be published, and will be created each time.
* __start:__ This script launch a tool called [Styleguidist](https://github.com/styleguidist/react-styleguidist) that creates a component catalog. This catalog is the main development tool for a component library.
* __start:in-app:__ This script allow us to develop components that needs from the main app to be displayed. This script copies the __src__ folder inside the __node_modules/<lib_name>__ and reload the main application to see the result.
* __test:__ This script launch the tests for the application: JavaScript linter, Sass linter and Jest test and coverage.
* __test:watch:__ This script is only to create Jest's tests. It opens the Jest's watch mode and allow you to work with Jest's test tools.
* __build:__ This is the script to build the library distribution.
* __build:styleguide:__ This is the script to build the catalog of the app in case it is a component library. This catalog can be published as an autonomous webpage to be consulted.

## File and Folder Structure

* __\_\_tests\_\_:__ This folder contains all the tests for the library.
* __config:__ This folder contains the configuration files for the library.
  * __modules.js:__ These are the folder inside the __rsc__ folder that will be used to build the library.
* __src:__ This folder contains all the source code for the library.

The rest of the files out of this folders are configuration files for the development environment of the library.

## How to

### Developing

To develop a component library, we just need to run `npm start`. This will launch the component catalog at [localhost:3100](http://localhost:3100). All the components must be autonomous from the main application.

To develop a big functionality that depends on the main application, we need to use `npm run start:in-app`. We need the main app running to, and we will visit the main app url to see the changes in our module.

### Building

To build the final package, we just need to execute `npm run build`. This build script will always pass all the test before building. If something fails, there will be no building process.

### Publishing

To publish the new library in Nexus, execute `npm publish`. This scripts executes `prepublish` that builds the library. Test are passed too, so if there are errors, the package won't be build, neither published.

This will be a normal npm package, so we are going to import functions or components from the package as it is. To gain this functionality, all the components or functions that the package will expose must be imported and exported inside `src/index.js`.

## Documentation

The __README.md__ is for the library. The instructions live in this __HOWTO.md__. The readme needs a description of the library and all the information needed to understand the functionality of the library.

At the end of the document can exist a table (already mocked), with a list of exports and descriptions to let the people know what they can use from the library and how to use it. If we are handling a component library, the components will be already exposed in the catalog, so we only need to put everything else that does not appear in the catalog, for example, constants or functions.

## Useful Tools

* [dotenv](https://github.com/motdotla/dotenv): tool to use a __.env__ file to store environment variables to emulate the server.
* [npm-check](https://github.com/dylang/npm-check): to update interactively our projects dependencies.
* [semantic-release](https://github.com/semantic-release/semantic-release): a tool to automatic versioning the application using the structure of the commit message.

## Useful Links

[Badges](https://shields.io)
[Why are you still using Yarn in 2018?](https://iamturns.com/yarn-vs-npm-2018/)
[Releases with semantic-release](https://egghead.io/lessons/javascript-automating-releases-with-semantic-release)
[Introduction to semantic-release](https://blog.greenkeeper.io/introduction-to-semantic-release-33f73b117c8)
