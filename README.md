# pelican-readtime - A Read Time Plugin for Pelican Static Site Generator
=============================
An article estimated read time plugin for Pelican static site generator. After Pelican generated the content of each page, the plugin read through the generated HTML content and strip all the tags, count all the word, then utilize average human read speed to calculate the read time of each article. The read time is passed over to the 'content' object of the article so Jinja template can use it to display the read time on wherever appropriate.


Note: This is a revised version of [jmaister's readtime plugin](https://github.com/jmaister/readtime). I added some more comments and tweaked the code so it runs smoothly on Python 3.6

Usage
-----

This plugin only uses standard modules(re, html, math, etc), so no extra module installation like BeautifuSoup. To use it, just add the plugin name to the **pelicanconf.py** file.

    PLUGINS=[ ... , 'pelican-readtime']

Then you can put the following code in whichever template you what, like *article.html*. 

    {% if article.readtime %}
    <div><b>Read in {{article.readtime.minutes}} min.</b></div>
    {% endif %}


You can also add some styling to it like so:
    {% if article.readtime %}
    <span><p style="text-align:right; color:#aaaaaa; ">&nbsp Estimated read time: {{article.readtime.minutes}} min.</p></span>
    {% endif %}

An example can be found in my own blog [here](https://wayofnumbers.github.io/).
