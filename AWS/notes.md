## Connect to your AWS Instance:

Things you need to replace in the code:
- A: /path_to_key/lighthouse.pem
- B: Public-IPv4-DNS-address

``` 

 ssh -i '/path_to_key/lighthouse.pem'  ubuntu@B

```
## Connect to jupyter lab

- In the same terminal write: 
```
jupyter lab
```
- Open the bookmarked page on chrome


## Transfer a file from your computer to AWS Instance

Run the following code on the window's main terminal:

Things you need to replace in the code:
- A: path-of-your-pem-file
- B: Source-File-Path
- C: Public-IPv4-DNS-address

```
scp -i'A''B' ubuntu@C:/home/ubuntu/
```