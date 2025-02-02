---
title: Checkbox
linktitle: Checkbox
description: Input element that allows a user to select or deselect one or more options
---

## Usage

Checkboxes are commonly utilized in forms to gather user input,
 enabling them to choose one or multiple options from a list.
 
 #### Use checkboxes when:
 * Users can select multiple options from a list.
 * An explicit action must be taken to apply settings (e.g. confirmation that the user has read a document).

### Anatomy

![Checkbox anatomy](Checkbox-anatomy.png)

1\. *Heading* – Question or prompt.  
2\. *Checkbox* – The selection control.  
3\. *Checkbox label* – Text label associated with the checkbox.  
4\. *Description text* – Optional text field with further description.  
5\. *Tooltip* – Clicking questionmark will show text popup.

### Style

* Checkboxes should always have a connected label on the right side.

### Best Practices

* Deactivated choice boxes should be avoided.
 If an alternative is unavailable, it should be removed and an explenation should be given in text as to why the option is missing.

 ### Content guidelines

* Keep checkbox labels short and descriptive.
* Start all checkbox labels with a capital letter.
* Don't include punctuation after checkbox labels.

### Related

* If the user can only make a single selection from a list of options, use [radio buttons](../radio-buttons).
* For a more compact way of displaying multiple options with single selection, use a [dropdown menu](../dropdown).

{{% expandlarge id="configuration-asd" header="Configuration in Altinn Studio" %}}

Add a checkbox component from the left-side panel and select it. This will bring up the configuration panel for the component on the right-hand side (below image).

Texts can be added directly by clicking the `+` sign next to the field
 (creates a new [text resource](/app/development/ux/texts/#add-and-change-texts-in-an-application)), or you can click the magnifying glass to choose a pre-made one.

![Checkbox configuration in Altinn Studio](Checkbox-settings-anatomy.png)

#### 1. Component ID
Unique ID for each component. This comes pre-filled, but you can change the value as you like.

#### 2. Link to data model
If your app is connected to a [data model](/app/development/data/data-modeling#data-models), you can 

#### 3. Header
Question, prompt, or short description positioned above checkboxes.

#### 4. Description text
Text field that allows for more elaborate description of options. Displayed directly beneath component label.

#### 5. Tooltip
When filled in, a questionmark will be displayed next to the compoent label. Clicking the questionmark will display the text as a popup.
Can be used for clarification, examples, use cases, etc.

#### 6. Read-only
When checked: disables the checkbox (not recommended, see [best practices](#best-practices)).

#### 7. Required
When checked: Requires the user to make a selection.

#### 8. Adding checkboxes
There are two ways of adding checkboxes: manually and by using [code (options) lists](/app/development/data/options/).

***Manually adding checkboxes***: Choose "Manuelt", add a new checkbox (1), and add a label (2).

The checkbox comes with a pre-filled value (3) which is the data that is stored when the user makes a selection.
 The value can be changed as you like.
 If the compoent is connected to a data model, the value(s) must correspond with the data type (e.g. boolean, string, number) specified in the model.

![Manually adding options](manually-add-options.png)

1\. *Add checkbox* – Add a new checkbox.  
2\. *Label* – Descriptive label associated with the checkbox.   
3\. *Value* – The value (data) that will be sent when the user makes a selection.
  

***Adding checkboxes with code lists (options)***: Choose 'Kodeliste' and provide a code list (options) ID.

For options retrieved from files, the options ID is the filename (without the extension).
For more info about code lists/options, see [Connect the component to options](/app/development/data/options/#connect-the-component-to-options-code-list).

![Add options with codelist](add-options-with-codelist.png)
1\. *Codelist (options) ID* – ID identifying the code list.

#### 9. Pre-select
Pre-select one of the checkboxes by typing its index.
Type '0' to pre-select checkbox 1, type '1' for checkbox 2, etc.

{{% /expandlarge %}}

{{% expandlarge id="property-list" header="Properties" %}}

* [Table with component layout properties](../#expandable-components-code)
* [Page layout JSON schema](https://altinncdn.no/schemas/json/layout/layout.schema.v1.json)

---

#### `optionsId`
**Type**:  string  
**Description**:  Reference to connected options by ID.

---

#### `options`
**Type**:  array  
**Description**:  An array of options. Only relevant if no `optionsId` is set.

#### `options.label`
**Type**:  string  
**Description**:  The option label. Can be plain text or a text resource binding.

#### `options.value`
**Type**:  string  
**Description**:  The option value.

#### `options.description`
**Type**:  string  
**Description**:  A description of the option displayed in Radio- and Checkbox groups. Can be plain text or a text resource binding.

#### `options.helpText`
**Type**:  string  
**Description**:  A help text for the option displayed in Radio- and Checkbox groups. Can be plain text or a text resource binding.

---

#### `preselectedOptionIndex`
**Type**:  integer  
**Description**:  Sets a preselected index.  
**Example**: `0`, `1`

---

#### `secure`
**Type**:  boolean  
**Description**:  Boolean value indicating if the options should be instance aware. Defaults to false.

---

#### `source`
**Type**:  object  
**Description**:  Object to define a data model source to be used as the basis for options.

#### `source.group`
**Type**:  string  
**Description**:  The repeating group to base options on.  
**Example**: `"model.some.group"`

#### `source.label`
**Type**:  string  
**Description**:  Reference to a text resource to be used as the option label.  
**Example**: `"some.text.key"`

#### `source.value`
**Type**:  string  
**Description**:  Field in the group that should be used as the value.  
**Example**: `"model.some.group[{0}].someField"`

#### `source.description`
**Type**:  string  
**Description**:  A description of the option displayed in Radio- and Checkbox groups. Can be plain text or a text resource binding.  
**Example**: `"some.text.key"`, `"My Description"`

#### `source.helpText`
**Type**:  string  
**Description**:  A help text for the option displayed in Radio- and Checkbox groups. Can be plain text or a text resource binding.  
**Example**: `"some.text.key"`, `"My Help Text"`

---

#### `mapping`
**Type**:  object  
**Description**:  Optionally used to map options.  
**Example**: `{ "some.source.field": "key1", "some.other.source": "key2" }`

---

#### `layout`
**Type**:  string  
**Description**:  Define the layout style for the options.  
**Enum**: `column`, `row`, `table`

---

<!-- ### Properties Description -->

{{% /expandlarge %}}


{{% expandlarge id="examples" header="Examples" %}}

![JSON layout page with checkbox](checkbox-json-layout.png)

{{% /expandlarge %}}
