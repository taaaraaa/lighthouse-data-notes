
## Python’s Requests Library (Guide)
- First we need to import the library
- Then we write it as: requests.get('URL of api')
An example is provided below. I wrote the if function to make it more fancy!

``` Python
import requests
response = requests.get('https://api.github.com')

if response:
    print('Success!')
else:
    print('An error has occurred.')
````