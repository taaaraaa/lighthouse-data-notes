
## Python’s Requests Library (Guide)

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
To see the response’s content in bytes, we use *.content* :
``` Python
response.content
```

For more details click [This](https://realpython.com/python-requests/)