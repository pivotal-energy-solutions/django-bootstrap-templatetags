django-bootstrap-templatetags
=============================

Utility templatetag library for minimizing Bootstrap scaffolding for verbose structures.

Add ``bootstrap_templatetags`` to your installed apps and then load up the library from a template!

**Be warned** that these tags do not exist in order to get wildly fancy and create some frankendjango.  These are provided to simplify some of the heavier Bootstrap scaffolding.  In most cases, care has been taken to not modify anything about how you would normally write your template; you simply replace the scaffolding with these tags and sub-tags.

If you need any more flexibility than what is being provided by the default, vanilla Bootstrap structures, you should actually write some Bootstrap markup and move on with your life :)

## Available tags

### Accordion
**Tag: ``{% bootstrap_accordion %}``**

Components:

* **``bootstrap_accordion``**
    * ``id`` (required): The DOM id for the accordion.
    * ``active_panel``: A 1-based index denoting the default expanded panel
    * Content should generally not be placed immediately after opening the tag.  Instead, move on to create the first ``{% group %}`` section.
* ``group``
    * ``heading`` (required): The markup that should appear inside of the clickable header's ``<a>`` tag.
    * Any content following a ``{% group %}`` tag will be inside of a content panel, until the next ``{% group %}`` is encountered or the whole tag ends.

Example:

```html
{% bootstrap_accordion id="my_accordion" %}
    {% group heading="First heading" %}
        First panel content
    {% group heading="Second heading" %}
        Second panel content
{% endbootstrap_accordion %}
```

