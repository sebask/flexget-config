# FlexGet Configuration for Synology DSM and Transmission

For a while I have been using [Transmission](http://transmissionbt.com) on my [DiskStation](http://synology.com). It works great. There is one problem though. Transmission can't automatically download and/or extract anything.

It took me a while to come up with a decent solution, but [FlexGet](http://flexget.com/) (available as a DiskStation Manager package by [SynoCommunity](http://synocommunity.com/repository)) seems to do the job really well. It's an excellent tool to automate downloads like series or movies. FlexGet uses [YAML](http://yaml.org/) for configuration. It's a little unsettling at first but once you get the hang of it it's very easy to use.

As such I published my config.yml. This script, used by FlexGet, downloads specific series from a (private) tracker using RSS and unpacks them to a location with other series. The downloads from this tracker come in a packed form and often contain a .nfo file.

Additionally the script keeps track of a manual and wishlist RSS feed. If anything shows up and meets the requirements it gets downloaded and sorted.

This script contains the following tasks:

1. The `manual` and `wishlist` task adds torrents from a RSS feed to Transmission using the web protocol.
2. The `series` task adds torrents from a RSS feed of the specified series to Transmission using the web protocol.
3. The `sort-manual-wishlist` task looks for new `mkv` files and copies those to their respective directory (`/Movies/The.Name.Of.The.Download`).
4. The `sort-series` task looks for `rar` files, creates the destination directory (`/Series Name/Series Season`) when needed and unpacks the episode at the destination.
5. An email notification will be sent when any task has started.
