sheetsee-starter
================

![ss](https://raw.github.com/jlord/sheetsee-cache/master/img/sheetsee-03.png)

Fork and get started with Sheetsee.js! 

### Step 1: Fork

Fork this repo (see top right of page)! Now you have a copy on your account.

### Step 2: Change the Repo's Name

You probably aren't building something called 'sheetsee-starter', so go into your fork's settings (right menubar) and rename.

### Step 3: Connect to your Spreadsheet

When you spreadsheet is ready, edit the HTML file in your fork to have your spreadsheet's key. You'll find the place for the key in these lines:

```JavaScript
document.addEventListener('DOMContentLoaded', function() {
    var URL = "YOURSPREADSHEETSKEYHERE" // <--- It's here! Change this to your key!
    Tabletop.init( { key: URL, callback: myData, simpleSheet: true } )
})
```

To get your spreadsheet's key, first *set the share setting* to 'anyone with a link can view' and then *start publishing* the data by going to File -> Publish to the Web... -> Start Publishing. Then grab the key from the URL it gives you (you can also just use the full url if you want).

**Now you've got your site hooked up!**

### Go to Town

Now it's time to add the elements you want on your site to the `index.html` file. You can edit the file directly from GitHub.com (so no need to install Git or text editor, unless you want to). When you've made your changes, click the commit button at the bottom of the edit page.

- HTML, Templates and JS [snippets](snippets.md) for tables & maps
- Add your CSS to `css/style.css`
- Add any other JS files to `js/`

### Visit your site!

Once you've commited changes, check out your site at **github.io/yourusername/theforksname**.

WOW!


