# [VALORANT Leaderboards API](https://playvalorant.com/en-us/leaderboards)

VALORANT's Leaderboards API used on the [website](https://playvalorant.com) and possibly in-game

# Regions

| Region name   | Region code |
| ------------- | ----------- |
| North America | NA          |
| Europe        | EU          |
| Korea         | KR          |
| Brazil        | BR          |
| Asia Pacific  | AP          |
| Latin America | LATAM       |

# Getting Started

### URL Parameters
> Replace the {param} in the Template URL with the value given in the table below, See Example Request below

**Template URL:** `https://dgxfkpkb4zk5c.cloudfront.net/leaderboards/affinity/{region}/queue/competitive/act/{actId}?startIndex={startIndex}&size={size}`

| Params     | Values                    |
| ---------- | ------------------------- |
| region     | NA, EU, KR, BR, AP, LATAM |
| startIndex | 0 - 499 (for Radiants)    |
| startIndex | 500+ (for Immortals)      |
| size       | 10                        |
| actId      | See table below           |

| Episode 2 Act IDs (actId) | Values                               |
| ------------------------- | ------------------------------------ |
| Act 1 ID                  | 97b6e739-44cc-ffa7-49ad-398ba502ceb0 |
| Act 2 ID                  | ab57ef51-4e59-da91-cc8d-51a5a2b9b8ff |
| Act 3 ID                  | 52e9749a-429b-7060-99fe-4595426a0cf7 |

| Episode 3 Act IDs (actId) | Values                               |
| ------------------------- | ------------------------------------ |
| Act 1 ID                  | 2a27e5d2-4d30-c9e2-b15a-93b8909a442c |
| Act 2 ID                  | 4cb622e1-4244-6da3-7276-8daaf1c01be2 |
| Act 3 ID                  | a16955a5-4ad0-f761-5e9e-389df1c892fb |

| Episode 4 Act IDs (actId) | Values                               |
| ------------------------- | ------------------------------------ |
| Act 1 ID                  | 573f53ac-41a5-3a7d-d9ce-d6a6298e5704 |
| Act 2 ID                  | d929bc38-4ab6-7da4-94f0-ee84f8ac141e |
| Act 3 ID                  | 3e47230a-463c-a301-eb7d-67bb60357d4f |

| Episode 5 Act IDs (actId) | Values                               |
| ------------------------- | ------------------------------------ |
| Act 1 ID                  | 67e373c7-48f7-b422-641b-079ace30b427 |
| Act 2 ID                  | 7a85de9a-4032-61a9-61d8-f4aa2b4a84b6 |
| Act 3 ID                  | aca29595-40e4-01f5-3f35-b1b3d304c96e |

| Episode 6 Act IDs (actId) | Values                               |
| ------------------------- | ------------------------------------ |
| Act 1 ID                  | 9c91a445-4f78-1baa-a3ea-8f8aadf4914d |
| Act 2 ID                  | 34093c29-4306-43de-452f-3f944bde22be |
| Act 3 ID                  | 2de5423b-4aad-02ad-8d9b-c0a931958861 |

### Example Request

> Example uses AP region. This URL fetches the top 10 Radiants of AP region in Episode 2 Act 1. You can change the region and startIndex to fine tune your results according to your liking

```
URL: https://dgxfkpkb4zk5c.cloudfront.net/leaderboards/affinity/AP/queue/competitive/act/97b6e739-44cc-ffa7-49ad-398ba502ceb0?startIndex=0&size=10
Request Type: GET
content-type: application/json
```

#### Node.js example

```js
const axios = require('axios');

const options = {
  method: "GET",
  url: "https://dgxfkpkb4zk5c.cloudfront.net/leaderboards/affinity/NA/queue/competitive/act/67e373c7-48f7-b422-641b-079ace30b427",
  params: { startIndex: "0", size: "10" },
};

axios
  .request(options)
  .then(function (response) {
    console.log(response.data);
  })
  .catch(function (error) {
    console.error(error);
  });

```

#### Go example

```go
package main

import (
	"fmt"
	"io/ioutil"
	"net/http"
)

func main() {
	url := "https://dgxfkpkb4zk5c.cloudfront.net/leaderboards/affinity/NA/queue/competitive/act/67e373c7-48f7-b422-641b-079ace30b427?startIndex=0&size=10"
	req, _ := http.NewRequest("GET", url, nil)
	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(string(body))
}
```

#### Python3 Example

```python
import requests

url = "https://dgxfkpkb4zk5c.cloudfront.net/leaderboards/affinity/NA/queue/competitive/act/67e373c7-48f7-b422-641b-079ace30b427"
querystring = {"startIndex":"0","size":"10"}
response = requests.request("GET", url, params=querystring)

print(response.text)
```



#### 

### Example Response

> Example uses AP region, the URL is the same as above. I am using [Insomnia API Client here](https://github.com/Kong/insomnia)

_Top 10 Radiants of AP region_
![Top 10 Radiants of AP as of January 21, 2021 2320 IST](img/ap-radiants-top10.png)

**If the URL gets broken or you face a problem, make sure to create an issue from the Issues tab**

# If someone from Riot Games is reading this...

_Hi there! First of all thanks for creating an amazing game, I love playing it. If this repo reveals some private information, please contact me at [haque.kashiful7@gmail.com](mailto:haque.kashiful7@gmail.com) or [@notifkash on Twitter](https://twitter.com/notifkash) and I will take this repo down._
