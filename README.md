# aa-lottery-oracle
Daily draw base AA using oracle results

Deploy an AA with parameters of your choice, like this (all fields needed):
```
{
    base_aa: "PCB4VYAJNH3CLHMN5BRQD4EZSOW4PBCG",
    params: {
        entry: 1000000,
        trigger_fee: 10000,
        oracle: "FOPUBEUPBC6YLIQDLKL6EW775BMV7YOH",
        feed_name: "bitcoin_hash"
    }
}
```

Send bytes to aa adress to buy tickets

Wait to next day (at 00:00 UTC) and trigger winner calculation to earn trigger_fee bytes (or lose 10 kbyte)

## Params
`entry` bytes for 1 ticket, min 10KB

`trigger_fee` part of entry which will go to user who triggered lottery calculation

`oracle` oracle to get results from

`feed_name` feed name to pick within oracle unit

## Usage
To participate, send `entry` amount or multiple

To trigger lottery calculation, send `trigger` = 1. If triggered, reward is paid, otherwise 10KB are added to aa balance

To claim reward, send any amount of bytes after lottery calculation

A 5KB flat fee is charged to both winners, it is reduced to 0 bytes when aa balance reach 20KB
