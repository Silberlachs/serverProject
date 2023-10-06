# MultiPage

Multipage is a Shellscript that aims in helping you setting up multipage websites.
I made it because I found it really cumbersome to manually edit VHOSTs and create
all the folder structures

## Requirements

An Ubuntu 20.04 server with a non-root user with sudo privileges. 

Apache installed on the server. This project assumes a www-data user responsible for 
handling apache2 stuff. You can change the name in line 4, however.


## Installation

Put the script into your /bin folder to make it accessible from the command line.
!!! Always be carefull when installing software this way !!!

You can use this line to install it from your downloads folder:
```bash
sudo chmod u+x multipage && mv multipage /bin/multipage
```
Tl;wr
Take 1 minute to look at the first 10 lines of the script, these are the options!

Depending on whether or not you want to enable ssl for your page, you need to setup
the correct paths before first use of the script, otherwise you will create useless
ssl files without actually using ssl (your server might print an error message).
A self-signed (snakeoil) certificate can be created by installing the ssl-cert package.
Feel free to expand the create_vhost_ssl_file() function if you need additional ssl options.

There might be a little issue with your /etc/hosts file, i made sure the entries are inserted
at the very top of the file ( because at the bottom there are the default ipv6 entries )
However, we're useing the sed command which will not work if the file is completely empty.
If you find your hosts file beeing completely empty, just add #comment and you're fine.

## Usage

```shell
# call as superuser
sudo multipage
```
Give a name for the new project ( e.g. mysite.com )
That's it! everything else should work out of the box.

## Contributing

Contact me if you have questions or suggestions.
I may not have the time to respond immediately.

## License

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
