# safaricom-number-hashes-API
An API that given a hash (sha256) of a valid Safaricom Number, returns the original phone number. This API is FREE. To gain access, contact robert@mabob.co.ke or whatsApp +254797186255
# Requirements
You will be provided with a URL and API KEY. Those are enough to get you going within minutes.
# Limitations
The API is FREE. There is a rate limit of 10 requests per seconds.
# Integrating
Just send a GET request to the url. Append the hash at the end of the url. Example: https://example.com/5c76f48d16048f8c2926ef5aa79dd515a71022a28f45b1b9909475724e60f25a /
Remember to add the X-API-KEY header.

#Example
```
    import requests
    URL = "will be provided"
    api_key = "will be provided"
    headers = {"x_api_key":api_key} #For other languages, X-API-KEY if it is valid syntax
    res = requests.get(URL, headers=headers)
    #returns a dict {"key":"str(hash provided)","value":"str(phone_number)"}
    """
    {
      "key": "247306e4e0058bcc04397125eb01f158606d8e4de7b83edf27f180663e24cad5",
      "value": "254799999999"
    }
   """
```
#Errors
status code 503 = Services is unavailable
status code 401 = Unauthorized
N/B For invalid/non-existent hashes, the response is None.

