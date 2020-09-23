<div align="center">

## MapQuest Link Generator


</div>

### Description

Provide your users with dynamically generated links to MapQuest using basic address, city, state, or zipcode strings with this simple function.
 
### More Info
 
address, city, state, zipcode, country

Call this function from anywhere in your PHP program. Pass-in address strings and get back the "&lt;a href" link to MapQuest.

"&lt;a href" style link to MapQuest map engine.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Steve Schoenfeld](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/steve-schoenfeld.md)
**Level**          |Intermediate
**User Rating**    |4.8 (19 globes from 4 users)
**Compatibility**  |PHP 3\.0, PHP 4\.0
**Category**       |[System Services/ Functions](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/system-services-functions__8-23.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/steve-schoenfeld-mapquest-link-generator__8-1229/archive/master.zip)





### Source Code

```
#
# Provide your users with dynamically generated links to MapQuest
# using basic address, city, state, or zipcode strings with this simple function.
#
# This function requires the Client address.
# Get the latest addres line requirements from MapQuest.
# Here's the latest as of August 31, 2006:
function generate_mapquest_link($address,$city,$state,$country,$zip)
{
	if ($country == "USA") $country="US";
	if ($country == "")  $country="US";
	if ($address > "" && $city > "" && $state > "" && $zip > "")
	{
		$address = trim($address);
		$address = str_replace(","," ",$address);
		$address = str_replace(" ","+",$address);
		#$address = str_replace(",","%2C",$address);
		$city  = trim($city);
		$city  = str_replace(" ","+",$city);
		$link="http://www.mapquest.com/maps/map.adp".
			"?country=$country".
			"&title=Map to RepleteMeeting Location".
			"&address=$address".
			"&city=$city".
			"&state=$state".
			"&zipcode=$zip".
			"&cid=lfmaplink";
	}
	else
		$link = "*** Address Not Specified ***";
	return $link;
}
```

