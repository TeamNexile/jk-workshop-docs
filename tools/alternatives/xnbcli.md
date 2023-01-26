---
layout: default
title: XNBCLI
parent: Content packing tools
grand_parent: Tools
nav_order: 3
last_modified_date: 2023-01-13 12:04
---

# XNBCLI
{: #xnbcli .title }

is a CLI tool for XNB packing/unpacking purpose built for Stardew Valley (but works for Jump King too!), made by [**LeonBlade**](https://github.com/LeonBlade).
{: .fs-6 .fw-300 }

 [Download tool](https://github.com/LeonBlade/XNBCLI/releases/latest){: .btn .btn-blue }
[Go to repository](https://github.com/LeonBlade/XNBCLI){: .btn }

![Preview]({{ site.baseurl }}/images/XNBCLI.png)

---

This program can be used in command line only, but there are two batch files that help you out so you don't have to do anything in command line.<!-- more -->

> Command line usage is:
    <br>`xnbcli pack input-file output-file` - to pack a file
    <br>`xnbcli unpack input-file output-file` - to unpack a file

## Table of convertions
<table>
    <thead>
        <tr>
            <th>Type of file</th>
            <th>file to XNB</th>
            <th>XNB to file</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th style="font-weight: normal;">image</th>
            <th class="label-green">✔</th>
            <th class="label-green">✔</th>
        </tr>
        <tr>
            <th style="font-weight: normal;">sound</th>
            <th class="label-red">✖</th>
            <th class="label-red">✖</th>
        </tr>
    </tbody>
</table>

## Supported types
Supported images formats are: `.png`, `.bmp`.

## Usage 

This program only works using command line but don't let that discourage you. You can execute `unpack.bat` and `pack.bat` to get the job done!

### CLI support

```sh
xnbcli (pack|unpack) [input] [output]
```

|Argument|Description|
|---|---|
|`pack`|file to XNB|
|`unpack`|XNB to file|
|`input`|Your input file name|
|`output`|Your output file name|

**Unpacking XNB files**

Place any files you wish to extract in the `packed` folder and run the appropriate file for unpacking (which is `unpack.bat`).

**Packing XNB files**

Place any files you wish to repack back into XNB files in the `unpacked` folder and run the appropriate file for packing (which is `pack.bat`).