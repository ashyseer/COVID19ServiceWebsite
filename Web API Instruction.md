## Web API

| 类型 |             URL             |                 功能介绍                  |        参数        |         返回值          |
| :--: | :-------------------------: | :---------------------------------------: | :----------------: | :---------------------: |
| GET  | api/map/country/certainDay  |        获取特定日期的全国疫情数据         |        date        |    Province (Object)    |
| GET  | api/map/country/timeSeries  |         返回全国时间序列疫情数据          |         无         | List\<Province> (Array) |
| GET  |      api/map/province       |       获取特定日期特定省的疫情数据        | provinceName, date |    Province (Object)    |
| GET  | api/map/province/timeSeries | 获取特定省的时间序列疫情数据（1.25-3.31） |    provinceName    | List\<Province> (Array) |
| GET  | api/map/province/certainDay |       获取特定日期所有省的疫情数据        |        date        | List\<Province> (Array) |
| GET  |   api/map/province/top10    |   获取特定日期特定条件下top10省疫情数据   |     key, date      | List\<Province> (Array) |
| GET  |        api/map/city         |       获取特定日期特定市的疫情数据        |   cityName, date   |      City (Object)      |
| GET  |   api/map/city/timeSeries   | 获取特定市的时间序列疫情数据（1.25-3.31） |      cityName      |   List\<City> (Array)   |
| GET  |   api/map/city/certainDay   |       获取特定日期所有省的疫情数据        |        date        |   List\<City> (Array)   |

### Web API示例

- URL: /api/map/province?provinceName=湖北&&date=2020/2/4

  Response Type: application/json

  Response:

  ```json
  {
      "countryName":"中国",
      "id":575,
      "provinceShortName":"湖北",
      "currentConfirmedCount":0,
      "confirmedCount":16678,
      "suspectedCount":0,
      "curedCount":522,
      "deadCount":479,
      "cities":null,
      "updateTime":1580859411761,
      "date":"2020/2/4"
  }
  ```

- URL: /api/map/country?certainDay=2020/3/14

  Response Type: application/json

  Response:

  ```json
  {
      "countryName":"中国",
      "id":2296,
      "provinceShortName":"中国",
      "currentConfirmedCount":12159,
      "confirmedCount":81033,
      "suspectedCount":95,
      "curedCount":65680,
      "deadCount":3194,
      "cities":null,
      "updateTime":1584230262402,
      "date":"2020/3/14"
  }
  ```

- URL: /api/map/province/top10?key=累计确诊&&date=2020/2/4

  Response Type: application/json

  Optional Keys: '累计确诊'、'累计死亡'、'累计治愈'、‘当前确诊''
