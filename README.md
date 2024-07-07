# Show Remaining Time for Product expiry, services etc. easy to use 
## _timestamp and other date format calculable_

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)



## Use example :
```sh
use in classes
private function GetTimeLeft($startDate){...}
$this->GetTimeLeft($package_row->enddate);

use in functions
$custome_date =  date("Y-m-d h:i:s");
echo getTimeLeft(date);
```



## Simple Function :
```sh
function GetTimeLeft($startDate)
    {
        $now = new DateTime();
        $then = new DateTime($startDate);
        $timeLeft = 0;

        // Only calculate time left if $then is still a future date
        if ($now < $then) {
            $difference = $now->diff($then);

            $days = $difference->days;
            $hours = $difference->h;
            $minutes = $difference->i;

            if ($days > 1) {
                $timeLeft = $days . ' days';
            } elseif ($days == 1) {
                $timeLeft = $days . ' day';
            } elseif ($days < 1) {

                if ($hours > 1) {
                    $timeLeft = $hours . ' hours';
                } elseif ($hours == 1) {
                    $timeLeft = $hours . ' hour';
                } elseif ($hours < 1) {

                    if ($minutes > 1) {
                        $timeLeft = $minutes . ' minutes';
                    } elseif ($minutes == 1) {
                        $timeLeft = $minutes . ' minute';
                    } elseif ($minutes < 1) {
                        $timeLeft = 0;
                    }
                }
            }
        }
        return $timeLeft;
    }
```

| format | 	Description |
| ------ | ------ |
| D | A textual representation of a day (three letters) |
| j | The day of the month without leading zeros (1 to 31) |
| l (lowercase 'L') | - A full textual representation of a day |
| N | The ISO-8601 numeric representation of a day (1 for Monday, 7 for Sunday) |
| S | The English ordinal suffix for the day of the month (2 characters st, nd, rd or th. Works well with j) |
| w | A numeric representation of the day (0 for Sunday, 6 for Saturday) |
| z | The day of the year (from 0 through 365) |
| W | The ISO-8601 week number of year (weeks starting on Monday) |
| F | A full textual representation of a month (January through December) |
| m | A numeric representation of a month (from 01 to 12) |
| M | A short textual representation of a month (three letters) |
| n | A numeric representation of a month, without leading zeros (1 to 12) |
| t | The number of days in the given month |
| L | Whether it's a leap year (1 if it is a leap year, 0 otherwise) |
| o | The ISO-8601 year number |
| Y | A four digit representation of a year |
| y | A two digit representation of a year |
| a | Lowercase am or pm |
| A | Uppercase AM or PM |
| B | Swatch Internet time (000 to 999) |
| g | 12-hour format of an hour (1 to 12) |
| G | 24-hour format of an hour (0 to 23) |
| h | 12-hour format of an hour (01 to 12) |
| H | 24-hour format of an hour (00 to 23) |
| i | Minutes with leading zeros (00 to 59) |
| s | Seconds, with leading zeros (00 to 59) |
| u | Microseconds (added in PHP 5.2.2) |
| e | The timezone identifier (Examples: UTC, GMT, Atlantic/Azores) |
| I (capital i) | | Whether the date is in daylights savings time (1 if Daylight Savings Time, 0 otherwise) |
| O | Difference to Greenwich time (GMT)  in hours (Example: +0100) |
| P | Difference to Greenwich time (GMT)  in hours:minutes (added in PHP 5.1.3) |
| T | Timezone abbreviations (Examples: EST, MDT) |
| Z | Timezone offset in seconds. The offset for timezones west of UTC is negative (-43200 to 50400) |
| c | The ISO-8601 date (e.g. 2013-05-05T16:34:42+00:00) |
| r | The RFC 2822 formatted date (e.g. Fri, 12 Apr 2013 12:01:05 +0200) |
| U | The seconds since the Unix Epoch (January 1 1970 00:00:00 GMT) |
and the following predefined constants can also be used (available since PHP 5.1.0) |:

| format | 	Description |
| ------ | ------ |
| DATE_ATOM | Atom (example: 2013-04-12T15:52:01+00:00) |
| DATE_COOKIE | HTTP Cookies (example: Friday, 12-Apr-13 15:52:01 UTC) |
| DATE_ISO8601 | ISO-8601 (example: 2013-04-12T15:52:01+0000) |
| DATE_RFC822 | RFC 822 (example: Fri, 12 Apr 13 15:52:01 +0000) |
| DATE_RFC850 | RFC 850 (example: Friday, 12-Apr-13 15:52:01 UTC) |
| DATE_RFC1036 | RFC 1036 (example: Fri, 12 Apr 13 15:52:01 +0000) |
| DATE_RFC1123 | RFC 1123 (example: Fri, 12 Apr 2013 15:52:01 +0000) |
| DATE_RFC2822 | RFC 2822 (Fri, 12 Apr 2013 15:52:01 +0000) |
| DATE_RFC3339 | Same as DATE_ATOM (since PHP 5.1.3) |
| DATE_RSS | RSS (Fri, 12 Aug 2013 15:52:01 +0000) |
| DATE_W3C | World Wide Web Consortium (example 2013-04-12T15:52:01+00:00) |
timestamp	Optional. Specifies an integer Unix timestamp. Default is the current local time (time()) 

