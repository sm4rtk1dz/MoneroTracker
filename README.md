# xmrmap 
![status](https://img.shields.io/badge/status-beta-orange) ![dependencies](https://img.shields.io/badge/dependencies-none-green)  
xmrmap is software that allows you to track and validate a Monero wallet within different public minning pools in an automated way.

## Usage
The tool is very easy to use, just provide the wallet address as follow.  
The software will classify the wallet address and will check the different public pools for workers.

```
chmod +x ./xmrmap
php ./xmrmap [wallet_address]
```

## Contributions
Contributions to the project are **very welcome**. In order to mantain it useful, **new minning pool addresses can be added** to the ``poolsList.json`` file.
The structure of the JSON is as follows:

```JSON
{
  "https://nanopool.org/": {
    "requestTo": "https://api.nanopool.org/v1/xmr/avghashrate/%%ADDR%%",
    "method": "GET"
  },
  "https://example.com/": {
    "requestTo": "https://example.com/api/pool/get_wid_stats",
    "method": "POST",
    "body": "address=%%ADDR%%"
  }
}
```
notice the ``%%ADDR%%`` special word is used in the place where the Monero address must be filled, the key of the JSON object is the URL of the pool.
In case of a ``POST`` request, the ``body`` must be specified.
