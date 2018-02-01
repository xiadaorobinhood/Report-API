> We provide the interface of slot&country report on a daily basis  
> You should apply to our operation manager for a token to access the interface in advance.

* URL: http://www.cloudmobi.net/cloudmobi-reporting/get-data?t={token}&st={start_time}&et={end_time}&dimension={dimension}  
* E.g：http://www.cloudmobi.net/cloudmobi-reporting/get-data?t=XXXXXXXXXXXXXXXXXXXXXXXXXXX&st=2017-12-20&et=2017-12-21&dimension=country  

* Definition of the Parameter:  

|  parameter   |   type   |  definition   |
| :---: | :----: | :---: |
| token | string | token |
|  st   | string | start time  |
|  et   | string | end time  |
|dimension|string|slot:interface of slot；country:interface of country。|

* The response is in the format of JSON array

* Definition of response parameter 

|  parameter   |   type   |        definition        |
| :---: | :----: | :--------------: |
| error | string | error message (It’ll return empty string if response is correct.) |
| data  | array  |     the object of placement information      |

### The interface of slot report
> While dimension=slot，We provide the interface of slot  
> The parameter will be different depends on your slot category 

a、noraml slot

|  parameter   |   type   |        definition        |
| :--------: | :----: | :---: |
|   app_id   | string | app id  |
|  slot_id   | string | Ad placement id |
|  revenue   | float  |  the earnings   |
|  request   | string |  the number of ad request  |
| impression | string |  the number of ad impression  |
|   click    | string |  the number of ad click  |
|    dau     | string |  daily active users    |
|  filled    | string |   the number of ad fill   |
|    day     | string |  date   |

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

b、reward video & video  slot

|  parameter   |   type   |        definition        |
| :--------: | :----: | :---: |
|   app_id   | string | app id  |
|  slot_id   | string | Ad placement id |
|  revenue   | float  |  the earnings   |
|  request   | string |  the number of ad request  |
| impression | string |  the number of ad impression  |
|   complete   | string |  the number of ad complete  |
|    dau     | string |   daily active users    |
|  filled    | string |  the number of ad fill  |
|    day     | string |  date  |


### The Interface of Country Report  
> While dimension=slot，We provide the interface of country     
> The parameter will be different depends on your slot category。  
> The interface of country report will show all the country on each slot。
>  

a、normal slot 

|  parameter   |   type   |        definition        |
| :--------: | :----: | :---: |
|   app_id   | string | app id  |
|  slot_id   | string | Ad placement id |
|  revenue   | float  |  the earnings   |
| country_name | string | country code defined by ISO 3166-1|
|  request   | string |  the number of ad request  |
| impression | string |  the number of ad impression  |
|   click    | string |  the number of ad click  |
|    dau     | string |  daily active users    |
|  filled    | string |   the number of ad fill   |
|    day     | string |  date   |

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
            "country_name": "CN",
        },...
    ]
}
  ```  
b、reward video & video  slot 

|  parameter   |   type   |        definition        |
| :--------: | :----: | :---: |
|   app_id   | string | app id  |
|  slot_id   | string | Ad placement id |
|  revenue   | float  |  the earnings   |
| country_name | string | country code defined by ISO 3166-1|
|  request   | string |  the number of ad request  |
| impression | string |  the number of ad impression  |
|   complete   | string |  the number of ad complete  |
|    dau     | string |   daily active users    |
|  filled    | string |  the number of ad fill  |
|    day     | string |  date  |

## Note
* The time range should not exceed 7 days and only data in the last 90 days will be available.  
* All the data provided is based on UTC 0 time zone.  
* Data on that very day will be accurate at 7 a.m. next day (UTC T+1 7:00 AM), peculiar circumstance exception.  
