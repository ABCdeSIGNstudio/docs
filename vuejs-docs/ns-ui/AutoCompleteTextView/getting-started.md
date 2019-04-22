---
title: Getting Started
page_title: RadAutoCompleteTextView Getting Started | Progress NativeScript UI Documentation
description: A getting started page for RadAutoCompleteTextView for Android. This article explains what are the steps to create a RadAutoCompleteTextView instance from scratch.
slug: autocomplete-gettingstarted-vue
tags: radautocompletetextview, gettingstarted, autocomplete, list, vue, nativescript, professional, ui
position: 1
publish: true
---

# RadAutoCompleteTextView Getting Started

In this article, you will learn how to initialize **RadAutoCompleteTextView** and use it with it's basic configuration inside an NativeScript + Vue applications.

## Installation
Run the following command to add the plugin to your application:

```
tns plugin add nativescript-ui-autocomplete
```

## Initialization
Before proceeding, make sure that the {% typedoc_link classes:NativeScriptUIAutoCompleteTextViewModule %} from the *nativescript-ui-autocomplete* plugin has been imported in the main JS in your app with the following sentences:

<snippet id='autocomplete-import-vue'/>

To create a functional **RadAutoCompleteTextView** you should:
- Place the RadAutoCompleteTextView tag in your component's template
- Once you have added it next you should specify the value for the {% typedoc_link classes:RadAutoCompleteTextView,member:items%} property. That property defines the collection of {% typedoc_link classes:TokenModel %} objects which will be used to provide suggestions on user input. The {% typedoc_link classes:TokenModel %} object is a data model used by the autocomplete to populate the suggestion view and the chosen items. Simply create a list of such objects in your component's code and bind it to the {% typedoc_link classes:RadAutoCompleteTextView,member:items%} property.
- Next you would like to specify the the suggestion list of the **RadAutoCompleteTextView** by adding an `SuggestionView` between the `RadAutoCompleteTextView` tags and setting the `~suggestionView` inline directive to it.
- All that is left is to specify the `v-template` of the of the {% typedoc_link classes:SuggestionView %} by adding an default Vue template structural directive between the `SuggestionView` tags.

First, lets create a `data.ts` file that generate the items used for autocompletion:

<snippet id='autocomplete-gettingstarted-data-vue'/>

So, if you create a new `MyPageWithAutocomplete.js` component which renders the whole page, you would need to add a code like this:

<snippet id='autocomplete-gettingstarted-vue'/>

The {% typedoc_link classes:SuggestionView,member:suggestionViewHeight%} property allows you to have control over the height of the suggestion view.
The `hint` property allows you to provide a text that will be displayed when there is no input.
The `text` property allows you to change the autocomplete text or get the current user input.
