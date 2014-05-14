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


