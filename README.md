# POC of a bug after production build using Vite + Vue3

Using the [vue-collapsible-panel](https://github.com/dafcoe/vue-collapsible-panel) library works only in development mode.

### Test 1

> npm run dev

Running the dev environment you will be able to see 2 expandable panels with names, both works good.

### Test 2

> npm run buildDev

Building the application using the buildDev command will generate the dist directory with the bundle, running it with Live Server (or any other http server of your choice) you can see it still working

### Test 3

> npm run build

Building the application using the build command will generate the dist directory with the bundle, running it with Live Server (or any other http server of your choice) you can see that now the panels does not work properly