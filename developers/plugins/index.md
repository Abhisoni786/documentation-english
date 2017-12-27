# Title: Plugins
<!-- Position: 10 -->
---
Snippet codes to work with plugins.

<div class="note">
The following codes work in Bludit > v2.1
</div>

## Check if a plugin is activated / enabled
```
<?php
	// Class name of the plugin
	$className = 'pluginRSS';

	if (pluginActivated($className)) {
		echo 'The plugin RSS is activated';
	}
?>
```

## Get a plugin, the function returns a plugin object
```
<?php
	// Class name of the plugin
	$className = 'pluginRSS';

	// Get the plugin object
	$plugin = getPlugin($className);

	// Print the plugin label
	echo $plugin->label();
?>
```

## Activate plugin
```
<?php
        // Class name of the plugin
        $className = 'pluginRSS';

	activatePlugin($className);
?>
```

## Deactivate plugin
```
<?php
        // Class name of the plugin
        $className = 'pluginRSS';

        deactivatePlugin($className);
?>
```

