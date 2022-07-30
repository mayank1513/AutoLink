# AutoLink
A thin wrapper to RouterLink component to automatically handle internal and external links.

Please read [this article](https://medium.com/js-dojo/extending-vue-router-links-in-vue-3-8c7d93eb20bc) to learn how to build this package step by step and the background story.

To learn vue js please check out our courses [Vue.js Complete Course + Guide](https://www.udemy.com/course/vuejs-complete-course-plus-guide/?referralCode=93BDA4A1FE3F73C37CD2) and [Vue 3 Essentials](https://www.udemy.com/course/vue-3-essentials/?referralCode=E6D2FDE2B8B06C1991F1)

Follow us on [FaceBook](https://www.facebook.com/Learn-Vue-Js-104953725168718/) to get the latest discount coupons and update to our articles and packages.

> To keep it thin and performant we have chosen to provide only the minified version. Because, that's what you really need. In case you are looking for the full version build your own from this source code as per [Build](#Build) section.

## Install
```
pnpm install @mayank1513/auto-link --production
```
If you don't have pnpm installed use `npm install @mayank1513/auto-link --production`

Add dependency in package.json 
```
    "@mayank1513/auto-link": "^0.0.3"
```
## Usage
Use `AutoLink` in same way you would use `RouterLink`. You can provide some additional parameters as described in [Styling](#Styling) and [Target](#Target) section.

You do not need to handle internal and external links separately. You can just use AutoLink for all links. Just make sure you use https:// or http:// for external links.

```
<template>
  <ul id="nav">
    <li v-for="(link, title) in links" :key="link">
      <auto-link :to="link">{{ title }}</auto-link>
    </li>
  </ul>
  <router-view />
</template>

<script>
import AutoLink from '@mayank1513/auto-link'

export default {
  name: "App",
  data() {
    return {
      links: {
        Home: "/", // internal link
        About: "/about", // internal link
        Blogs: "https://mayank1513.medium.com", // external link
        "Vue Crash Course + Guide":
          "https://www.udemy.com/course/vuejs-complete-course-plus-guide/?referralCode=93BDA4A1FE3F73C37CD2", // external link
        "Vue 3 Essentials":
          "https://www.udemy.com/course/vue-3-essentials/?referralCode=E6D2FDE2B8B06C1991F1", // external link
      },
    };
  },
  components: {
    AutoLink,
  },
};
</script>
```

### Styling
To style external links differently you can provide `externalLinkClass` as additional attribute.
```
<auto-link :to="link" external-link-class="your-css-classname-here">{{ title }}</auto-link>
```
You can also style `a` tag as AutoLink component uses `a` tag to render external links.
> Make sure you take care of CSS cascading rules (e.g. use !important)

### Target
By default external links are opened in new tab. If you want to override this behaviour please set `target="_self"`

## Build
To build the example clone the repo `git clone https://github.com/mayank1513/AutoLink.git` and run

```
npm i && npm run build
// or
pnpm i && npm run build 
```
## Help us to help you more
- Please start this repo
- Follow us on [FaceBook](https://www.facebook.com/Learn-Vue-Js-104953725168718/)
- Upvote our helpful posts on [StackOverflow](https://stackoverflow.com/users/story/9640177)
- Refer our courses to your colleagues, friends and business leaders
  - [Vue.js Complete Course + Guide](https://www.udemy.com/course/vuejs-complete-course-plus-guide/?referralCode=93BDA4A1FE3F73C37CD2)
  - [Vue 3 Essentials](https://www.udemy.com/course/vue-3-essentials/?referralCode=E6D2FDE2B8B06C1991F1)
- Use our referrals to get advantage of special offers
  - Learn [organic marketing](https://leads-arc.web.app/) 
  - Open your free demat account with [Groww](https://groww.app.link/refe/mayank-kumar8914309)
  - Open your demat account with leading discount broker [Zerodha](https://zerodha.com/?c=GG0215&s=CONSOLE)
  - Buy what you need on [amzon.in](https://www.amazon.in/ref=assoc_aax_fallback_300x250?tag=mayank1513-21&linkCode=ur8) using [our refferal](https://www.amazon.in/ref=assoc_aax_fallback_300x250?tag=mayank1513-21&linkCode=ur8)
  - Buy what you need on [amazon.com](https://amzn.to/3i2PPsE)
  - Donate for social cause. We are happy if you help anyone in need. It need not be only us!
- Want to learn business skills? Checkout [Bada Business](https://www.badabusiness.com/dd/BIMK003866)

## Contribute for a Cause
- [PM Cares Fund](https://www.pmcares.gov.in/en/)
- [#IamOxygenMan](https://www.badabusiness.com/IamOxygenMan)


