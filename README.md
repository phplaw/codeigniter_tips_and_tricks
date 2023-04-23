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
