# Functional Programming for WordPress
## Dave Ross • @csixty4 • @10up
WordCamp Boston 2017
---
# Some History
## (because that's my thing)
---
# Imperitive Programming

```php
<?php

$colors = ['red', 'orange', 'yellow', 'green', 'blue'];

$colorIndex = 0;
outputColor:
	print "The color is $colors[$colorIndex]" . "\n";
	$colorIndex = $colorIndex + 1;
	if($colorIndex < count( $colors )) {
		goto outputColor;
	}
```
---
# Procedural (Structured) Programming
```php
<?php

function outputColor($color) {
	print "The color is $color" . "\n";
}

$colors = ['red', 'orange', 'yellow', 'green', 'blue'];

foreach($colors as $color) {
	outputColor( $color );
}
```
---
# Object-Oriented Programming
```php
<?php

class Color {
	function __construct( $color ) {
		$this->color = $color;
	}
    
	public function output() {
		print "The color is $this->color" . "\n";
	}
}

$colors = ['red', 'orange', 'yellow', 'green', 'blue'];

foreach($colors as $color) {
	$theColor = new Color( $color );
	$theColor->output();
}
```
---
# Functional Programming
```php

function getColors() {
	return new SplFixedArray::fromArray( ['red', 'orange', 'yellow', 'green', 'blue'] );
}

array_walk( getColors(), function( $color ) {
	print "The color is $color" . "\n";
} );
```
---
# Principles of Funcational Programming
* Referential transparency
* Minimal state
* No side effects