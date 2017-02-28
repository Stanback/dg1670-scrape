# OSX Installation

Assuming you have Homebrew installed.

    brew install perl
    brew link --force libxml2
    cpan -I HTML::TableExtract
    cpan -I LWP::UserAgent
    cpan -I CGI
    cpan -I Alien::RRDTool
    brew unlink libxml2

Update the `cable-modem` and `cablegraph` to use /usr/local/bin/perl
instead of /usr/bin/perl

Create /var/db/cable and give write access (chmod / chown)

Create cron job:

    export EDITOR=nano
    crontab -e
    */5 * * * * zsh -c /Users/user/Desktop/dg1670-scrape/cgi-bin/cable-modem

Move files to cgi-bin or htbin directory and run:

    python -m CGIHTTPServer 8000
