<h1>Gravity Forms Sticky List</h1>

Sticky List is an Gravity Forms (for wordpress) add-on that lets you list and edit entries from the front end.

<h2>Description</h2>

#### Sticky List
Sticky List is a WordPress plugin for <a href="http://www.gravityforms.com/" target="_blank">Gravity Forms</a> that lets you list and edit entries from the front end.

**Note:** There is a bug in the Gravity Forms API that prevents Sticky List from working correctly. More information and fix, please see the FAQ section of this readme.

#### List Gravity Form entries on the front end

#### Edit Gravity Form entries from front end

#### Usage

1. Upload and activate the plugin
2. Go to the settings page of a form and click the Sticky List settings tab
3. Enable Sticky List for that form att choose your settings
4. Go to the form editor and select what fields should be displayed in the list
5. Put the shortcode in a page/post with the corresponding form id, i.e `[stickylist id="1"]`

#### Developers
This is the fully documented version of the plugin. This plugin is Open Source and pull requests are welcome.

**Note:** <a href="http://www.gravityforms.com/" target="_blank">Gravity Forms</a> is required for this plugin.

<h3>Installation</h3>

1. Upload extracted folder to the '/wp-content/plugins/' directory
2. Activate the plugin through the 'Plugins' menu in WordPress
3. Choose the required Sticky List settings on the individual form settings page.

<h3>Frequently Asked Questions</h3>

<h5>Question</h5>

Answer

<h5>Some fields do not get updated</h5>

There is a bug in the Gravity Forms api that prevent fields from getting saved in the entry. This will supposedly get fixed in Gravity Forms 1.9. In the meantime, download an <a href="https://downloads.wordpress.org/plugin/gravity-forms-sticky-form.1.0.1.zip">earlier version</a> of this plugin, (that uses a different way to save the entries) or apply the patch manually to `plugins/gravityforms/includes/api.php`

On line `510`, remove 
```PHP
if (empty($entry_id))
    $entry_id = $entry["id"];
```
and replace with
```PHP
if (empty($entry_id)) {
    $entry_id = $entry["id"];
}else{
    $entry["id"] = $entry_id;
}
```

<h3>Changelog</h3>

**1.0**
* Initial release
