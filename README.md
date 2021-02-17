# Web Archive scraper

Waybackpack is a command-line tool that lets you download the entire Wayback Machine archive for a given URL.

## How to run

```sh
python cli.py infopark.co -d infopark.co --follow-redirects
```

## Usage

```
usage: python cli.py [-h] (-d DIR | --list) [--raw] [--root ROOT]
                   [--from-date FROM_DATE] [--to-date TO_DATE]
                   [--user-agent USER_AGENT] [--follow-redirects]
                   [--uniques-only] [--collapse COLLAPSE] [--quiet]
                   url

positional arguments:
  url                   The URL of the resource you want to download.

optional arguments:
  -h, --help            show this help message and exit
  -d DIR, --dir DIR     Directory to save the files. Will create this
                        directory if it doesn't already exist.
  --list                Instead of downloading the files, only print the list
                        of snapshots.
  --raw                 Fetch file in its original state, without any
                        processing by the Wayback Machine or waybackpack.
  --root ROOT           The root URL from which to serve snapshotted
                        resources. Default: 'https://web.archive.org'
  --from-date FROM_DATE
                        Timestamp-string indicating the earliest snapshot to
                        download. Should take the format YYYYMMDDhhss, though
                        you can omit as many of the trailing digits as you
                        like. E.g., '201501' is valid.
  --to-date TO_DATE     Timestamp-string indicating the latest snapshot to
                        download. Should take the format YYYYMMDDhhss, though
                        you can omit as many of the trailing digits as you
                        like. E.g., '201604' is valid.
  --user-agent USER_AGENT
                        The User-Agent header to send along with your requests
                        to the Wayback Machine. If possible, please include
                        the phrase 'waybackpack' and your email address. That
                        way, if you're battering their servers, they know who
                        to contact. Default: 'waybackpack'.
  --follow-redirects    Follow redirects.
  --uniques-only        Download only the first version of duplicate files.
  --collapse COLLAPSE   An archive.org `collapse` parameter. Cf.:
                        https://github.com/internetarchive/wayback/blob/master
                        /wayback-cdx-server/README.md#collapsing
  --quiet               Don't log progress to stderr.
  --max-retries MAX_RETRIES
                        How many times to try accessing content with 4XX or
                        5XX status code before skipping?
```

## Support

Waypackback is written in pure Python, depends only on [`requests`](docs.python-requests.org), and should work wherever Python works. Should be compatible with both Python 2 and Python 3.

