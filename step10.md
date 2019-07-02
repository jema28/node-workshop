# Step 10 - Save your blog posts

## Working with the last few files

We've included a front end JavaScript file in the public folder called `script.js`. We need to include this in the `index.html` so paste this line just before the `</body>` tag:
```html
  <script src="./script.js" type="text/javascript"></script>
```

You'll note that in the `src` folder there's a file called `posts.json`. This is where we will save our posts. If you look in the `posts.json` file, you will see there's already one blog post there. The format is:
```js
{
    [timestamp]: [blog post message]
}
```


**Your job now is:**
1. **Handle the `script.js` request coming into the server** (from the line you added to your html)

2. **Retrieve your posts from `posts.json` and send them back to `script.js`**

3. **Save new blog posts data into `posts.json`**


## Loading existing blog posts

`script.js` is trying to load existing posts by making a `GET` request. Look inside `script.js` and see if you can find any useful endpoints. `fs.readFile()` might be useful here.


The code in `script.js` is expecting to receive a JSON object. Remember your http headers!

## Saving data to a file

At the moment, your blog posts are reaching the server, but aren't being saved anywhere. To add your own blog posts to `posts.json`, you will need to read the file from the hard drive, add to it, then write it back.

You'll remember that `fs.readFile()` is the method responsible for reading files from your hard drive.  Well, `fs.writeFile()` is a method that allows you to write data into a file.

```js
fs.writeFile('path/to/file', yourData, error => {
    // do something after the file has been written
});
```

### Things to remember

* You'll want to make sure that your blog posts are also added with a timestamp. You can get the current unix timestamp using `Date.now()`.

* `fs.writeFile()` automatically overwrites the whole file. Chances are you don't want to lose all your old blog posts, so think about how you can combine `fs.readFile()` and `fs.writeFile()` to prevent overwriting.

* You will need to convert between JSON and a javascript object several times. `JSON.parse()` and `JSON.stringify()` are what you need.

---

If all the steps have gone well, you should have a fully functional CMS!


🎉CONGRATULATIONS!!🎉
===


Want more?  Then head over to...

## [**Stretch goals >>> **](stretch.md)
---
## Keywords
* [JSON](http://www.w3schools.com/js/js_json.asp)
* [JSON.parse()](https://www.w3schools.com/js/js_json_parse.asp) & [JSON.stringify()](https://www.w3schools.com/js/js_json_stringify.asp)
* [timestamp](http://www.w3schools.com/jsref/jsref_now.asp)
* [fs.readFile](https://nodejs.org/docs/latest-v6.x/api/fs.html#fs_fs_readfile_filename_options_callback)
* [fs.writeFile](https://nodejs.org/docs/latest-v6.x/api/fs.html#fs_fs_readfile_filename_options_callback)
