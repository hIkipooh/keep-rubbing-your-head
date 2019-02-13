## 1. About

This was made during my time at Code Chrysalis. Keep Rubbing Your Head is notetaking / brainstorming application designed for users with experience in using Mac OS terminal.

## 2. Features

In the application, the only input field is located at the terminal line styled interface in the center bottom of the application. Directories are roughly translated to paragraph and files to sentence. However, user can only input text via files. In its default state user will begin in Users/ directory. From there user can make, delete, move around directories. Following are the commands that can be used:

### a) cd

Just like in the terminal cd is the command used for changing directories.

```
cd <directory/you/wish/to/go/to>
```

### b) mkdir

Makes a paragraph in the directory.

```
mkdir <paragraphName>
```

### c) touch

Makes a sentence in the directory.

```
touch
```

## 3. Set up

## Project setup

Please fork the repository and clone the forked repo.
Yarn is our recommended package manager.
Install yarn through

```
yarn install
```

If you do not have Vue installed globally please follow below step to allow Vue CLI

```
yarn global add @vue/cli
```

### Compiles and hot-reloads for development

```
yarn run serve
```

### Compiles and minifies for production

```
yarn run build
```

### Run your tests

```
yarn run test
```

### Lints and fixes files

```
yarn run lint
```

## 4) Contributions

All contributions are welcomed. Please feel free to fork and clone and test it out. As it is in very early stage of development, any input would be greatly appreciated.

Currently, the work in focus is the cd, which can get into directory but not move back out.

For other commands, it would be greatly appreciated if any contribution can be made on touch, mkdir and remove.
