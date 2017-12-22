# Cloudmobi Report API V2使用指南

> ssp平台提供slot层级和country层级报表按日拉取接口  
> 需要向ssp平台管理人员申请token才能访问接口
> 后续的升级和维护过程中，可能会在原有字段的基础上添加新字段，我方会提前通知，但也请您做好对应的容错机制





* URL: http://www.cloudmobi.net/cloudmobi-reporting/get-data?t={token}&st={start_time}&et={end_time}&dimension={dimension}  
* URL示例：http://www.cloudmobi.net/cloudmobi-reporting/get-data?t=XXXXXXXXXXXXXXXXXXXXXXXXXXX&st=2017-12-20&et=2017-12-21&dimension=country  

* URL参数释义:  

|  字段   |   类型   |  说明   |
| :---: | :----: | :---: |
| token | string | token |
|  st   | string | 起始时间  |
|  et   | string | 截止时间  |
|dimension|string|slot:广告位维度；country:国家维度。|

* 响应结果为**JSON数组**格式

* 响应结果字段列表 

|  字段   |   类型   |        说明        |
| :---: | :----: | :--------------: |
| error | string | 错误提示信息(成功返回空字符串) |
| data  | array  |     广告位信息对象      |

### slot层级
> dimension=slot时，返回slot层级的广告数据  
> 根据广告类型的不同，返回数据的字段有所不同，请根据自己所接入的广告类型获取相应的数据 

a、普通类型slot字段

|     字段     |   类型   |  说明   |
| :--------: | :----: | :---: |
|   app_id   | string | 应用id  |
|  slot_id   | string | 广告位id |
|  revenue   | float  |  收入   |
|  request   | string |  请求数  |
| impression | string |  展示数  |
|   click    | string |  点击数  |
|    dau     | string |  日活    |
|  filled    | string |  填充数  |
|    day     | string |  日期   |

响应结果示例(示例数据，仅供参考，后续slot与此类似，不再重复展示)  

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

b、激励视频广告slot返回字段

|     字段     |   类型   |  说明   |
| :--------: | :----: | :---: |
|   app_id   | string | 应用id  |
|  slot_id   | string | 广告位id |
|  revenue   | float  |  收入   |
|  request   | string |  请求数  |
| impression | string |  展示数  |
|   complete   | string |  完成数  |
|    dau     | string |  日活    |
|  filled    | string |  填充数  |
|    day     | string |  日期   |

c、视频广告slot返回字段（与激励视频一致）  

### country层级  
> dimension=country时，返回country层级的广告数据。  
> 根据广告类型的不同，返回数据的字段有所不同，请根据自己所接入的广告类型获取相应的数据。  
> country层级会将每个slot在每个国家的数据分解展示。
> 相较于slot层级，在对应广告类型上，country层级多一个 country_name字段。  

a、普通广告位country层级信息对象:

|      字段      |   类型   |   说明   |
| :----------: | :----: | :----: |
|    app_id    | string |  应用id  |
|   slot_id    | string | 广告位id  |
| country_name | string | 国家国际代码 |
|   revenue    | float  |   收入   |
|   request    | string |  请求数   |
|  impression  | string |  展示数   |
|    click     | string |  点击数   |
|  dau       | string |  日活    |
|  filled    | string |  填充数  |
|     day      | string |   日期   |

响应结果示例(示例数据，仅供参考)

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
b、其他广告位country层级信息对象:  
> 请参照对应slot层级广告对象，在其中增加country_name字段即可  



## 注意事项
* 数据拉取的时间范围不能超过7天（超过七天会返回错误），且只能查询最近90天的数据
* 所有报表数据以UTC 0时区统计
* 接口中返回的当日数据均不准确，在UTC 0时区 下一天的上午七点（UTC  T+1 7:00 AM）以后可取到准确数据，特殊情况除外。
