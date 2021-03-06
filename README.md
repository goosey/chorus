chorus
======

a content management system! cool!

txt-file based and lightweight, I coded the base of this a very long time ago. it was time for an update! the new version has cleaner code and a tumblr-inspired look. new features include two (2) ways of editing content- clean WYSIWYG with Summernote and raw syntax highlighted code with Codemirror, drag-and-drop image uploading, and more modular settings.

![screenshot](http://s.goose.im/screenshot_20140504_173754.png)

## Instructions

### 1. Copying files
To set up chorus, copy the `admin`,`txt`, and `upload` folders and the file `header.php` to your website's folder on the server.  If you're starting from scratch, go ahead and also copy over `index.php`- this will give you a head start on building your site!

### 2. Setting login info
The default login information is `admin` and `password`- you're going to want to change this right away. To do this, open up `admin/login.php` in a text editor and look for which lines to change- they're clearly labeled. Change only what's in between quotes, and then save the file.

### 3. Adding content files
To add editable content areas, you have to start with text files! For each content area you want, you have to create a `[name].txt` file in the `txt` folder on your server, replacing [name] with a title for each area. If you already have content, go ahead and place it in these files.

### 4. Including header.php
In your index file and any other pages you want to manage using chorus, you'll need to include header.php. First, make sure you're ready to use PHP, the language chorus runs on- your files will need to have .php extensions instead of .html extensions if you want to use chorus with them. To include the header, add `<?php include 'header.php'; ?>` to the very top of your file(s).

### 5. Including content files
Now you have to place the content in your pages! To do this, just paste `<?=$txt['[name].txt'];?>` wherever you want the content to be in your page's HTML, changing [name] respectively for each content file.

### 6. Using settings variables
To implement settings, paste `<?=$s['name-of-setting'];?>` wherever those variables need to go. For example, if you have inline css on your page, you could do `body {background-color:<?=$s['color'];?>}`.

And you're done with the basic setup! For more tips, keep reading.

### Advanced

There's currently no way in the interface to delete settings (or files)- to delete a setting, go to `admin/settings.ini` and delete the line of the setting you don't want. To delete files, you'll have to delete them directly from your server.

If you're going to use the built-in WYSIWYG editor, _please_ don't upload images using the editor, upload them using the drag-and-drop one to your left. The image uploader built into the editor doesn't actually upload- it embeds images directly into the file in base64 format, which can make your txt files HUGE and sometimes crash the editor next time you try to edit the file. To place images that you've uploaded using the sidebar uploader, go to View Uploads to get the file url, then, back in the editor, click the "Picture" icon, paste the url, and click Insert Image.

If you're tired of the tumblr throwback quote, you can change the big pink text in `admin/index.php`. It's near the bottom of the page, but be careful not to touch anything else.

A lot of things are customizable if you're comfortable with editing PHP- feel free to change things around. If you can't figure something out, go ahead and ask me! I'm on twitter as [@cubeghost](http://twitter.com/cubeghost) and you can email me at hello@goose.im.
