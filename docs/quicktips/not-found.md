---
tipindex: "006"
tiptitle: "Adding a 404 Not Found Page to your Static Site"
date: 2018-09-20
---
A `404: Not Found` page is a pretty standard thing on the web. It’s particularly useful when someone shares a broken or mistyped link. You don’t need dynamic middleware to do this, it’s pretty easy to add to a statically generated site. There are a few options, depending on your web host:

But first let’s make our `404.html` template:

```html
---
title: Oops! Not Found
permalink: 404.html
---
<!doctype html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>{{ title }}</title>
    </head>
    <body>
        <h1>{{ title }}</h1>
        <p>This is where you should tell the user how to find their content. Maybe on the <a href="{{ "/" | url }}">home page?</a></p>
    </body>
</html>
```

Eleventy will output this template to `404.html`.

If you’re using [GitHub Pages](https://help.github.com/articles/creating-a-custom-404-page-for-your-github-pages-site/) or [Netlify](https://www.netlify.com/docs/redirects/#custom-404), there is no step two! A `404.html` file in your output directory is all you need.

Netlify even has lovely [multi-language 404 page support too using `Redirects`](https://www.netlify.com/docs/redirects/#custom-404).

## .htaccess

For other hosts, if you use `.htaccess` for configuration you can use `ErrorDocument`. Make sure your root directory matches here!

```
ErrorDocument 404 /404.html
```
