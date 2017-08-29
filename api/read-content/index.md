# Title: Read content
<!-- Position: 2 -->
<!-- Date: 2017-08-27 13:00:00 -->
---
With the Bludit API you can request a particular page or a list of pages via the API.

By default the API requiere the `API token` to interact with them you need to send all the time for any request.

## Request a list of pages

### Request
- Endpoint: `/api/pages`
- Method: `GET`
- Parameters: `token`

### Response
- HTTP Code: 200
- Content-Type: application/json
- Content
```
{
        "status": "0",
        "message": "List of pages, amount of items: 15",
        "data": [
                {
                        "key": "the-dog",
                        "title": "The Dog",
                        "content": "Content of the page",
                        "description": "Description of the page",
                        "date": "2017-08-24 22:00:00",
                        "permalink": "http:\/\/example.com\/the-dog"
                },
                {
                        ....
                }
        ]
}
```

### cURL command example
Here is an example of a request maded via the command line with the command curl.
```
$ curl -vvv -X GET -G "https://example.com/api/pages" -d "token=80a09ba055b73f68e3c9e7c9ea12b432"

> GET /api/pages?token=80a09ba055b73f68e3c9e7c9ea12b432 HTTP/1.1
> Host: example.com
> User-Agent: curl/7.54.0
> Accept: */*

< HTTP/1.1 200 OK
< Date: Sun, 27 Aug 2017 18:58:25 GMT
< Set-Cookie: Bludit-KEY=3de3df692e83b9cbbf5d31de385110bb; path=/; HttpOnly
< Expires: Thu, 19 Nov 1981 08:52:00 GMT
< Cache-Control: no-store, no-cache, must-revalidate, post-check=0, pre-check=0
< Pragma: no-cache
< Content-Length: 50731
< Content-Type: application/json

{JSON Data}
```

### AJAX with jQuery
Example of AJAX request with the library [jQuery](https://api.jquery.com/jQuery.ajax/).
```
$.ajax({
        url: "https://example.com/api/pages",
        method: "GET",
        data: "token=80a09ba055b73f68e3c9e7c9ea12b432",
        dataType: 'json',
        success: function(json) {
                console.log(json);
        }
});
```

You can see and download a full example in [Bludit Examples](https://github.com/bludit/examples/tree/master/api/ajax-request-list-of-pages)