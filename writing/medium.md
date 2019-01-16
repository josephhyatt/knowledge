# Medium

## Medium-to-Markdown on the Command Line

> The [medium-to-markdown command line ](https://www.npmjs.com/package/medium-to-markdown)package is written in **Javascript** which means you’ll need `node` to run and `npm` to install the package. If you’re on Windows, use [this page](https://nodejs.org/en/) to install both \(it takes about 3 minutes\). Then, install the package using `npm install medium-to-markdown`. The actual script you’ll need to run is available [here](https://www.npmjs.com/package/medium-to-markdown), and also shown below.

```javascript
const mediumToMarkdown = require('medium-to-markdown');
 
// Enter url here
mediumToMarkdown.convertFromUrl('<medium post url>')
.then(function (markdown) {
  console.log(markdown); //=> Markdown content of medium post
});
```

> To run, save the script as `medium-to-markdown.js`, change the `"<medium post url">` to the address of your published post, and type `node medium-to-markdown.js` at the command line \(making sure the script is in your directory.
>
> This will output the entire post as Markdown in your console. To redirect the output to a file, you can type `node medium-to-markdown.js >> file.md` If you’re using GitHub Pages + Jekyll for your blog, you’ll want to save the `md`file in the `_posts/` directory of your repository as `date-title.md` . For example, my [latest post file](https://github.com/WillKoehrsen/willkoehrsen.github.io/tree/master/_posts) is `_posts/2018-09-16-Five-Minutes-to-Your-Own-Website.md` . Once the article has been converted to a properly named Markdown file, it can be published by pushing the repository to GitHub.
>
> Personally, I found that process of manually renaming the file tedious, so I wrote a Python script that accepts a url of a published Medium post along a date, calls the `medium-to-markdown.js` conversion script with the url, and saves the resulting markdown with the correct file name. The script can be found [here](https://github.com/WillKoehrsen/willkoehrsen.github.io/blob/master/_posts/medium_to_markdown.py), and the command line usage is below:

```text
C:\Users\willk\OneDrive\Documents\willkoehrsen.github.io\_posts>python medium_to_markdown.py
Enter post url: https://medium.com/@williamkoehrsen/five-minutes-to-your-own-website-fd0b43cbd886
Enter date (as 2018-10-05): 2018-09-16
Post saved as markdown to 2018-09-16-five-minutes-to-your-own-website.md
```

> Overall, it takes 15 seconds to run the script and about 5 minutes for the website to update! Go to your blog to see the article rendered. 
>
> Original Source: [https://towardsdatascience.com/converting-medium-posts-to-markdown-for-your-blog-5d6830408467](https://towardsdatascience.com/converting-medium-posts-to-markdown-for-your-blog-5d6830408467)





