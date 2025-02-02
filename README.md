# stonx-backend

Information aggregation for some of your assets.
Powers the [stonx-frontend](https://github.com/nicolaiort/stonx-frontend) dashboard.

Powered by (among many others):
* [Ts.ED](https://tsed.io)
* [TypeORM](https://typeorm.io/)
* [Axios](https://axios-http.com/)
* [PassportJS](https://www.passportjs.org/)

## Supported assets
> Warning: We currently save your bitpanda api keys in plaintext in our DB

* Bitpanda Wallets (Needs a bitpanda api token that can read your assets - scope "Guthaben")
* Bitpanda Indices (Needs a bitpanda api token that can read your assets - scope "Guthaben")
* Binance Spot Wallets (Needs a binance api token that can read your assets)
* ETH Wallets (Only needs the public key/address)
* BTC Wallets (Only needs the public key/address)
* DOGE Wallets (Only needs the public key/address)

### Balances and prices powered by:
* Bitpanda Assets and Prices: https://api.bitpanda.com
* Binance Assets and Prices: https://api.binance.com
* ETH Wallet Balances: https://api.etherscan.io
* BTC Wallet Balances: https://api.blockcypher.com/
* DOGE Wallet Balances: https://dogechain.info/
* Custom Wallet Prices: https://www.coingecko.com/api

## Roadmap
* Suport more Tokens and exchanges (if i have time)

## Configuration
> You can (or sometimes have to) use the following env vars to configure some parts of the backend
> This repository provides an .example.env file that contains all env vars

| Env var | Type | Optional | Default value | Description|
| - | - | - | - | - |
| JWT_SECRET | String | No | empty | The secret used by the backend to sign jwts - Should be at least 32bits (Max 512) |
| CURRENCY | String | No | empty | Your local currency string (Tested with EUR and USD) |
| ETHERSCAN_APIKEY | String | No | empty | An api key for etherscan - the backend uses etherscan to get the balance of erc20 wallets - You can get one for free [here](https://etherscan.io/apis) |
| ENABLE_SIGNUP | Boolan | Yes | true | Enable the aut/signup endpoint(true,default) or disable it |
| DATABASE_TYPE | String | No | `sqlite` | The type of the db that you want to use(currently supported: `sqlite`, `postgres`, `mysql`, `mariadb`) |
| DATABASE_NAME | String | No | `database.sql` | The name of the db that you want to use (filename for sqlite) |
| DATABASE_HOST | String | No | empty | The fqdn for the db's host (empty for sqlite) |
| DATABASE_PORT | String | No | empty | The port for the db's host (empty for sqlite) |
| DATABASE_USER | String | No | empty | The user to authenticate against the db (empty for sqlite) |
| DATABASE_PASSWORD | String | No | empty | The password to authenticate against the db (empty for sqlite) |

## Dev Setup 🛠
```bash
yarn
yarn dev
```
