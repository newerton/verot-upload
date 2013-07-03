Package of VEROT's Upload Class
=============

This package is simply a copy of [Verot's PHP Upload class](http://www.verot.net/php_class_upload.htm).

### Usefull Links

* [class.upload.php page](http://www.verot.net/php_class_upload.htm)
* [class.upload.php downloads](http://www.verot.net/php_class_upload_download.htm)
* [class.upload.php documentation](http://www.verot.net/php_class_upload_docs.htm)
* [class.upload.php samples, a files uploading and images manipulation PHP class](http://www.verot.net/php_class_upload_samples.htm)
* [class.upload.php license](http://www.verot.net/php_class_upload_gpl.htm)

class.upload.php
-------

### What is it?

An example will be more useful than any blurb I can write :

```php
$foo = new Upload($_FILES['form_field']);
if ($foo->uploaded) {
    // save uploaded image with no changes
    $foo->Process('/home/user/files/');
    if ($foo->processed) {
        echo 'original image copied';
    } else {
        echo 'error : ' . $foo->error;
    }
    // save uploaded image with a new name
    $foo->file_new_name_body = 'foo';
    $foo->Process('/home/user/files/');
    if ($foo->processed) {
    echo 'image renamed "foo" copied';
    } else {
    echo 'error : ' . $foo->error;
    }
    // save uploaded image with a new name,
    // resized to 100px wide
    $foo->file_new_name_body = 'image_resized';
    $foo->image_resize = true;
    $foo->image_convert = gif;
    $foo->image_x = 100;
    $foo->image_ratio_y = true;
    $foo->Process('/home/user/files/');
    if ($foo->processed) {
        echo 'image renamed, resized x=100
              and converted to GIF';
        $foo->Clean();
    } else {
        echo 'error : ' . $foo->error;
    }
}
```

### What does it actually do in this example?

This example uses a file uploaded via a form. With this single file, it will :

* copy the file without any modification
* copy the file after having changed its name to 'foo'
* copy the file, resizing it to x=100, y=auto, converting it to GIF

### How does it work?

* the class constructor _upload_ handles a uploaded file (it can also handle a local file)
* some optional parameters can be set up to act on the file during the _process_
* the process is called with as an argument the destination directory on the server. If some parameters have been set up, the class will rename, resize, convert files and images
* when the uploaded file is not needed anymore, we can delete it using _clean_.

### Why use this class?

* with one uploaded file, you can do as many copies, convertions, resizing you want.
* you can resize each image dimension, or both, keeping the image ratio or not.
* you can choose to resize an image only if it is bigger -or smaller- than the wanted sizes
* you can manipulate the image in many ways, play with colors, add borders, labels and watermarks...
* its use is simplistic but powerful
* you can work on uploaded files or local files, useful for batch processing
* Flash uploaders are fully supported
* MIME type detection is very comprehensive
* more than 60 documented configuration settings
* a lot of variables are set up during the process. You can retrieve all these values after a process.
* error messages are understandable, and a variable log allows you to see what the class does.
* it is translated in more than 25 languages
* it is already widely used on Internet
* it is free :)

### Is it out there on Internet?

The class.upload.php source code has been downloaded well over **100 000 times** just in the last three years. It is also a key part of the popular [K2 content component for Joomla!](http://getk2.org/), downloaded over **500 000 times**, and has been implemented in numerous CMS and frameworks!

class.upload.php is featured on [HotScripts](http://www.hotscripts.com/). If you like the script, please rate it or write a review for it. You can find it [here](http://www.hotscripts.com/Detailed/45364.html).

class.upload.php is featured on [PHP Classes](http://www.phpclasses.org/). If you like the script, please rate it there. You can find it [here](http://www.phpclasses.org/browse/package/2181.html).

class.upload.php is featured on [Freshmeat](http://freshmeat.net/). If you like the script, please rate it there. You can find it [here](http://freshmeat.net/projects/class_upload_php/).

### Commercial licenses

[Commercial licenses](http://www.verot.net/php_class_upload_license.htm) are available [here](http://www.verot.net/php_class_upload_license.htm).
