# Advance String Templating
Advance String Template with conditional statement similar to smarty and twig.

> Initialling the class
```
$template = new StringTemplating();
```
> Methods
```
$template->assign("car", "peugeot");
$template->assign("x", 10);
```
> Acceptable condition tags
- {if $car == peugeot} 
- {elseif $x > 7}
- {else}
- {/if}  

> Acceptable operators

>, <, >=, <=, ==, !=

## Example
```
$stringToFormat = 'I love watching $car Cars. 
{if $type == 1} Where are you now 
{elseif $type > 4} This is just a sample 
{else} Else will be ran {/if}';

$template = new StringTemplate();
$template->assign("type", 5);
$template->assign("car", 'Toyota');
$formatted = $template->format($stringToFormat);

-- $formatted will return the following
/**
I love watching Toyota Cars. This is just a sample
**/
```

> Change Assign Value Format

You can change the assign value symbol used in the string. e.g instead of using $car you can use @@car@@ or {{car}} by changing the start and end replace string public method of the class.
```
$template->$start_replace_string = "@@";
$template->$end_replace_string = "@@";
```
