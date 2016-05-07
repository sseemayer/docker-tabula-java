# docker-tabula-java

A minimal Docker image for running the [tabula-java](https://github.com/tabulapdf/tabula-java) from a Docker container. Based on [java:openjdk-8-jre-alpine](https://hub.docker.com/_/java/).

## Running

You can mount a PDF file available at `/full/path/to/my/file.pdf` to the docker container by using the `-v` option to the `docker run` command:

```
$ docker run --rm -v /full/path/to/my/file.pdf:/data.pdf sseemayer/tabula-java [tabula options] /data.pdf > output.csv
```

To get tabula help:

```
$ docker run --rm sseemayer/tabula-java --help
usage: tabula [-a <AREA>] [-c <COLUMNS>] [-d] [-f <FORMAT>] [-g] [-h] [-i]
       [-n] [-o <OUTFILE>] [-p <PAGES>] [-r] [-s <PASSWORD>] [-u] [-v]

Tabula helps you extract tables from PDFs
 -a,--area <AREA>           Portion of the page to analyze
                            (top,left,bottom,right). Example: --area
                            269.875,12.75,790.5,561. Default is entire
                            page
 -c,--columns <COLUMNS>     X coordinates of column boundaries. Example
                            --columns 10.1,20.2,30.3
 -d,--debug                 Print detected table areas instead of
                            processing.
 -f,--format <FORMAT>       Output format: (CSV,TSV,JSON). Default: CSV
 -g,--guess                 Guess the portion of the page to analyze per
                            page.
 -h,--help                  Print this help text.
 -i,--silent                Suppress all stderr output.
 -n,--no-spreadsheet        Force PDF not to be extracted using
                            spreadsheet-style extraction (if there are
                            ruling lines separating each cell, as in a PDF
                            of an Excel spreadsheet)
 -o,--outfile <OUTFILE>     Write output to <file> instead of STDOUT.
                            Default: -
 -p,--pages <PAGES>         Comma separated list of ranges, or all.
                            Examples: --pages 1-3,5-7, --pages 3 or
                            --pages all. Default is --pages 1
 -r,--spreadsheet           Force PDF to be extracted using
                            spreadsheet-style extraction (if there are
                            ruling lines separating each cell, as in a PDF
                            of an Excel spreadsheet)
 -s,--password <PASSWORD>   Password to decrypt document. Default is empty
 -u,--use-line-returns      Use embedded line returns in cells. (Only in
                            spreadsheet mode.)
 -v,--version               Print version and exit.
```
