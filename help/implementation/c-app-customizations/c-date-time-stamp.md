---
description: Customize date and time stamps using Livefyre.js.
seo-description: Customize date and time stamps using Livefyre.js.
seo-title: Customize the Date and Time Stamp
solution: Experience Manager
title: Customize the Date and Time Stamp
uuid: 632ea405-56b7-4664-8d2b-0dd0a7611bd8
exl-id: 77130793-00ba-4a5c-8318-4221d971da6c
---
# Customize the Date and Time Stamp{#customize-the-date-and-time-stamp}

Customize date and time stamps using Livefyre.js.

Livefyre Apps provide the option parameter, datetimeFormat, to specify the date format as described below.

* [Terminology](#c_date_time_stamp/section_xsk_jn4_xz)
* [Formatting](#c_date_time_stamp/section_ynx_gn4_xz)
* [Symbol Designation](#c_date_time_stamp/section_inq_2n4_xz)

## Terminology {#section_xsk_jn4_xz}

* **Absolute Timestamps** are defined as exact and specific times (e.g. January 1, 2012 12:00pm)
* **Relative Timestamps** are defined as general and less precise times (e.g. 25 seconds ago, 14 minutes ago, 1 day ago, 1 year ago, etc.)

## Formatting {#section_ynx_gn4_xz}

The datetimeFormat parameter has the following default behavior when no argument is given:

* Datetime format of: MMMM d yyyy (for January 8, 2012)
* 20160 Minutes (14 days) until absolute time (14 days until relative timestamps become absolute timestamps)

The datetimeFormat parameter accepts three possible argument types: datetime, format, and string.

```
// Example 1 (Datetime format string)  
var convConfig = { 
   "collectionMeta":"eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJ0aXRsZSI6InBvc3QgMiIsInVybCI6Imh0dHA6XC9cL29yYW5nZXNhcmVncmVhdC5jb21cL3VzZWExcDcwXzEyXC8_cD01IiwidGFncyI6IiIsImNoZWNrc3VtIjoiYjBiYzRkMmVmY2UyZWZkYzZkYTE4NmQ2ZGZhNmVkYzAiLCJhcnRpY2xlSWQiOjV9.XZJTJgwpiFZCQ6dv8vvl91sMbFSJndzZPTHhmtOaImo", 
   "checksum":"b0bc4d2efce2efdc6da186d6dfa6edc", 
   "siteId":"12345", 
   "articleId":5, 
   "el":"comments1", 
   "datetimeFormat": 'MMM d y Ka' 
}; 
var conv = fyre.conv.load(networkConfig, [convConfig]);
```

An object specifying absoluteFormat and/or minutesUntilAbsoluteTime. A minutesUntilAbsoluteTime with a value of -1 will make the time absolute time immediate.

```
// Example 2 (Object)  
var convConfig = { 
   "collectionMeta":"eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJ0aXRsZSI6InBvc3QgMiIsInVybCI6Imh0dHA6XC9cL29yYW5nZXNhcmVncmVhdC5jb21cL3VzZWExcDcwXzEyXC8_cD01IiwidGFncyI6IiIsImNoZWNrc3VtIjoiYjBiYzRkMmVmY2UyZWZkYzZkYTE4NmQ2ZGZhNmVkYzAiLCJhcnRpY2xlSWQiOjV9.XZJTJgwpiFZCQ6dv8vvl91sMbFSJndzZPTHhmtOaImo", 
   "checksum":"b0bc4d2efce2efdc6da186d6dfa6edc", 
   "siteId":"12345", 
   "articleId":5, 
   "el":"comments1", 
   "datetimeFormat": { 
      minutesUntilAbsoluteTime: 10, 
      absoluteFormat: 'MMM d y Ka' 
   } 
};  
var conv = fyre.conv.load(networkConfig, [convConfig]);
```

A function that takes as argument a Date object and returns a datetime string to be displayed

```
// Example 3 (Function accepting a Date object, returning a datetime string to display) 
var convConfig = { 
   "collectionMeta":"eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJ0aXRsZSI6InBvc3QgMiIsInVybCI6Imh0dHA6XC9cL29yYW5nZXNhcmVncmVhdC5jb21cL3VzZWExcDcwXzEyXC8_cD01IiwidGFncyI6IiIsImNoZWNrc3VtIjoiYjBiYzRkMmVmY2UyZWZkYzZkYTE4NmQ2ZGZhNmVkYzAiLCJhcnRpY2xlSWQiOjV9.XZJTJgwpiFZCQ6dv8vvl91sMbFSJndzZPTHhmtOaImo", 
   "checksum":"b0bc4d2efce2efdc6da186d6dfa6edc", 
   "siteId":"12345", 
   "articleId":5, 
   "el":"comments1", 
   "datetimeFormat": function(theDateInput) { 
      return +theDateInput; 
   } 
};  
var conv = fyre.conv.load(networkConfig, [convConfig]);
```

## Symbol Designation {#section_inq_2n4_xz}

Datetime formatting functions following the pattern specification as defined in JDK, ICU and CLDR, with minor modification for typical usage in JS. For more information, see the [Google Closure Library Documentation](https://developers.google.com/closure/library/docs/overview).

```
  Symbol Meaning Presentation        Example 
  ------   -------                 ------------        ------- 
  G        era designator          (Text)              AD 
  y#       year                    (Number)            1996 
  Y* year (week of year)     (Number)            1997 
  u* extended year           (Number)            4601 
  M        month in year           (Text & Number)     July & 07 
  d        day in month            (Number)            10 
  h        hour in am/pm (1~12)    (Number)            12 
  H        hour in day (0~23)      (Number)            0 
  m        minute in hour          (Number)            30 
  s        second in minute        (Number)            55 
  S        fractional second       (Number)            978 
  E        day of week             (Text)              Tuesday 
  e* day of week (local 1~7) (Number)            2 
  D* day in year             (Number)            189 
  F* day of week in month    (Number)            2 (2nd Wed in July) 
  w* week in year            (Number)            27 
  W* week in month           (Number)            2 
  a        am/pm marker            (Text)              PM 
  k        hour in day (1~24)      (Number)            24 
  K        hour in am/pm (0~11)    (Number)            0 
  z        time zone               (Text)              Pacific Standard Time 
  Z        time zone (RFC 822)     (Number)            -0800 
  v        time zone (generic)     (Text)              Pacific Time 
  g* Julian day              (Number)            2451334 
  A* milliseconds in day     (Number)            69540000 
  '        escape for text         (Delimiter)         'Date=' 
  ''       single quote            (Literal)           'o''clock'
```

Items marked with ‘&#42;’ are not yet supported.

Items marked with ‘#’ work differently than Java.

The count of pattern letters determine the format.

* **Text:** 4 or more, use full form. Fewer than 4, use short or abbreviated form if it exists. (For example: “EEEE” produces “Monday”, “EEE” produces “Mon”.)
* **Number:** the minimum number of digits. Shorter numbers are zero-padded to this amount (For example: If “m” produces “6”, “mm” produces “06”.). Year is handled specially; that is, if the count of ‘y’ is 2, the Year will be truncated to 2 digits. (For example: if “yyyy” produces “1997”, “yy” produces “97”.) Unlike other fields, fractional seconds are padded on the right with zero.
* **Text & Number:** 3 or over, use text. Fewer than 3, use number. (For example: “M” produces “1”, “MM” produces “01”, “MMM” produces “Jan”, and “MMMM” produces “January”.)

Any characters in the pattern that are not in the ranges of [‘a’..’z’] and [‘A’..’Z’] will be treated as quoted text. For instance, characters like ‘:’, ‘.’, ‘ ‘, ‘#’ and ‘@’ will appear in the resulting time text even they are not embraced within single quotes.
