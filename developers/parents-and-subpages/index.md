# Title: Parents and Subpages
<!-- Position: 7 -->
---
<div class="note">
The following codes work in Bludit > v2.1
</div>

## Check if a page has subpages
```
<?php
	// The variable $page is an object Page
	if ($page->hasSubpages())) {
		echo 'The page has subpages';
	} else {
		echo 'The page has not subpages';
	}
?>
```

## List all subpages of a page
```
<?php
        // The variable $page is an object Page
        $subpages = $page->subpages();
        if (empty($subpages)) {
                echo 'The page has not subpages';
        } else {
        	foreach ($subpages as $pageKey) {
			$subpage = buildPage($pageKey);
			echo 'Title of subpage ' . $subpage->title();
		}
        }
?>
```

