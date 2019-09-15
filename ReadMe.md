<link rel="stylesheet" href="./dist/css/wulechuan-styles-for-html-via-markdown--vscode.default.min.css">

# Wulechuan's HTML Article Themes


## Multilingual Editions of this Article

- [简体中文版文档](./ReadMe.zh-hans-CN.md)




## NPM Page

<dl>
<dt>Package Name</dt>
<dd>

[@wulechuan/css-stylus-markdown-themes](https://www.npmjs.com/package/@wulechuan/css-stylus-markdown-themes)

</dd>
<dt>Author</dt>
<dd><p>wulechuan (南昌吴乐川)</p></dd>
</dl>



## Documentation Chapters

> These links lead to a different page each.

- [Introduction](./docs/refs/en-US/introduction.md)
- [How does this Tool Work](./docs/refs/en-US/how-does-this-tool-work.md)
- [Application Examples](./docs/refs/en-US/application-examples.md)
- [Supported Scenarios so far](./docs/refs/en-US/supported-scenarios.md)
- [Develope CSS for a New Theme](./docs/refs/en-US/develope-css-for-a-new-theme.md)




## A Visual Example

A picture paints a thousand words.

The pictures below showcase how does an article look and feel as the default css generated by this tool is applied to the article.

> These 2 pictures are huge (file sizes in mega bytes).


- [en-US-example-in-a-wide-window-toc-collapsed.png](./docs/examples/rendered/snapshots/en-US-example-in-a-wide-window-toc-collapsed.png)

- [zh-Hans-CN-1-大尺寸浏览器中的效果-文章纲要列表已收叠.png](./docs/examples/rendered/snapshots/zh-Hans-CN-1-大尺寸浏览器中的效果-文章纲要列表已收叠.png)


For more pictures, see [Application Examples](./docs/refs/en-US/application-examples.md).





## Usage

- If your purpose is to build some HTMLs out of some Markdown documents, and you'd like to utilize my themes(thanks), then please consider this advise:

    > Although you can use this package directly, as you following the guidelines below, I highly recommand you to checkout other two packages of mine, which are both promoted right inside this article, [here](#promotions). With the helps of either of the promoted packages, you can convert your Markdown files with just tiny little efforts.

- Well, if you really need to take my theme CSS in some other way, then please read on.

### Manually get Files

#### CSS Files

Simply use any CSS file located under `./dist/css` folder.

#### Javascript File(s)

Simply use any Javascript file located under `./dist/js` folder.



### Use as a Nodejs Package

```js
const { // All 6 interfaces are here.
    cssFileEntries,                  // An array of object(s).
    jsFileEntries,                   // An array of object(s).
    allFileEntriesKeyingByFileNames, // An object as a dictionary.

    syncGetContentStringOfOneFileEntry,         // A method that returns a string.
    syncGetContentStringOfDefaultCSS,           // A method that returns a string.
    syncGetContentStringOfDefaultTOCJavascript, // A method that returns a string.
} = require('@wulechuan/css-stylus-markdown-themes') // require this module

console.log('-'.repeat(60))
console.log(
    'All available files in @wulechuan/css-stylus-markdown-themes:',
    Object.keys(allFileEntriesKeyingByFileNames)
)
console.log('-'.repeat(60))

const theDefaultCSSContentString = syncGetContentStringOfDefaultCSS()

const alsoTheDefaultCSSContentString = syncGetContentStringOfOneFileEntry(
    'wulechuan-styles-for-html-via-markdown.default--no-toc.min.css'
)

const typoraCSSContentString = syncGetContentStringOfOneFileEntry(
    'wulechuan-styles-for-html-via-markdown--typora.default.css'
)

const the7thThemeContentString = syncGetContentStringOfOneFileEntry(
    cssFileEntries[6]
)

const theDefaultAndOnlyTOCJavascriptContentString = syncGetContentStringOfDefaultTOCJavascript()

const alsoTheOnlyTOCJavascriptContentString = syncGetContentStringOfOneFileEntry(
    'table-of-contents-behaviours.min.js'
)

const stillTheOnlyTOCJavascriptContentStringButNotMinified = syncGetContentStringOfOneFileEntry(
    jsFileEntries[0]
)
```





## Promotions

There's another npm package of mine, named "[@wulechuan/generate-html-via-markdown](https://www.npmjs.com/package/@wulechuan/generate-html-via-markdown)". For conveniences, let's call it package A. Package A converts a provided MarkDown string into an HTML string, and utilizes the CSS themes provided here to decorate the generated HTML contents.

Yet there is a third npm package of mine, name "[@wulechuan/gulp-markdown-to-html](https://www.npmjs.com/package/@wulechuan/gulp-markdown-to-html)". Let's call it package B. Package B works like a wrapper of the package A, make functionalities of A work just fine in [Gulpjs](https://gulpjs.com) pipelines. 


## TODOS

- Consider introducing more stylus variables for theming. I'm not sure it worths me at present. Too many arguments would make this tool much worse to understand.
- More base themes, like a dark theme?
- More combinations of base themes and code block themes?
- Typora built-in TOC styling?



## License

WTFPL

> NOTE:
>
> I'm not an expert about license types. So I temporarily use WTFPL. But I guess this type of license might conflict with the ones used by those npm packages I'm utilizing.

