This module allows you to connect to coinmarketcap.com and use their API to retrieve data about a single or multiple cryptocurrencies

### How to Install:

```bash
npm install async-coinmarketcap-api
OR
yarn add async-coinmarketcap-api
```

### The module contains the following methods:

```bash
getCoinByName(name) - This method returns data about a single cryptocurrency.

(string) name - Return data for [name] 

getTopTenCoins(limit) - This method returns ten of the largest cryptocurrencies.

(int) limit - Return a maximum of [limit] results (default is 10, use 0 to return all results)
```

### Data Structure

```bash
Success:

{
    success: true,
    data: {
        id: String,
        name: String,
        symbol: String,
        rank: Int,
        price_usd: String,
        price_btc: String,
        market_cap_usd: Int,
        available_supply: Int,
        total_supply: Int,
        max_supply: Int,
        percent_change_1h:c String,
        percent_change_24h: String,
        percent_change_7d: String,
        last_updated: String,
    },
}

Error:

{
    success: false,
    data: {}
}
```

### How to Use

Once installed you can use it by first importing the functions from the module:

```bash
import { getCoinByName, getTopTenCoins } from 'async-coinmarketcap-api';
```

Then just call one of the functions and pass it an argument and some data should be returned.

For example, here is how i use the module together with my GraphQL server.

```bash
coinByName: (parent, { name }, context) => {
    return getCoinByName(name);
},
topTenCoins: (parent, { limit = 10 }, context) => {
    return getTopTenCoins(limit);
}
```

About
-----

**Type:** School project @[BTH](https://www.bth.se/)  
**License:** MIT  
**Author:** [Zero2k](mailto:vibe16@student.bth.se)
