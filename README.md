#react-component-publish

A barebones boilerplate to quickly publish react components.  

Features Webpack 4 and Babel 7.

It will compile down to commonjs, and will require a peer dependancy of react, meaning it will use whatever version of react the host project is using.  Hopefully this will minimize compatibility issues.

[based on this tutorial.](https://medium.com/quick-code/publish-your-own-react-component-as-npm-package-under-5-minutes-8a47f0cb92b9)

#To start

```
npm i
npm start
```
Edit `src/index.js` (your component)

#To test your component in another project, without publishing to npm:

build this project:
```
npm run build
```
in this project's root directory, type:
```
npm link
```
And then, in the project (root dir) you would like to use your component:
```
npm link my-awesome-component
```
For this example I've used the package name `my-awesome-component`.
This creates a symlink of your package in your project's node_modules/ dir.
Now, you may import the component in your test project, as if it was a normally installed dependancy:
```
import MyAwesomeComponent from 'my-awesome-component'
```
If you're using a hot-reload system, you should be able to observe any changes you make to your component (as long as you build them)

#To publish your component to npm
Update the package.json with correct information.
Important things to set:

```json
{
  "name": "cool-beans",
  "version": "4.2.0",
  "description": "My wizzbang gizmo",
  "author": "stevejobs",
  "license": "ISC",
}
```

if you have a git repo for the project, include the details:

```json
"repository": {
    "type" : "git",
    "url" : "https://github.com/zxol/react-component-publish"
  },
```

then, in the root directory, type:

```
npm publish
```

[npm docs on publishing packages](https://docs.npmjs.com/packages-and-modules/contributing-packages-to-the-registry)
