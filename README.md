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

| Params     | Values                                                                                 |
| ---------- | -------------------------------------------------------------------------------------- |
| urlCode    | dgxfkpkb4zk5c (This seems like some kind of random seed, idk)                          |
| startIndex | 0 - 499 (for Radiants)                                                                 |
| startIndex | 500+ (for Immortals)                                                                   |
| size       | 10 (# of results to fetch, 10 is the max)                                              |
| apiKey     | 97b6e739-44cc-ffa7-49ad-398ba502ceb0 (I am assuming it is some kind of public API key) |

**Template URL:** `https://{urlCode}.cloudfront.net/leaderboards/affinity/{region}/queue/competitive/act/{apiKey}?startIndex={startIndex}&size={size}`

> Example uses AP region