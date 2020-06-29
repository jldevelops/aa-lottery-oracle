# aa-lottery-oracle
Daily draw base AA using oracle results

Deploy an AA with parameters of your choice, like this (all fields needed):
```
{
    base_aa: "YVHAIFMATQKCRDYUIQKGCMR4OZ6IKIUD",
    params: {
        entry: 10000,
        trigger_fee: 100,
        oracle: "FOPUBEUPBC6YLIQDLKL6EW775BMV7YOH",
        feed_name: "bitcoin_hash"
    }
}
```
Deployed on https://explorer.obyte.org/#RqP2ZePq/9mIErnCSlP9XOMoFu5dUjcTd+2cwnkh004=

Send bytes to aa adress `QZKNGJQTCI4WCS6FFXAZ4QQ55LPNMXDT` to buy tickets

Wait to next day (at 00:00 UTC) and trigger winner calculation to earn trigger reward (or lose 10 kbyte)

## Params
`entry` bytes for 1 ticket, min 10KB

`trigger_fee` part of entry which will go to user who triggered lottery calculation

`oracle` oracle to get results from

`feed_name` feed name to pick within oracle unit

## Usage
To participate, send `entry` amount or multiple

To trigger lottery winner calculation, send `trigger` = 1. If triggered, reward is paid, otherwise 10KB are lost and added to AA balance

To claim prize, send any amount of bytes after lottery calculation

A 5KB flat fee is charged to both winners, it is reduced to 0 bytes when aa balance reach 20KB
