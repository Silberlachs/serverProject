# MultiPage

Multipage is a Shellscript that aims in helping you setting up multipage websites.
I made it because I found it really cumbersome to manually edit VHOSTs and create
all the folder structures

## Requirements

An Ubuntu 20.04 server with a non-root user with sudo privileges. 

Apache installed on the server. This project assumes a www-data user responsible for 
handling apache2 stuff. You can change the name in line 5, however.


## Installation

Put the script into your /bin folder to make it accessible from the command line.
!!! Always be carefull when installing software this way !!!

You can use this line to install it from your downloads folder:
```bash
sudo chmod u+x multipage && mv multipage /bin/multipage
```
Attention:
Depending on whether or not you want to enable ssl for your page, you need to setup
the correct paths before first use of the script, otherwise you will create useless
ssl files without actually using ssl (your server might print an error message).
A self-signed (snakeoil) certificate can be created by installing the ssl-cert package.
Feel free to expand the create_vhost_ssl_file() function if you need additional ssl options.

## Usage

```shell

# call as superuser
First, give a name for the new project ( e.g. mysite.com )

```

## Contributing

Contact me if you have questions or suggestions.
I may not have the time to respond immediately.

## License

[MIT]