## CDL website repository

 - Based on [sites template](https://github.com/rosedu/sites_template)

## How to code

 To be able to archive an edition, each `_data`, `_includes` and `_layouts` directory
 is split in folders per edition. In the `editions` directory are the former editions
 main content, like `index.html` and `assets`.


To add a new edition for the year 2017:

   - create a `editions` directory with the former edition year as name, ex: `editions/2016`
   - copy the `index.html` and `assets` to `editions/2016/`
   - create the content for the current year/edition name, in each folder: `_data`, `_includes` and `_layouts`.
     - `_data/2017/`
     - `_layouts/2017/default.yml`
     - `_includes/2017/`
   - change `index.html` to point to the new layout: `_layouts/2017/default.yml`, and other information: year, name etc.
   - copy the data files from the former edition to `_data/2017/*.yml`, make any necessary updates.
   - copy from `_includes/2016` to `_includes/2017` and change each inclusion and data to match this year's edition.


Example:

```
# File: _includes/2017/albums.html
   <section class="feature-columns row clearfix">
     {% for item in site.data.albums['2017'] %}
       {% include 2017/album_item.html %}
     {% endfor %}
```
