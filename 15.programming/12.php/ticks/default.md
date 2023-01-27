---
title: declare
---

** Use case: Aggregate stats, so the total time in a function would be counted, including inside called functions.**

The declare construct is used to set execution directives for a block of code. The syntax of declare is similar to the syntax of other flow control constructs:

declare (directive)
    statement
https://www.php.net/manual/en/control-structures.declare.php

Example:

The event(s) that occur on each tick are specified using the register_tick_function(). See the example below for more details. Note that more than one event can occur for each tick.

<?php

declare(ticks=1);

// A function called on each tick event
function tick_handler()
{
    echo "tick_handler() called\n";
}

register_tick_function('tick_handler'); // causes a tick event

$a = 1; // causes a tick event

if ($a > 0) {
    $a += 2; // causes a tick event
    print($a); // causes a tick event
}

?>