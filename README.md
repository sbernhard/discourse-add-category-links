# discourse-add-category-links theme component

This component scans the **full** description of a category for given tags and
display the additional links to categories. See screenshot.

![Screenshot](https://github.com/sbernhard/discourse-add-category-links/blob/master/screenshot.jpeg)

It can also display the links of a parent category in its child categories. 
This can be configured. 

## Why should I use it and why is it implemented like this?

You want to display additional links to e.g. other resources of this type of category.
Think about a category for a soccer club and you want to add the link to the website of the club.
In such cases, you can use a https://github.com/naidihr/discourse-category-headers.git

If you have more than one link, and/or you don't want that link to appear in the categories overview site,
and/or you don't want that huge banner, you can use this theme.

It's implemented like this to parse the **full** description of a category because discourse
only uses the first fragment of the "first topic post" to create the category description 
which is dislayed in the categories overview site. The rest of the post isn't shown. 

In case you are using a lot of categories, maybe created using a API, this additon is 
fully usable as the category first post (= the full description) can be set via API, too.

## To get it working

Configure the theme component and set the tags, like

    WIKI, blank

Change the description of a category so that it looks like this

    This is the displayed category description.


    `
    {AddCategoryLinks}
    {WIKI#Wiki#Our awesome wiki#https://awesome-wiki-which-doesnt.exist}
    {TAGNAME#Link Name#Link Title#Link URL}
    `

Please note

- Its important that `{AddCategoryLinks}` exists in the description.
- ``Its important that its within a code block (within `...`).``
- Use # as a separator.


**Note:** I would recommend to hide the post in which the description
of a category is written down so that users don't see the 
<code>AddCategoryLinks</code> etc. additions.

## Thank you

- discourse, a great tool
- https://github.com/discourse/discourse-custom-header-links.git 
- https://github.com/discourse/discourse-category-headers.git
