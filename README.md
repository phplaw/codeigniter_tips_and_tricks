# codeigniter_tips_and_tricks


From the end of `system/core/CodeIgniter.php` you will see this line that good for custome layout.    

```php
/*
 * ------------------------------------------------------
 *  Send the final rendered output to the browser
 * ------------------------------------------------------
 */
	if ($EXT->call_hook('display_override') === FALSE)
	{
		$OUT->_display();
	}
```

If you dont like using hook, you can look at this 
```
CodeIgniter has an output class that takes care of sending your final rendered data to the web browser automatically. More information on this can be found in the Views and Output Class pages. In some cases, however, you might want to post-process the finalized data in some way and send it to the browser yourself. CodeIgniter permits you to add a method named _output() to your controller that will receive the finalized output data.
```
### example
```php
public function _output($output)
{
        echo $output;
}
```
