# Title: Categories
<!-- Position: 5 -->
---
How to work with categories on your themes and plugins.

<div class="note">
<div class="title">Note</div>
By default, the database of categories is alphanumeric sorted.
</div>

## List all categories
<pre><code data-language="php"><?php
	// $dbCategories is the object who handle the categories
	foreach ($dbCategories->db as $key=>$fields) {
		echo 'Category name: ' . $fields['name'];
		echo 'Category key: ' . $key;
		echo 'Category link: ' . DOMAIN_CATEGORIES . $key;
		echo 'Category amount of items: ' . count($fields['list']);
	}
?></code></pre>

## List only the categories that have pages
<pre><code data-language="php"><?php
	// $dbCategories is the object who handle the categories
	foreach ($dbCategories->db as $key=>$fields) {
		if (count($fields['list']) > 0) {
			echo 'Category name: ' . $fields['name'];
			echo 'Category key: ' . $key;
			echo 'Category link: ' . DOMAIN_CATEGORIES . $key;
		}
	}
?></code></pre>

## List all categories and the pages linked to it
<pre><code data-language="php"><?php
	// $dbCategories is the object who handle the categories
	foreach ($dbCategories->db as $key=>$fields) {
		echo 'Category name: ' . $fields['name'];

		// The variable $fields['list'] contains all the pages key related to this category
		foreach ($fields['list'] as $pageKey) {
			$page = buildPage($pageKey);
			echo '- Page title: ' . $page->title();
		}
	}
?></code></pre>

## List all pages linked to a particular category
<pre><code data-language="php"><?phpi
        // Category key
        $categoryKey = 'example';

        // Get the map from the categories database object
        $category = $dbCategories->getMap($categoryKey);

        // Print the category name
        echo 'Category name: ' . $category['name'];

        // Print the pages title linked to the category "example"
        foreach ($category['list'] as $pageKey) {
                $page = buildPage($pageKey);
                echo $page->title();
        }
?></code></pre>

