# Safaricom Number Hashes API

An API that, given a hash (SHA256) of a valid Safaricom Number, returns the original phone number. This API is FREE. To gain access, contact [Robert](mailto:robert@mabob.co.ke) or via WhatsApp at +254797186255.

## Requirements
You will be provided with a URL and API KEY. These credentials are sufficient to get you started within minutes.

## Limitations
The API is FREE, but there is a rate limit of 10 requests per second.

## Integrating
Just send a GET request to the URL. Append the hash at the end of the URL. Example: `https://example.com/5c76f48d16048f8c2926ef5aa79dd515a71022a28f45b1b9909475724e60f25a`

Remember to add the `X-API-KEY` header.

## Example
```python
import requests

URL = "will be provided"
api_key = "will be provided"
headers = {"X-API-KEY": api_key}
res = requests.get(URL, headers=headers).json()
# returns a dict {"key": "str(hash provided)", "value": "str(phone_number)"}
"""
{
  "key": "247306e4e0058bcc04397125eb01f158606d8e4de7b83edf27f180663e24cad5",
  "value": "254799999999"
}
"""
```
## Errors
Status Code 503: Service is unavailable  

Status Code 401: Unauthorized  

Note: For invalid/non-existent hashes, the response is `None`.

