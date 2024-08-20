# clojurescript-tutorial

In this tutorial:

    Create a project using shadow-cljs.
    Manage npm and ClojureScript dependencies.
    Set up a live coding workflow for faster and easier development.
    Separate the View from the Interaction when building a UI.

What is ClojureScript?

ClojureScript is a version of Clojure that compiles to JavaScript. ClojureScript can run in the browser, on Node.js, on Electron, or in mobile apps via React Native. ClojureScript gives you the power of Clojure to exploit the JavaScript library ecosystem.

People use ClojureScript to build:

    Single Page Web Applications using React
    Web servers using Node.js
    Desktop apps via Electron
    Mobile apps via React Native
    Serverless Functions (such as AWS Lambda)

In addition, many companies use ClojureScript as a frontend to their Clojure backend. They can share code and data structures between Clojure and ClojureScript.

Then, create the project. I have named it counter-app because I will make a demo counter application in this tutorial:

npx create-cljs-project counter-app

That will list:

    node_modules - where npm keeps the installed npm libraries
    package.json - lists the npm libraries to install
    package-lock.json - also used by npm
    shadow-cljs.edn - the shadow-cljs project configuration file
    src/ - where ClojureScript source code goes

Below src/ are two more directories:

    main - where your application code goes
    test - where your test code goes

Test your project by running a browser REPL

npx shadow-cljs browser-repl

(js/alert "Hello!")

Production builds should be slim so that the client has less to download. They can happen over the entire program and slowly because it's only done once just before release.

First, lets kill the shadow-cljs watcher. Then, we do a release build with this command:

npx shadow-cljs release app

After building the release asset, we can run a server like this:

npx shadow-cljs server app

If you're ready to deploy to production, you can include public/index.html and public/app/js/main.js.

Conclusion

In this tutorial we've set up shadow-cljs, configured it for a live coding workflow, and set to work building a simple app. We refactored the app a bit and then built a release version of the app for production. Pretty handy work!
