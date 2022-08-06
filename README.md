<h1 align="center">Welcome to Webtori</h1>

Are you tired of centralized databases? Manually updating links? Linear topological structures? Try Webtori!!

![Webtori banner image. It has a big colored torus and the caption “go beyond webrings”.](https://cdn.discordapp.com/attachments/575809098923376650/1005032062111195237/Example_torus.webp "Unlock the torus." )

Webtori is a simple and flexible script to automatically update webring links. It supports up to six directions of page relationships (`prev`, `next`, `above`, `below`, `behind`, and in `front`), allowing for complex topological structures represented by surfaces in up to four dimensions. For example, the humble torus can be accomplished with a collection of left-right webrings and up-down webrings linked together. More complex structures are yet possible:

<p align="center"><img alt="The view from inside a 3-torus. It is like a room covered in mirrors." title="What is this?" src="https://upload.wikimedia.org/wikipedia/commons/d/db/3-Manifold_3-Torus.png" width="auto" height="auto"></p>

## Installation
To install, copy the [webtori.js](https://github.com/vqbc/webtori/blob/main/webtori.js) file to your root directory, and add a GitHub Action (or its equivalent with tools like Heroku CI) with the script in [main.yaml](https://github.com/vqbc/webtori/blob/main/main.yml). If you’d like, you can also add the axios and cheerio modules to your package.json file as dependencies, which makes installing them in the script automatic (so you can delete two lines of code):
```js
{
   // other stuff
  "dependencies": {
    // other dependencies
    "axios": "^0.27.2",
    "cheerio": "^1.0.0-rc.12",
    // ...
  },
  // ...
}
  ```

Then have all sites in the webring add ID's `wr-link-prev`, `wr-link-next`, etc. to the `<a>` links of the webring. This will allow each site to automatically scrape and update their own links accordingly. Enjoy!
