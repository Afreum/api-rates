# API QUERY LINKS: EXCHANGE RATES

Afreum provides a public exchange rate API that can be called remotely by developers building on top of the Afreum Ecosystem. This API is also used by the Afreum developer team in the upcoming Afreum 2.0 ecosystem upgrade. Developers who wish to build apps for the Afreum Ecosystem should use these API end points in production, rather than any of the Javascript scripts (used mainly for redundancy) provided that perform the same functions. The endpoints are as follows:

# 1. Universal Rates Query URL: https://afreum.com/ice/sites/app/api/rates.cfm

Use this endpoint to query the exchange rate of any Afreum token (e.g. AFR, AFRX, ANGN, AKES), any Stellar token supported by Afreum (e.g. XLM, USDC, yBTC), any external crypto supported by the Afreum Ecosystem (e.g. BTC, ETH, BUSD), and any fiat currency (USD, EUR, CHF) against each other. This makes the rates endpoint a powerful exchange rate system supporting over 1.2 million asset pairs. To use this endpoint you will need to get free or paid exchange rate keys, and also obtain a free API ACCESS KEY from Afreum. 

**URL Query Parameters:**

* **fiat_rates_api_key:** Get a free or paid API key from **https://exchangerate-api.com/**

* **crypto_rates_api_key:** Get a free or paid API key from **https://coinapi.io/**

* **base:** The asset code of the Stellar token, currency code of the fiat currency, or symbol of the cryptocurrency supported by Afreum Ecosystem for which you want to retrieve a price in the counter asset. E.g. **AFR, USD, BTC**

* **counter:** The asset code of the Stellar token, currency code of the fiat currency, or symbol of the cryptocurrency supported by Afreum Ecosystem in which you want to price the base asset. E.g. **AFR, EUR, ETH**

* **base_type:** Optional: The asset type of the Stellar asset if the base asset is a Stellar asset.
  
* **counter_type:** Optional: The asset type of the Stellar asset if the counter asset is a Stellar asset.
  
* **base_amount:** Optional: The amount of the base asset that you wish to exchange to the counter asset. The result will be the equivalent amount of the counter asset.   
  
**Query Response:** The endpoint will return either 0 for an invalid query, the rate of 1 base asset in the counter asset i.e. 1 BASE = ? COUNTER, or the total amount of the counter asset based on the amount of the base asset specified. The default response of the endpoint if you do not specify any parameters is AFR/USDC on Stellar. 


# 2. Stellar Rates Query URL: https://afreum.com/ice/sites/app/api/rates_stellar.cfm

Use this endpoint to query exchange rates between any Stellar asset supported by Afreum in any other Stellar asset supported by the Afreum ecosystem. Supported tokens include AFR, AFRX, flexible country tokens, stable country tokens, and 3rd party Stellar tokens such as XLM, USDC, BTC etc.

**URL Query Parameters:**

* **fiat_rates_api_key:** Get a free or paid API key from **https://exchangerate-api.com/**

* **crypto_rates_api_key:** Get a free or paid API key from **https://coinapi.io/**

* **base_asset_code:** The asset code of the Stellar token, fiat, or cryptocurrency supported by Afreum Ecosystem for which you want to retrieve a price in the counter asset. E.g. **AFR**
  
* **base_asset_issuer:** The asset issuer address of the Stellar token supported by Afreum Ecosystem for which you want to retrieve a price in the counter asset. E.g. **GBX6YI45VU7WNAAKA3RBFDR3I3UKNFHTJPQ5F6KOOKSGYIAM4TRQN54W**. This is always required for this endpoint.

* **counter_asset_code:** The asset code of the Stellar token supported by Afreum Ecosystem in which you want to price the base asset. E.g. **USDC**
  
* **counter_asset_issuer:** The asset issuer address of the Stellar token supported by Afreum Ecosystem in which you want to price the base asset. E.g. **GBX6YI45VU7WNAAKA3RBFDR3I3UKNFHTJPQ5F6KOOKSGYIAM4TRQN54W**. This is always required for this endpoint.
  
