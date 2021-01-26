# [VALORANT Leaderboards API](https://playvalorant.com/en-us/leaderboards)

VALORANT's Leaderboards API used on the [website](https://playvalorant.com) and possibly in-game

# IMPORTANT NOTE:

- Different regions have different servers, hence each region has a slightly different URL. I will be using the example of APAC (or AP // Asia Pacific) server.

# Table of regions

| Region name   | Region code |
| ------------- | ----------- |
| North America | NA          |
| Europe        | EU          |
| Korea         | KR          |
| Brazil        | BR          |
| Asia Pacific  | AP          |
| Latin America | LATAM       |

# Getting Started

## URL Parameters
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

## Example Request

> Example uses AP region. This URL fetches the top 10 Radiants of AP region. You can change the region and startIndex to fine tune your results according to your liking

```
URL: https://dgxfkpkb4zk5c.cloudfront.net/leaderboards/affinity/AP/queue/competitive/act/97b6e739-44cc-ffa7-49ad-398ba502ceb0?startIndex=0&size=10
Request Type: GET
content-type: application/json
```

## Example Response

> Example uses AP region, the URL is the same as above. I am using [Insomnia API Client here](https://github.com/Kong/insomnia)

_Top 10 Radiants of AP region_
![Top 10 Radiants of AP as of January 21, 2021 2320 IST](img/ap-radiants-top10.png)

**If the URL gets broken or you face a problem, make sure to create an issue from the Issues tab**

# If someone from Riot Games is reading this...

_Hi there! First of all thanks for creating an amazing game, I love playing it. If this repo reveals some private information which it should not, please contact me at [haque.kashiful7@gmail.com](mailto:haque.kashiful7@gmail.com) or [@notifkash on Twitter](https://twitter.com/notifkash) and I will take this repo down. As far as I am concerned, this repo only shows the public API which is already used by [playvalorant.com Leaderboards](https://playvalorant.com/en-us/leaderboards)_
