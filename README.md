FlexGet Config for Synology DSM and Transmission
==============

For a while I have been using [Transmission](http://transmissionbt.com) on my [DiskStation](http://synology.com). It works great. There is one problem though. Transmission can't automatically download and/or extract anything.

It took me a while to come up with a decent solution, but [FlexGet](http://flexget.com/) (available as a DiskStation Manager package by [SynoCommunity](http://synocommunity.com/repository)) seems to do the job really well. It's an excellent tool to automate downloads like tv shows or movies. FlexGet uses [YAML](http://yaml.org/) for configuration. It's a little unsettling at first but once you get the hang of it it's very easy to use.


As such I published my config.yml. This script, used by FlexGet, downloads specific tv shows from a (private) tracker using RSS and unpacks them to a location with other tv shows. The downloads from this tracker come in a packed form and often contain a .nfo file.

This script contains the following tasks:

1. The download task adds torrents from a RSS feed of the specified tv shows to Transmission using the web protocol.  
2. The unpack task looks for a .rar/.nfo file, creates the destination folder (Series Name/Series Season) when needed and unpacks the episode.