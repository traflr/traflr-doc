##user
------
* register [POST]
..- email           valid email                     *required
..- username        string, 5-12                    *required
..- password        string, min 5                   *required
* login [POST]
..- email / username                string          *required
..- password                        string          *required
* forgot [POST]
..- email                           string          *required
* forgot/{hash code} [POST]
..- password                        string          *required
 
 
##trip {header : token}
----------
* create[POST]   
..* title           string                          *required
..* date            iso date (yyyy-mm-dd)           *required
..* location        double(longitude,latitude)      *required
* edit/{id}[GET]
* edit/{id}[POST]
..* title           string                          *required
..* date            iso date (yyyy-mm-dd)           *required
..* location        double(longitude,latitude)      *required      
* delete/{id}[GET]
 
 
##post {header : token}
--------
* create[POST]
..* trip_id         int valid trip id                       *required
..* time            iso date time (yyyy-mm-dd hh:ii:ss)     *required
..* coordinat       double long lat                         *required
..* caption         string                                  *required
* edit/{id}[GET]
* edit/{id}[POST]
..* time            iso date time (yyyy-mm-dd hh:ii:ss)     *required
..* coordinat       double long lat                         *required
..* caption         string                                  *required      
* delete/{id}[GET]
 
 
##feed
-----------
* trip/{page:optional => 0,1,2,3}[GET]
* user/{user_id}/{page:optional => 0,1,2,3}[GET]
* trip_detail/{trip_id}/{page:optional => 0,1,2,3}[GET]
 
 
##comment {header : token}
--------------
* trip/{id}/page/{page:optional => 0,1,2,3}[GET]
* trip/{id}[POST]
..* comment         string                                  *required
* trip/{id}/delete[GET]
* post/{id}/page/{page:optional => 0,1,2,3}[GET]
* post/{id}[POST]
..* comment         string                                  *required
* post/{id}/delete[GET]
 
 
##like {header : token}
---------------
* trip/{id}/page/{page:optional => 0,1,2,3}[GET]
* trip/{id}[POST]
* trip/{id}/delete[GET]
* post/{id}/page/{page:optional => 0,1,2,3}[GET]
* post/{id}[POST]
* post/{id}/delete[GET]


1. First ordered list item
2. Another item
⋅⋅* Unordered sub-list. 
1. Actual numbers don't matter, just that it's a number
⋅⋅1. Ordered sub-list
4. And another item.

⋅⋅⋅You can have properly indented paragraphs within list items. Notice the blank line above, and the leading spaces (at least one, but we'll use three here to also align the raw Markdown).

⋅⋅⋅To have a line break without a paragraph, you will need to use two trailing spaces.⋅⋅
⋅⋅⋅Note that this line is separate, but within the same paragraph.⋅⋅
⋅⋅⋅(This is contrary to the typical GFM line break behaviour, where trailing spaces are not required.)

* Unordered list can use asterisks
- Or minuses
+ Or pluses