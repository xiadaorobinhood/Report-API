Cloudmobi Report API User Guide
=== 

Catalog
=== 

* [Placement Report](#the-interface-of-placement-report) 

* [Country Report](#the-interface-of-country-report)

* [Note](#Note)

> You should apply to our operation manager for a token to access the interface in advance.

The Interface of Placement Report
===

* Description: We provide the interface of daily placement report.

* URL: http://www.cloudmobi.net/cloudmobi-reporting/index?t={token}&st={start time}&et={end time}

* E.g.: http://www.cloudmobi.net/cloudmobi-reporting/index?t={token}&st=2017-04-01&et=2017-04-03

* Definition of the Parameter:  

|  parameter | type | definition |
| :---: | :----: | :---: |
| token | string | the code for getting data |
|  st   | string | start time |
|  et   | string | end time |

* The response is in the format of JSON array

* Definition of response parameter 

|  parameter   |   type   |        definition        |
| :---: | :----: | :--------------: |
| error | string | error message (It’ll return empty string if response is correct.) |
| data  | array  |     the object of placement information      |

The objects of placement report:

|     parameter     |   type   |  definition   |
| :--------: | :----: | :---: |
|   app_id   | string | the given App id   |
|  slot_id   | string | Ad placement id |
|  revenue   | float  |  the earnings   |
|  request   | string |  the number of ad request  |
| impression | string |  the number of ad impression  |
|   click    | string |  the number of ad click  |
|    dau     | string |  daily active users    |
|  filled    | string |  the number of ad fill   |
|    day     | string |  date   |


E.g. (for reference only)

  ```json 
{
    "error": "",
    "data": [
        {
            "app_id": "1",
            "slot_id": "2",
            "revenue": 888,
            "request": "88888888",
            "impression": "88",
            "click": "8",
            "dau": "6",
            "filled": "100",
            "day": "2017-04-01"
        },...
    ]
}
  ```

[Back to TOC](#目录) 


The Interface of Country Report
=== 

* Description: We provide the interface of country report on a daily basis.

* URL: http://www.cloudmobi.net/cloudmobi-reporting/country-report?t={token}&st={start time}&et={end time}

* E.g.: http://www.cloudmobi.net/cloudmobi-reporting/country-report?t={token}&st=2017-04-01&et=2017-04-03

* Definition of the Parameter:  

|  parameter   |   type   |  definition   |
| :---: | :----: | :---: |
| token | string | the code for getting data |
|  st   | string | start time  |
|  et   | string | end time  |

* The response is in the format of JSON array

* Definition of response parameter 

|  parameter   |   type |        definition        |
| :---: | :----: | :--------------: |
| error | string | error message (It’ll return empty string if response is correct.) |
| data  | array  |     the object of placement information      |

The objects of placement report:

|      字段      |   类型   |   说明   |
| :----------: | :----: | :----: |
|    app_id    | string |  the given App id   |
|   slot_id    | string | Ad placement id  |
| country_name | string | country code defined by ISO 3166-1 |
|   revenue    | float  |   the earnings   |
|   request    | string |  the number of ad request   |
|  impression  | string |  the number of ad impression   |
|    click     | string |  the number of ad click   |
|  dau       | string |  daily active users    |
|  filled    | string |  the number of ad fill   |
|     day      | string |   date |


E.g. (for reference only)

  ```json 
{
    "error": "",
    "data": [
        {
            "app_id": "1",
            "slot_id": "2",
            "country_name": "CN",
            "revenue": 888,
            "request": "88888888",
            "impression": "88",
            "click": "8",
            "dau": "6",
            "filled": "100",
            "day": "2017-04-01"
        },...
    ]
}
  ```
Note
===
* The time range should not exceed 7 days and only data in the last 90 days will be available.
* All the data provided is based on UTC 0 time zone.
* Data on that very day will be accurate at 7 a.m. next day (UTC T+1 7:00 AM), peculiar circumstance exception.
