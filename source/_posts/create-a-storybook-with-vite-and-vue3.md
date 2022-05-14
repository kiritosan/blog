---
title: create a storybook with vite and vue3
date: 2022-05-14 22:42:05
tags:
---

## steps

### First

First, we need to create a vue3 project with vite, only in this way can we use `sb init` to install storybook

``` bash
pnpm create vite
# after run this command, choose vue
```

### Second

Second, we need to delete some needless files in vue project(because we don't actually dev and build this by vite, actually we use storybook's vite builder to build it)

```
rm index.html ts* v*

rm -rf public src
```

Delete config files because we dont't need to dev and build it by project's vite. we use storybook's vite builder to build, and we use `.storybook`(this is storybook's config folder and it is hidden in project's root directory) as a configuration.

Delete files like App.vue, main.js, public file folder which created for dev and build an app, because we don't wan't to build an app, instead we we want to create components which should dev and build by storybook's vite builder.

Delete src folder(without src, `stories` folder will created at root directory; if src exists, it will be created at src folder).


Now, we only have package.json README.md in our projcet.

### Third

Third, execute the follow command to init storybook which use vite builder

```bash
# choose vite builder is critical
pnpx sb init --builder @storybook/builder-vite

# the command above will download packages for us so we don't need to run pnpm install, but the packages is not installed by pnpm, so after we run pnpm to install some package, the pnpm will move the packages installed by other package manager to .ignored folder in node_modules and install these packages itself.
```

Because we deleted src folder, so we get a stories foler at root directory and a .storybook folder(this is configuration of stroybook) surely at root directory.

Now we can run the follow command to start a storybook service.

```
pnpm storybook
```

OK, now the steps actually completed, but we can also change name to let the project more sementic.

### Addition

1. Change the stories folder's name to components and also change the configuration of storybook by edit main.js in .storybook folder.

```bash
mv stories components
```

```bash
vi .storybook/main.js
# open main.js and change the path to what to changed.
# change stories to components
```

Now we have components folder which we can write componets in here.
But in this components folder we find there are some chaos beacuse each component and each component's story mixed together and all in on foler.

So we can make folders for each component and it's stories(also other files related)

!!mention that after change the configuration in .storybook folder, we need to restart service to let it work.

