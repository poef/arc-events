ARC: Ariadne Component Library 
========================= 

[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/Ariadne-CMS/arc-events/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/Ariadne-CMS/arc-events/?branch=master)
[![Latest Stable Version](https://poser.pugx.org/arc/events/v/stable.svg)](https://packagist.org/packages/arc/events)
[![Total Downloads](https://poser.pugx.org/arc/events/downloads.svg)](https://packagist.org/packages/arc/events)
[![Latest Unstable Version](https://poser.pugx.org/arc/events/v/unstable.svg)](https://packagist.org/packages/arc/events)
[![License](https://poser.pugx.org/arc/events/license.svg)](https://packagist.org/packages/arc/events)

A flexible component library for PHP
------------------------------------ 

The Ariadne Component Library is a spinoff from the Ariadne Web 
Application Framework and Content Management System 
[ http://www.ariadne-cms.org/ ]

arc/events contains
------------------
- [events](docs/events.md): W3C style event system, with a filesystem tree as the DOM

Example code:

```php
    \arc\events::cd('/foo/')->listen( 'onbeforesave', function( $event ) {
        return $event->preventDefault(); // don't allow saves in /foo/
    });

    $eventData = \arc\events::cd('/foo/bar/')->fire( 'onbeforesave' );
    if ( $eventData ) {
         // save something, but alas - it has been prevented by a listener
    }
```