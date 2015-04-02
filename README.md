PHP Simple HTML DOM Parser
==========================

This repository is a manual git clone from [SourceForge](https://informa.link/408de42d/PHP+Simple+HTML+DOM+Parser).

## Description, Requirements & Features
- A HTML DOM parser written in PHP+ which lets you manipulate HTML in a very easy way.
- Requires PHP 5+
- Supports invalid HTML
- Find tags on an HTML page with selectors, similar to [jQuery](https://informa.link/7202a21b/jQuery)
- Extract contents from HTML in a single line

## Download & Documents
- Download latest version from [Sourceforge](https://informa.link/27521ca2/PHP+Simple+HTML+DOM+Parser+-++Browse+Files+at+SourceForge.net)
- Read [Online Documentation](https://informa.link/90637cf1/PHP+Simple+HTML+DOM+Parser%3A+Manual)

## Quick Start
- How to get HTML elements
```php
// Create DOM from URL or file
$html = file_get_html('http://www.google.com/');

// Find all images 
foreach($html->find('img') as $element) 
       echo $element->src . '<br>';

// Find all links 
foreach($html->find('a') as $element) 
       echo $element->href . '<br>';
```

- How to modify HTML elements
```php
// Create DOM from string
$html = str_get_html('<div id="hello">Hello</div><div id="world">World</div>');

$html->find('div', 1)->class = 'bar';

$html->find('div[id=hello]', 0)->innertext = 'foo';

echo $html; // Output: <div id="hello">foo</div><div id="world" class="bar">World</div>
```

- Extract contents from HTML
```php
// Dump contents (without tags) from HTML
echo file_get_html('http://www.google.com/')->plaintext; 
```
- Scraping Slashdot!
```php
// Create DOM from URL
$html = file_get_html('http://slashdot.org/');

// Find all article blocks
foreach($html->find('div.article') as $article) {
    $item['title']     = $article->find('div.title', 0)->plaintext;
    $item['intro']    = $article->find('div.intro', 0)->plaintext;
    $item['details'] = $article->find('div.details', 0)->plaintext;
    $articles[] = $item;
}

print_r($articles);
```

## Feedback
- [Feature Request Tracker](https://informa.link/8bece642/PHP+Simple+HTML+DOM+Parser+%2F+Feature+Requests)
- [Bug Tracking System](https://informa.link/975c071f/PHP+Simple+HTML+DOM+Parser+%2F+Bugs)
- [Discussion Forums](https://informa.link/7006fc19/PHP+Simple+HTML+DOM+Parser+%2F+Discussion+%2F+Forums)

## Misc.
- Author: S.C. Chen (me578022@gmail.com)
- Original idea is from Jose Solorzano's [HTML Parser for PHP 4](https://informa.link/9d47d80d/HTML+Parser+for+PHP-4)
- Contributions by: Yousuke Kumakura (Attribute Filters)
