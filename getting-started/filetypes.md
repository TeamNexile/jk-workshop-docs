---
layout: default
title: File types
parent: Getting started
nav_order: 3
last_modified_date: 2023-03-28 11:02
---

# File types
{: .no_toc }

distinguishing and understanding the file types and format.<!-- more -->
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Configuration files

All configuration files in Jump King use the XML format.

### XML and mark-up language

XML (which stands for eXtensible Markup Language) is a type of markup language that is used to store and exchange data in a structured format and is widely used as a standard for **exchanging data between different applications and platforms**.

A markup language is a **set of rules** for adding tags (also known as "markup") to a document to define its **structure** and **meaning**. In XML, you use tags to **define the structure of your data**. 

### XML rules

A tag name:
1. **cannot** contain special characters and/or spaces.
    ```xml
    <!-- ❌ NOT VALID -->
    <volume audio 🎵></<audio name 🎵> 

    <!-- ☑️ VALID -->
    <volume_audio></volume_audio>          
    ```
2. **can** contain a value:
    ```xml
     <!-- ☑️ VALID -->
    <audio_enabled>true</audio_enabled>
    <speech>A long paragraph...</speech>
    <sprite>Character</sprite>
    <sprite>☑️</sprite>
    <screen>12</screen>
    <audio_volume>0.12</audio_volume>
    ```
3. **can** contain other tags:
    ```xml
    <!-- ☑️ VALID -->
    <merchant>
        <trading>Silver</trading>
        <npc_settings>
            <position>
                <X>128.5</X>
                <Y>62</Y>
            </position>
            <screen>3</screen>
        </npc_settings>
    </merchant>
    ```
4. is **case sensitive**:
    ```xml
    <!-- ⚠️ X and x are two different tags! -->
    <X>64</X>
    <x>63.5</x>
    ```
5. need to be **properly nested and closed**:
    ```xml
    <!-- ❌ NOT VALID -->
    <first><second><third>1.5</second></third></first> 
    <first><second><third>1.5</second></first>

    <!-- ☑️ VALID -->
    <first><second><third>1.5</third></second></first> 
    ```

### Practical example

For instance, if you were creating an XML document to store information about the locations in Jump King, you might use tags to indicate the start and end screen, title animation trigger screen (unlock) and name. Here's an example of what **<u>a portion of the XML document</u>** might look like:

```xml
<locations>
    <Location>
        <start>1</start>
        <end>8</end>
        <unlock>2</unlock>
        <name>Jungle</name>
    </Location>
    <Location>
        <start>9</start>
        <end>15</end>
        <unlock>9</unlock>
        <name>Keep of Despair</name>
    </Location>
</locations>
```

In this example, the `locations` element contains two `Location` elements, each of which has child elements for the start and end screen, title animation trigger screen (unlock) and name.

> While the previous XML example is grammatically valid, this will not work since the snippet is not complete to work in-game. Check out [**Locations**]({{site.baseurl}}/level-making/gui#locations) to implement properly.
{: .disclaimer }

> **The tags define the structure of the data, making it easier to parse and process by computers.**