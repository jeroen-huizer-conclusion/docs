---
title: "Input reference set selector"
space: "Mendix 7 Reference Guide"
parent: "input-widgets"
---


The input reference set selector is an [input widget](input-widgets) that can be used to display and edit [associations](associations) for which the multiplicity setting is configured to allow multiple parent objects to associate with multiple children. This type of association is also known as a reference set.

<div class="alert alert-info">{% markdown %}

![](attachments/16713883/16844008.jpg)
The multiplicity settings of an association can be found by double-clicking the association in the [domain model](domain-model).

{% endmarkdown %}</div><div class="alert alert-info">{% markdown %}

![](attachments/16713883/16844004.png)
This input reference set selector allows you to link a user to organizations.

{% endmarkdown %}</div>

When clicked, the input reference set selector will open a select page containing a widget with all possible objects that can be used to fill the association.

## General properties

### Select page

The select page determines which page is displayed when the input reference selector is clicked. This page can be used to select associated objects from the list of all possible objects. This page should contain a data grid, template grid or list view connected to the same entity as the input reference set selector.

If an input reference set selector is not editable under any circumstances, no select page is required.

See [Opening Pages](opening-pages). Note that opening select pages in content is prohibited.

<div class="alert alert-success">{% markdown %}

You can generate a new page to show by right-clicking the widget and selecting 'Generate select page...'.

{% endmarkdown %}</div>

## Selectable objects properties

### XPath constraint

With the XPath constraint you can add a manual constraint to limit the list of objects that can be selected. This XPath constraint will be added to the constraints that are generated by the [context mechanism](context-mechanism).

<div class="alert alert-info">{% markdown %}

The XPath constraint `[InStock = true()]` on a reference selector for products will ensure that only products that are in stock are selectable.

{% endmarkdown %}</div>

### Constrained by

An input reference set selector can be constrained by one or more paths. This is typically used to make one reference selector dependent on another. For example, in page where you can edit a user, an organization selector can be constrained by a country selector. After selecting a country, the organization selector is constrained by this country and shows only organizations linked to that country.

<div class="alert alert-info">{% markdown %}

![](attachments/16713883/16844007.jpg)

In the domain model the user has a reference association to country and a reference set association to organization. The third association, from country to organization, describes the relation between those two entities. Such a 'triangle' shaped part of the domain model is what makes constraining possible.

![](attachments/16713883/16844006.jpg)

The page has displays a reference selector for the reference to country and an input reference set selector for the reference set to organization. The latter is constrained by the path through the domain model that forms the triangle.

![](attachments/16713883/16844005.jpg)

{% endmarkdown %}</div>

## Data source properties

{% snippet Attribute+Path+Property.md %}

{% snippet Label+Property.md %}

## Editability properties

{% snippet Editable+Property.md %}

{% snippet Read+Only+Style.md %}

{% snippet Condition+Property.md %}

## Visibility properties

{% snippet Visibility+Property+With+Module+Roles+Simple.md %}

## Events properties

{% snippet On+Change+Event.md %}

## Common properties

{% snippet Name+Property.md %}

{% snippet Class+Property.md %}

{% snippet Style+Property.md %}

{% snippet Tab+index+Property.md %}

## Related articles

*   [Data view](data-view)
