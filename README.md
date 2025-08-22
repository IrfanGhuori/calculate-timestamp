# How to convert a timestamp to a time ago format in PHP 
## _timestamp and other date format calculable_

[![Behance](https://img.shields.io/badge/Behance-1769ff?logo=behance&logoColor=white)](https://behance.net/Irfan_Ghuori) [![Facebook](https://img.shields.io/badge/Facebook-%231877F2.svg?logo=Facebook&logoColor=white)](https://facebook.com/irfan.whitehead) [![LinkedIn](https://img.shields.io/badge/LinkedIn-%230077B5.svg?logo=linkedin&logoColor=white)](https://linkedin.com/in/irfan-ghuori-39b410155/) [![Pinterest](https://img.shields.io/badge/Pinterest-%23E60023.svg?logo=Pinterest&logoColor=white)](https://pinterest.com/irfanghuori_) 

# 💻 Tech Stack:
![PHP](https://img.shields.io/badge/php-%23777BB4.svg?style=for-the-badge&logo=php&logoColor=white) ![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E) ![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white) ![Apache Groovy](https://img.shields.io/badge/Apache%20Groovy-4298B8.svg?style=for-the-badge&logo=Apache+Groovy&logoColor=white) ![AssemblyScript](https://img.shields.io/badge/assembly%20script-%23000000.svg?style=for-the-badge&logo=assemblyscript&logoColor=white) ![Nodemon](https://img.shields.io/badge/NODEMON-%23323330.svg?style=for-the-badge&logo=nodemon&logoColor=%BBDEAD) ![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi) ![Xamarin](https://img.shields.io/badge/Xamarin-3199DC?style=for-the-badge&logo=xamarin&logoColor=white) ![Apache](https://img.shields.io/badge/apache-%23D42029.svg?style=for-the-badge&logo=apache&logoColor=white) ![Apache Airflow](https://img.shields.io/badge/Apache%20Airflow-017CEE?style=for-the-badge&logo=Apache%20Airflow&logoColor=white) ![MySQL](https://img.shields.io/badge/mysql-4479A1.svg?style=for-the-badge&logo=mysql&logoColor=white) ![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white) ![SQLite](https://img.shields.io/badge/sqlite-%2307405e.svg?style=for-the-badge&logo=sqlite&logoColor=white) ![Sequelize](https://img.shields.io/badge/Sequelize-52B0E7?style=for-the-badge&logo=Sequelize&logoColor=white) ![Adobe](https://img.shields.io/badge/adobe-%23FF0000.svg?style=for-the-badge&logo=adobe&logoColor=white) ![Adobe Illustrator](https://img.shields.io/badge/adobe%20illustrator-%23FF9A00.svg?style=for-the-badge&logo=adobe%20illustrator&logoColor=white) ![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white) ![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)

## Use example :
```sh
use in classes
private or public - function TimeAgo($startDate){...} 
$this->TimeAgo($package_row->enddate);

use in functions
$custome_date =  $row->created_at;
echo TimeAgo($custome_date);
```

Use in Laravel

{{ timeAgo($order->created_at) }}
```



## Simple Function :
```sh
function TimeAgo($time, $short = false){ 
    $SECOND = 1; 
    $MINUTE = 60 * $SECOND; 
    $HOUR = 60 * $MINUTE; 
    $DAY = 24 * $HOUR; 
    $MONTH = 30 * $DAY; 
    $before = time() - $time; 
 
    if($before < 0){ 
        return "not yet"; 
    } 
 
    if($short){ 
        if($before < 1 * $MINUTE){ 
            return ($before <5) ? "just now" : $before . " ago"; 
        } 
 
        if($before < 2 * $MINUTE){ 
            return "1m ago"; 
        } 
 
        if($before < 45 * $MINUTE){ 
            return floor($before / 60) . "m ago"; 
        } 
 
        if($before < 90 * $MINUTE){ 
            return "1h ago"; 
        } 
 
        if($before < 24 * $HOUR){ 
            return floor($before / 60 / 60). "h ago"; 
        } 
 
        if($before < 48 * $HOUR){ 
            return "1d ago"; 
        } 
 
        if($before < 30 * $DAY){ 
            return floor($before / 60 / 60 / 24) . "d ago"; 
        } 
 
        if($before < 12 * $MONTH){ 
            $months = floor($before / 60 / 60 / 24 / 30); 
            return $months <= 1 ? "1mo ago" : $months . "mo ago"; 
        }else{ 
            $years = floor  ($before / 60 / 60 / 24 / 30 / 12); 
            return $years <= 1 ? "1y ago" : $years."y ago"; 
        } 
    } 
 
    if($before < 1 * $MINUTE){ 
        return ($before <= 1) ? "just now" : $before . " seconds ago"; 
    } 
 
    if($before < 2 * $MINUTE){ 
        return "a minute ago"; 
    } 
 
    if($before < 45 * $MINUTE){ 
        return floor($before / 60) . " minutes ago"; 
    } 
 
    if($before < 90 * $MINUTE){ 
        return "an hour ago"; 
    } 
 
    if($before < 24 * $HOUR){ 
        return (floor($before / 60 / 60) == 1 ? 'about an hour' : floor($before / 60 / 60).' hours'). " ago"; 
    } 
 
    if($before < 48 * $HOUR){ 
        return "yesterday"; 
    } 
 
    if($before < 30 * $DAY){ 
        return floor($before / 60 / 60 / 24) . " days ago"; 
    } 
 
    if($before < 12 * $MONTH){ 
        $months = floor($before / 60 / 60 / 24 / 30); 
        return $months <= 1 ? "one month ago" : $months . " months ago"; 
    }else{ 
        $years = floor  ($before / 60 / 60 / 24 / 30 / 12); 
        return $years <= 1 ? "one year ago" : $years." years ago"; 
    } 
 
    return "$time"; 
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

  ## 💰 You can help me by Donating
  [![BuyMeACoffee](https://img.shields.io/badge/Buy%20Me%20a%20Coffee-ffdd00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](https://buymeacoffee.com/irfanghuori) 

  

