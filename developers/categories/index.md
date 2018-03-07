# Title: Categories
<!-- Position: 5 -->
---
Snippet code to work with categories.

<div class="note">
By default, the database of categories is alphanumeric sorted.
</div>

## List all categories

```
<?php
	$categories = getCategories();

	foreach ($categories as $category) {
		// Each category is an Category-Object
		echo 'Category name: '	. $category->name();
		echo 'Category key: ' 	. $category->key();
		echo 'Category link: ' 	. $category->permalink();
		echo 'Category amount of pages: ' . count($category->pages());
	}
?>
```

## List only the categories that have pages

```
<?php
	$categories = getCategories();

	foreach ($categories as $category) {
		// Each category is an Category-Object
		if (count($category->pages())>0) {
			echo 'Category name: '	. $category->name();
			echo 'Category key: ' 	. $category->key();
			echo 'Category link: ' 	. $category->permalink();
		}
	}
?>
```

## List all categories and the pages related to the category

```
<?php
	$categories = getCategories();

	foreach ($categories as $category) {
		// Each category is an Category-Object
		echo 'Category name: ' . $category->name();

		// The method $category->pages() returns all the pages keys releated to the category
		foreach ($category->pages() as $pageKey) {
			// buildPage function returns a Page-Object
			$page = buildPage($pageKey);

			echo '- Page title: ' . $page->title();
		}
	}
?>
```

## List all pages related to a category

```
<?php
        // Category key
        $categoryKey = 'example';

		// The category is an Category-Object
        $category = getCategory($categoryKey);

        // Print the category name
        echo 'Category name: ' . $category->name();

        // Print the pages title related to the category "example"
        foreach ($category->pages() as $pageKey) {
			// buildPage function returns a Page-Object
			$page = buildPage($pageKey);

			echo $page->title();
        }
?>
```

## Get active category

```
<?php
	// Check if the user is browsing a category
	if ($WHERE_AM_I=='category') {
		// Get the category key from the URL
		$categoryKey = $Url->slug();

		// Get the category name from the category key
		$categoryName = $dbCategories->getName($categoryKey);

		// Print the category name
		echo $categoryName;
	}
?>
```
