# desk-twitter
A one-person twitter application inspired by the US former president Donald J. Trump's [From the desk of Donald J. Trump](https://www.donaldjtrump.com/desk) APP. This project is powered by ViteJS and VueJS.

单机版推特，一个人的微博，唐纳德·J·特朗普的 [办公桌](https://www.donaldjtrump.com/desk) 应用，你值得拥有。本项目是用ViteJS和VueJS写的。

[live demo](https://www.houzhenni.com/desk)

The live demo is made with Nuxt.js, but the Vue file is mostly the same. Vite is really super blazing fast on dev speed, when your Vite app is ready for live changes, Nuxt is still building dev environment. After you finished the Vue file in Vite, you only need to do some minor changes for migration to Nuxt app.

此线上演示版本使用 Nuxt.js 制作，但是使用的 Vue 组件文件的内容基本是一样的。Vite在构建开发环境上确实十分特别以及及其地快，Nuxt 还在读进度条的时候 Vite 都已经可以上手操作了。先在 Vite 应用里写好 Vue 文件，然后移植过去 Nuxt 使用即可。

[How to use](#How-to-use)

[如何使用](#如何使用)

# How to use

First fork the repo and clone it to your computer.

```
git clone https://github.com/<your github id>/desk-twitter
```

Then install dependencies

```
npm install
```

Run dev mode

```
npm run dev
```

Go to dev server `localhost:3000` and view your project.

Go to folder `desk-content/` and input your thoughts in the `posts.yml`, please make sure you follow the formats. Refresh the page and you will see the page is updated.

# 如何使用

先 Fork 本项目，然后下载到你的电脑上

```
git clone https://github.com/<your github id>/desk-twitter
```

安装依赖

```
npm install
```

运行开发模式

```
npm run dev
```

浏览器打开 `localhost:3000` 就可以看到结果了。

进入文件夹 `desk-content/` 并修改文件 `posts.yml`, 填写时请注意格式。 刷新网页即可见到更新后的内容。
