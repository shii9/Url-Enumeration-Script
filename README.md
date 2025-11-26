# Url-Enumeration-Script For All knowing tools

A small, practical collection of conventions and an example "universal" shell script to run multiple URL/endpoint discovery tools, collect their output into a single file, normalize results, sort them and remove duplicates.

This repository's goal is to make it easy to run any supported URL enumeration tool (or your own custom commands), capture their stdout, and produce one clean, deduplicated list of URLs for further processing (scanning, fuzzing, scraping, etc).

Why this repo
- Different tools output URLs in different formats and to different destinations. This repo documents a simple convention and provides a reusable script you can customize.
- The universal script runs tools in parallel (or sequentially), captures each tool's output to a per-tool file, and produces a single deduplicated, sorted file named results-<target>.txt.

Principles and naming convention
- Each tool command should write URLs to stdout.
- Use a consistent output file name pattern:
  url_enum_<toolname> <target> > all_<toolname>
  Example:
    url_enum_gau example.com > all_gau
- The universal runner will look for files named all_<toolname> in a temporary directory, then combine them.
- Keep the tool wrapper names or commands simple so they can be chained, redirected, or run by the universal script.

Tools For collecting URLs

-  Gau
-  Gospider
-  Katana
-  Hakrawler 
-  WaybackUrl 
-  XnLinkFinder 
-  Waymore
