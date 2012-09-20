JSDate
======

jsdate.js adds a format function to the javascript date object that works like PHP `date()`. It implements all of the PHP date formats except for timezone names and daylight saving.  For the complete list of possible formats, refer to the Parameters section of the [PHP date() documentation](http://php.net/manual/en/function.date.php).

###Using JSDate

JSDate adds a `.format()` function on the Date object prototype. To use it, create a new `Date()` object, then call `.format()` on the date object with any combination of the implemented formats (any of the parameters on the [PHP manual page](http://php.net/manual/en/function.date.php) except "e", "I", and "T") plus any other characters that you need.

    var dateObj = new Date();
    var formattedDate = dateObj.format('F jS, Y'); // prints out as "January 11th, 2010"

Note that the above example uses spaces and a comma in addition to the formatting letters.  You may also use other alphabetical characters, but if you need to use one of the letters reserved for a format you’ll need to escape it with two backslashes (`\\`).  To use an actual backslash character, use 4 backslashes.

    var dateObj = new Date();
    var formattedDate = dateObj.format('l, \\t\\h\\e jS \\o\\f F, Y'); // prints out as "Monday, the 11th of January, 2010"