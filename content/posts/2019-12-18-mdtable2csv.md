---
title: "Convert Markdown Table to CSV"
date: 2019-12-18T23:40:27+09:00
draft: false
tags: ["golang", "markdown", "converter"]
---

I created `mdtable2csv` command for me.

[515hikaru/mdtable2csv: Convert markdown table to csv](https://github.com/515hikaru/mdtable2csv)

## Why?

I often use [Markdown Tables generator](https://www.tablesgenerator.com/markdown_tables) because of writing table with markdon is too difficult for me. However, I had one problem. Markdown Tables generator cannot reverse transform, for example, markdown table to csv. Because of this, I was reluctant to edit the table once I wrote it.

I always use a spreadsheet like Microsoft Excel to edit a table because I don't want to worry about anything other than the contents of the cell. If you can do the reverse conversion, you can edit the table by converting the table once written markdown into CSV and paying attention only to the contents of the cell.

## Language and Implementation

I knew it was very easy before I made it. At least if you have a Markdown parser and a CSV parser, you can just connect them. Both were in Golang, and above all I wanted to make it easier to run on multiple machines.

It's so easy that everything goes just with the `go get` command.

## Impressions

To be honest, it's not the quality that people can still use, but I've been freed from the trivial (and still not negligible) stress of everyday life. This is the best part of programming.
