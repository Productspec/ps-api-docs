# Productspec API V1

This is the official documentation for the Productspec API.

API Objects
-----------

- [Primary Categories](content/categories.md)
- [Companies](content/company.md)
- [Filter Products](content/search.md)
- [GET Product](content/product.md)

Making Requests
---------------

The base URL for all requests is 'https://services.productspec.net/' 

Only https is supported.

The Productspec API uses an API key that must be included in an custom HTTP request header named `api-key` for all requests except for requests for files.

*The API key is not used for security and is not private.  Future versions of this API may require a private key, but for now it is public.*

using cURL you would make a request like:

```shell
curl -H 'api-key: <api_key>' -XGET 'https://services.productspec.net/api/product/4e9b90464ff399d11457cd6a'
```
`Exception: requests for files must include the api-key in the url.`


Pagination
----------
Product search and filter results use pagination.  Each page has a limit of 25 products.  
To select select a page provide the 'page=<number>' querystring parameter.  

```shell
curl -H 'api-key: <api_key>' https://services.productspec.net/api/search?page=2
```

The total number of available objects will be returned in the 'total' property on the results object returned.

