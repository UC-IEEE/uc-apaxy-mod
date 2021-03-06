#   Apaxy mod_autoindex theme
### Classy Apache directory indexes made easy
![](screenshot.png)

Originally by @AdamWhitcroft ([home][ah]), with very small modifications for
ieee.uc.edu by @ernstki. The IEEE-specific customizations are maintained in a
separate "ieee" branch, so this repository is ready for any on-campus to clone
and start using. (You'll want to customize the contact email in the footer is
all; see below for instructions.)

## Getting started

After having cloned the repository from GitHub like so:

    cd /web/sites/<your org's site>/htdocs
    # Either:
    git clone https://github.com/UC-IEEE/uc-apaxy-mod.git index-theme
    # or:
    # git clone https://github.uc.edu/IEEE/uc-apaxy-mod.git index-theme

Create a symbolic link to `dot-htaccess` named `.htaccess` in directories where
you want fancy indexes enabled, _e.g._:

    # working dir: /web/sites/your.site.uc.edu/htdocs
    cd pub
    ln -s ../index-theme/dot-htaccess .htaccess

This `.htaccess` file will now be hidden, so you'll need to use `ls -la` to
see it. The settings in this file will apply to subdirectories as well,
_e.g._, `your.site.uc.edu/pub/software` using the example.


## Customization

You'll definitely want to replace `admin@your-org.uc.edu` in `footer.html`
(around line 5) with your actual webmaster/webmistress' contact email.

If you wish to customize the header or footer for just a specific
subdirectory of your site, make a **copy** of `dot-htaccess` as `.htaccess` in
the desired directory.

    # for example, inside a 'pub' directory off your "web root"
    cp ../index-theme/dot-htaccess .htaccess

If you don't like `/index-theme` or you cloned the Git repo into some other
directory, just do a global search-and-replace on this file for `/index-theme`
and update it to match the directory (rooted at your "server root") where
you've cloned this repository.

When doing _really_ crazy customizations, you might find that relative paths
(_e.g._, `../index-theme`) work in some cases, but you're always safer
specifying the absolute path (_e.g._, `/index-theme`) to where the Apaxy theme
support files are.

## See also

For a full breakdown of the settings for the Apache `mod_autoindex` module, check the
[relevant section][ap1] of the manual.


[ah]:  http://adamwhitcroft.com/apaxy/
[ap1]: http://apache.org/docs/2.2/mod/mod_autoindex.html
