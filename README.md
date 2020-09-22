<div align="center">

## Dir\_Size \- Recursively get the size of a directory


</div>

### Description

Uses recursion to scan a directory and all subdirectories to get the total size of all files residing within.
 
### More Info
 
The only parameter is the root directory.

Make sure you set $g_dirsize = 0; before calling the function a second time.

Returns the total size of the directory and all contents.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Daniel Green](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/daniel-green.md)
**Level**          |Intermediate
**User Rating**    |4.3 (13 globes from 3 users)
**Compatibility**  |PHP 4\.0
**Category**       |[Algorithims](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/algorithims__8-29.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/daniel-green-dir-size-recursively-get-the-size-of-a-directory__8-1186/archive/master.zip)





### Source Code

```
$g_dirsize = 0;
function dir_size($dir)
{
	global $g_dirsize;
	$handle = opendir($dir);
	while($file = readdir($handle))
	{
		if($file != "." && $file != "..")
		{
			if(is_dir($dir . "/" . $file))
			{
				dir_size($dir . "/" . $file);
			}else{
				$g_dirsize += filesize($dir . "/" . $file);
			}
		}
	}
	return($g_dirsize);
}
```

