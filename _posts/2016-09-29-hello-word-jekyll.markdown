---
layout: post
title:  "Hello Word Jekyll"
date:   2016-09-29 12:55:00 +0700
categories: [jekyll]
---

Ada yang tau apa itu `jekyll`?.

Jekyll adalah keadaan ketika kita 5 hari tidak mandi, maka badan kita akan 'jekyll'.


* **jekyll**
_Erwin Wahyudi_


First level header
==================

Second level header
-------------------


# H1 header

## H2 header

### H3 header

#### H4 header

##### H5 header

###### H6 header



First level header
==================

Second level header
-------------------


And A Header
------------
And a paragraph

> This is a blockquote.


Hello        {#id}
-----

# Hello      {#id}

# Hello #    {#id}


> This is a paragraph.
>
> > A nested blockquote.
>
> ## Headers work
>
> * lists too
>
> and all other block-level elements
Note that the first space character after the > marker does not count when counting spaces for the indentation of the block-level elements inside the blockquote! So code blocks will have to be indented with five spaces or one space and one tab, like this:

> A code block:
>
>     ruby -e 'puts :works'
Line wrapping allows one to be lazy but hinders readability and should therefore be avoided, especially with blockquotes. Here is an example of using blockquotes with line wrapping:

> This is a paragraph inside
a blockquote.
>
> > This is a nested paragraph
that continues here
> and here
> > and here
Code Blocks
Code blocks can be used to represent verbatim text like markup, HTML or a program fragment because no syntax is parsed within a code block.



{% highlight ruby %}
#!/usr/bin/env ruby

require 'json'
require 'net/http'
require 'libnotify'

def parsejson
    file = "http://api.openweathermap.org/data/2.5/find?q=London&mode=json"
    response = Net::HTTP.get_response(URI.parse(file))
    weatherjson = response.body
    actual = JSON.parse(weatherjson)

    # check for errors
    if actual.has_key? 'Error'
        raise "error with the url"
    end

    results = []

    actual["list"].each do |listitem|
        weather = listitem["weather"]
        weather.each do |weath|
            results.push(weath["description"])
        end
        main = listitem["main"]
        temp = main["temp"] - 273.15
        results.push ("%.2f" % temp)
    end

    return results
end
{% endhighlight %}

Unordered and ordered lists work the same way in regard to the indentation:

* list 1 item 1
* list 1 item 2 (indent 1 space)
  * list 1 item 3 (indent 2 spaces)
   * list 1 item 4  (indent 3 spaces)
    * lazy text belonging to above item 4
1. list 1 item 1
 2. list 1 item 2 (indent 1 space)
  3. list 1 item 3 (indent 2 spaces)
   4. list 1 item 4  (indent 3 spaces)
    5. lazy text belonging to above item 4
* list 1 item 1
  * nested list item 1
  * nested list item 2
* list 1 item 2
  * nested list item 1
1. list 1 item 1
   1. nested list item 1
   2. nested list item 2
10. list 1 item 2
    1. nested list item 1
1. text for this list item
   further text (indent 3 spaces)


   Since the content of a list item can contain block-level elements, you can do the following:

*   First item

    A second paragraph

    * nested list

    > blockquote


| First cell|Second cell|Third cell
| First | Second | Third |

First | Second | | Fourth |

Here are some example separator lines:

|----+----|
+----|----+
|---------|
|-
| :-----: |
-|-


|-----------------+------------+-----------------+----------------|
| Default aligned |Left aligned| Center aligned  | Right aligned  |
|-----------------|:-----------|:---------------:|---------------:|
| First body part |Second cell | Third cell      | fourth cell    |
| Second line     |foo         | **strong**      | baz            |
| Third line      |quux        | baz             | bar            |
|-----------------+------------+-----------------+----------------|
| Second body     |            |                 |                |
| 2 line          |            |                 |                |
|=================+============+=================+================|
| Footer row      |            |                 |                |
|-----------------+------------+-----------------+----------------|


* list one
^
* list two

A simple paragraph with an ID attribute.
{: #para-one}

> A blockquote with a title
{:title="The blockquote title"}
{: #myid}

{:.ruby}
    Some code here