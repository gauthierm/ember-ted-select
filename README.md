# Ember-ted-select

A data down, actions up select component rendered with real DOM elements.Supports disabled options, multi-select, option sorting and custom prompt.

## Installation

* `ember install ember-ted-select`

## Examples

### Standard Usage

You'll need to give `ted-select` an array of options (`content`), specifying a property to use for both option value and option label. A selection can be passed in (data down) using the `selected` property, and the add-on will send an `on-change` action out (actions-up)

````
{{ted-select
  selectClassNames="form-control"
  content=TEDevents
  optionValueKey="id"
  optionLabelKey="title"
  on-change=(action "update")
  selected=initialSelection
}}
````

### Demo and additional examples

Visit the [docs site](http://tedconf.github.io/ember-ted-select/) for demos and more detailed usage examples.


##Configurable options

<table class="table table-bordered">
  <thead>
    <tr>
      <th>Property</th>
      <th>Purpose</th>
      <th>Expected Type</th>
      <th>Default value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>content</code></td>
      <td>Pass in a content array to populate the select options.</td>
      <td>array</td>
      <td><code>null</code></td>
    </tr>
    <tr>
      <td><code>optionLabelKey</code></td>
      <td>[optional] Specify a property of the content object to use as each option's <code>value</code> attribute.</td>
      <td>string</td>
      <td><code>'id'</code></td>
    </tr>
    <tr>
      <td><code>optionValueKey</code></td>
      <td>[optional] Specify a property of the content object to use as each option's label.</td>
      <td>string</td>
      <td><code>'title'</code></td>
    </tr>
    <tr>
      <td><code>optionDisabledKey</code></td>
      <td>[optional] Specify a boolean property of the content object to use as a flag for the <code>disabled</code>attribute.</td>
      <td>string, null</td>
      <td><code>null</code></td>
    </tr>
    <tr>
      <td><code>on-change</code></td>
      <td>
        Specify your own named action to trigger when the select value changes. Standard usage is: <code>(action "update")</code>. Your action handler will receive the new value, as a single value for a standard select or as an array if <code>multiple</code> is active.<br>
        You can also force a two-way binding by using the [`mut` helper](http://emberjs.com/api/classes/Ember.Templates.helpers.html#method_mut). See <strong>two-way-bound</strong> for an example.
      </td>
      <td>Ember action</td>
      <td><code>Ember.K</code> (noop)</td>
    </tr>
    <tr>
      <td><code>selected</code></td>
      <td>
        Pass in an initial selection or update the selected value from outside the component. Must match one of the options in the content array for single select, or be an array of objects for multi-select.
      </td>
      <td>Object, Array</td>
      <td><code>null</code></td>
    </tr>
    <tr>
      <td><code>sortBy</code></td>
      <td>[optional] Specify a property of the content array to use for sorting the options. When set to null, options will remain in the order of the original array.</td>
      <td>string, null</td>
      <td><code>null</code></td>
    </tr>
    <tr>
      <td><code>multiple</code></td>
      <td>
        [optional] When <code>true</code>, adds the <code>multiple</code> attribute to the rendered <code>&lt;select&lt;</code>element.<br>
        When active, the <code>on-change</code> action will pass an array of objects rather than a single selected object.
      </td>
      <td>boolean</td>
      <td><code>false</code></td>
    </tr>
    <tr>
      <td><code>disabled</code></td>
      <td>[optional] Pass a boolean value in to disabled the entire input.</td>
      <td>boolean</td>
      <td><code>false</code></td>
    </tr>
    <tr>
      <td><code>selectClassNames</code></td>
      <td>Adds one or more custom class names to the select element. Pass multiple classes as a space separated list: <code>form-control My-select</code></td>
      <td>string, null</td>
      <td><code>null</code></td>
    </tr>
    <tr>
    </tr>
    <tr>
      <td><code>prompt</code></td>
      <td>[optional] String or <code>null</code>. Sets the prompt text or hides the prompt option when set to <code>null</code>.</td>
      <td>string, null</td>
      <td><code>'Select an item'</code></td>
    </tr>
  </tbody>
</table>


## Running a demo

* `git clone` this repository
* `npm install`
* `bower install`
* `ember server`
* Visit your app at http://localhost:4200.

## Running Tests

* `npm test` (Runs ember try:testall to test your addon against multiple Ember versions)

or to run a test server while developing:

* `ember test --server`

## Updating the GitHub pages docs site
* `ember github-pages:commit --message "update gh-pages"`
* `git push origin gh-pages`

## Building

* `ember build`

For more information on using ember-cli, visit [http://www.ember-cli.com/](http://www.ember-cli.com/).
