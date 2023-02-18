
# Python’s Requests Library (Guide)

## The GET Request

## The Response

### 1. Status Code
- First we need to import the library
- Then we write it as:     *requests.get ('URL of api')*

An example is provided below:

``` Python
import requests
response = requests.get('https://api.github.com')
response
````
### 2. Content
To see the response’s content in bytes, we use ***.content*** like follow:
``` Python
response.content
```

### 3. Headers

 If you need more information, like metadata about the response itself, you’ll need to look at the response’s headers. Use the code belowe:
 ``` python
 response.headers
 ```
## Query String Parameters



For more details click [This](https://realpython.com/python-requests/)