
[![node.cobol](http://i.imgur.com/x9CJpKB.png)](#)

# node.cobol

 [![Support me on Patreon][badge_patreon]][patreon] [![Buy me a book][badge_amazon]][amazon] [![PayPal][badge_paypal_donate]][paypal-donations] [![Version](https://img.shields.io/npm/v/node.cobol.svg)](https://www.npmjs.com/package/node.cobol) [![Downloads](https://img.shields.io/npm/dt/node.cobol.svg)](https://www.npmjs.com/package/node.cobol)

> Node.js bridge for COBOL which allows you to run Node.js code from COBOL.

[![node.cobol](http://i.imgur.com/xmsSmLX.png)](#)

You have to install [Node.js](https://nodejs.org/en/) on
your machine. In case you do not have a COBOL compiler,
you can install it by running:
```sh
# Ubuntu
sudo apt-get install open-cobol

# OS X
brew install gnu-cobol
```

## :clipboard: Example



```cobol
      * Compile this file together with the node.cobol
      * modules:
      *
      *  $ cobc -x example/main.cbl lib/node-exec*.cbl
      *
      * Then execute the binary file:
      *
      *  $ ./main
       IDENTIFICATION DIVISION.
       PROGRAM-ID. MAIN.

       DATA DIVISION.
          WORKING-STORAGE SECTION.
          01 NODEJS-CODE PIC X(100) value "console.log('Hello World!')".

       PROCEDURE DIVISION.
      * Execute a short Node.js snippet
           CALL 'EXEC_NODEJS' USING NODEJS-CODE

           DISPLAY "Starting an HTTP server on port 8000".

      * Convert an image into ASCII/ANSI art
           CALL 'EXEC_NODEJS_FILE' USING "example/grace-hopper.js"

           DISPLAY "Starting an HTTP server on port 8000".

      * Starting an HTTP server in Node.js
           CALL 'EXEC_NODEJS_FILE' USING "example/server.js".
       STOP RUN.
```

## :question: Get Help

There are few ways to get help:

 1. Please [post questions on Stack Overflow](https://stackoverflow.com/questions/ask). You can open issues with questions, as long you add a link to your Stack Overflow question.
 2. For bug reports and feature requests, open issues. :bug:
 3. For direct and quick help from me, you can [use Codementor](https://www.codementor.io/johnnyb). :rocket:


To compile the program, use:
```sh
cobc -x example/main.cbl lib/node-exec*.cbl
```

## :memo: Documentation

The COBOL modules from the [`lib/`](/lib) directory export the following subroutines:
### `EXEC_NODEJS(code)`

 - `code`: The Node.js snippet to execute.

### `EXEC_NODEJS_FILE(file)`

 - `file`: The Node.js file path.


## :yum: How to contribute
Have an idea? Found a bug? See [how to contribute][contributing].


## :sparkling_heart: Support my projects

I open-source almost everything I can, and I try to reply everyone needing help using these projects. Obviously,
this takes time. You can integrate and use these projects in your applications *for free*! You can even change the source code and redistribute (even resell it).

However, if you get some profit from this or just want to encourage me to continue creating stuff, there are few ways you can do it:

 - Starring and sharing the projects you like :rocket:
 - [![PayPal][badge_paypal]][paypal-donations]—You can make one-time donations via PayPal. I'll probably buy a ~~coffee~~ tea. :tea:
 - [![Support me on Patreon][badge_patreon]][patreon]—Set up a recurring monthly donation and you will get interesting news about what I'm doing (things that I don't share with everyone).
 - **Bitcoin**—You can send me bitcoins at this address (or scanning the code below): `1P9BRsmazNQcuyTxEqveUsnf5CERdq35V6`

    ![](https://i.imgur.com/z6OQI95.png)

Thanks! :heart:



## :sparkles: Related

 - [`cobol`](https://github.com/IonicaBizau/node-cobol)—COBOL bridge for NodeJS which allows you to run COBOL code from NodeJS.
 - [`fortran`](https://github.com/IonicaBizau/node-fortran)—Fortran bridge for Node.js which allows you to run Fortran code from Node.js.
 - [`node.fortran`](https://github.com/IonicaBizau/node.fortran#readme)—Execute Node.js in your Fortran programs.



## :scroll: License

[MIT][license] © [Ionică Bizău][website]

[badge_patreon]: http://ionicabizau.github.io/badges/patreon.svg
[badge_amazon]: http://ionicabizau.github.io/badges/amazon.svg
[badge_paypal]: http://ionicabizau.github.io/badges/paypal.svg
[badge_paypal_donate]: http://ionicabizau.github.io/badges/paypal_donate.svg
[patreon]: https://www.patreon.com/ionicabizau
[amazon]: http://amzn.eu/hRo9sIZ
[paypal-donations]: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=RVXDDLKKLQRJW
[donate-now]: http://i.imgur.com/6cMbHOC.png

[license]: http://showalicense.com/?fullname=Ionic%C4%83%20Biz%C4%83u%20%3Cbizauionica%40gmail.com%3E%20(https%3A%2F%2Fionicabizau.net)&year=2016#license-mit
[website]: https://ionicabizau.net
[contributing]: /CONTRIBUTING.md
[docs]: /DOCUMENTATION.md
