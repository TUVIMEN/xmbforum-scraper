# Archive

Any further development has been transfered to [forumscraper](https://github.com/TUVIMEN/forumscraper).

# xmbforum-scraper

A bash script for scraping xmb forums in json.

## Requirements

 - [reliq](https://github.com/TUVIMEN/reliq)
 - [jq](https://github.com/stedolan/jq)

## Installation

    install -m 755 xmbforum-scraper /usr/bin

## Supported links formats

    http(s)?://forum.com/(.*/)?viewthread.php\?tid=([[:digit:]]+)
    http(s)?://forum.com/(.*/)?forumdisplay.php\?fid=([[:digit:]]+)
    http(s)?://forum.com/(.*/)?index.php\?gid=([[:digit:]]+)
    http(s)?://forum.com/.*

## Json format

Here's example of [thread](thread-example.json).

## Supported forums examples

    https://www.sciencemadness.org/whisper/
    https://forum.solbu.net
    https://forum.postcrossing.com
    https://forums.xmbforum2.com
    https://cieplodlawarszawy.pl

## Usage

    xmbforum-scraper [URL]...

Script downloads thread to files named by their id's.

Download forum into current directory using 4 processes

    xmbforum-scraper -p 4 'https://www.sciencemadness.org/whisper/forumdisplay.php?fid=9'

Download thread by irregular thread url into DIR

    xmbforum-scraper -d DIR -t 'https://forum.com/abcdef/loop/'

Download whole forum

    xmbforum-scraper -c 'https://forum.postcrossing.com/'

Get some help

    xmbforum-scraper -h
