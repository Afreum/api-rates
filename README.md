# API QUERY LINKS: EXCHANGE RATES

Afreum provides a public universal exchange rate API that can be called remotely by developers building on top of the Afreum Ecosystem. This API will be used by Afreum developers in the upcoming Afreum 2.0 ecosystem upgrade. Developers who wish to build apps for the Afreum Ecosystem should use these APIs in production, rather than any of the scripts provided that perform the same functions. The endpoints are as follows:

# 1. Fiat Rates Query URL: https://afreum.com/ice/sites/app/api/rates.cfm

**URL Query Parameters:**

* **fiat_rates_api_key:** Get a free or paid API key from **https://exchangerate-api.com/**

* **crypto_rates_api_key:** Get a free or paid API key from **https://coinapi.io/**

* **token:** The asset code of a Stellar token supported by Afreum Ecosystem. See JSON files here: **https://api.afreum.com/tokens/** 
  
* **token_issuer:** The asset issuer address of a Stellar token supported by Afreum Ecosystem. See JSON files here: **https://api.afreum.com/tokens/** 

* **fiat:** The currency code of a fiat currency. E.g. USD or EUR.

* **json:** The name of JSON file relating to the token without the .JSON extention. Supported values are: **afr_token_flexible, afr_token_stable, afr_token_other, afr_token_external**.

**Query Response:** The endpoint will return either nothing for an invalid query or the rate of the token in fiat.  


# 2. Universal Rates Query URL: https://afreum.com/ice/sites/app/api/rates_tokens.cfm

**URL Query Parameters:**

* **fiat_rates_api_key:** Get a free or paid API key from **https://exchangerate-api.com/**

* **crypto_rates_api_key:** Get a free or paid API key from **https://coinapi.io/**

* **base:** The asset code of the Stellar token, fiat, or cryptocurrency supported by Afreum Ecosystem for which you want to retrieve a price in the counter asset. E.g. **AFR, USD, BTC**
  
* **base_issuer:** The asset issuer address of the Stellar token supported by Afreum Ecosystem for which you want to retrieve a price in the counter asset. E.g. **GBX6YI45VU7WNAAKA3RBFDR3I3UKNFHTJPQ5F6KOOKSGYIAM4TRQN54W**. If the base asset is not a Stellar token this should be blank.

* **counter:** The asset code of the Stellar token supported by Afreum Ecosystem in which you want to price the base asset. E.g. **AFR, EUR, ETH**
  
* **counter_issuer:** The asset issuer address of the Stellar token supported by Afreum Ecosystem in which you want to price the base asset. E.g. **GBX6YI45VU7WNAAKA3RBFDR3I3UKNFHTJPQ5F6KOOKSGYIAM4TRQN54W**. If the counter asset is not a Stellar token this should be blank.

* **base_json:** The name of JSON file relating to the base asset without the .JSON extention. Supported values are: **afr_token_flexible, afr_token_stable, afr_token_other, afr_token_external**. This field is always required.

* **counter_json:** The name of JSON file relating to the counter asset without the .JSON extention. Supported values are: **afr_token_flexible, afr_token_stable, afr_token_other, afr_token_external**. This field is always required.
  
* **base_amount:** The amount of the base asset exchanged into the counter asset. Default is 1. Use this parameter if you would like to return results for **1 BASE = ? COUNTER**.  

**Query Response:** The endpoint will return either nothing for an invalid query or the rate of the base asset in the counter asset. 