* **base_asset_amount:** The amount of the base asset exchanged into the counter asset. Default is 1. Use this parameter if you would like to return results for **n BASE = ? COUNTER**.  

**Query Response:** The endpoint will return either 0 for an invalid query, the rate of the base asset in the counter asset, or the total amount of the counter asset based on the amount of the base asset specified. 


# 3. Crypto Rates Query URL: https://afreum.com/ice/sites/app/api/rates_crypto.cfm

Use this endpoint to query exchange rates between external cryptocurrencies supported by Afreum, such as BTC, ETH etc., and any fiat currency. 

**URL Query Parameters:**

* **crypto_rates_api_key:** Get a free or paid API key from **https://coinapi.io/**

* **crypto:** The crypto symbol of the external cryptocurrency supported by Afreum Ecosystem for which you want to retrieve a price in fiat. E.g. **BTC**
  
* **fiat:** The 3-character currency code of the of the fiat currency in which you want to retrieve the price of the crypto. E.g. **USD**

**Query Response:** The endpoint will return either 0 for an invalid query, or the rate of the crypto in the fiat.


# 4. Afreum Stable Token Rates Query URL: https://afreum.com/ice/sites/app/api/rates_stable.cfm

Use this endpoint to query exchange rates between Afreum Stable Country Tokens, such as SNGN, SCHF etc., and any fiat currency. The rates are 1:1 with the underlying fiat of each stable token. 1 SNGN = 1 NGN

**URL Query Parameters:**

* **fiat_rates_api_key:** Get a free or paid API key from **https://exchangerate-api.com/**

* **stable:** The Stellar asset code of the Afreum stable token for which you want to retrieve a price in fiat. E.g. **SEUR**
  
* **fiat:** The 3-character currency code of the of the fiat currency in which you want to retrieve the price of the crypto. E.g. **USD**

**Query Response:** The endpoint will return either 0 for an invalid query, or the rate of the stable token in fiat.


# 5. ALL Afreum Stable Token Rates Query URL: https://afreum.com/ice/sites/app/api/rates_stable_all.cfm

Use this endpoint to get the exchange rate between all Afreum stable country tokens, such as SNGN, SCHF, SEUR etc., and the specified fiat currency such as USD. 

**URL Query Parameters:**

* **fiat_rates_api_key:** Get a free or paid API key from **https://exchangerate-api.com/**
  
* **fiat:** The 3-character currency code of the of the fiat currency in which you want to retrieve the price in all other fiats. E.g. **USD** will return 1 USD = n FIAT, where n IS the number of fiat equivalent to 1 USD.

**Query Response:** The endpoint will return either nothing for an invalid query, or an array of all fiat currencies and their exchange rate to the specified fiat.


# 6. Fiat Rates Query URL: https://afreum.com/ice/sites/app/api/rates_fiat.cfm

Use this endpoint to query exchange rates between any fiat currency. 

**URL Query Parameters:**

* **fiat_rates_api_key:** Get a free or paid API key from **https://exchangerate-api.com/**

* **base_fiat:** The 3-character currency code of the fiat for which you want to retrieve a price in another fiat. E.g. **GBP**
  
* **counter_fiat:** The 3-character currency code of the of the fiat currency in which you want to retrieve the price of the crypto. E.g. **USD**

**Query Response:** The endpoint will return either 0 for an invalid query, or the rate of the base_fiat in the counter fiat.


# 7. ALL Fiat Currency Rates Query URL: https://afreum.com/ice/sites/app/api/rates_stable_all.cfm

Use this endpoint to get the exchange rate between all fiat currencies, such as NGN, CHF, EUR etc., and the specified base fiat currency such as USD. 

**URL Query Parameters:**

* **fiat_rates_api_key:** Get a free or paid API key from **https://exchangerate-api.com/**
  
* **base_fiat:** The 3-character currency code of the of the fiat currency in which you want to retrieve the price in all other fiats. E.g. **USD** will return 1 USD = n FIAT, where n IS the number of fiat equivalent to 1 USD.

**Query Response:** The endpoint will return either nothing for an invalid query, or an array of all fiat currencies and their exchange rate to the specified fiat.
