# Network Errors
## 1. OpenSSL SSL_read: Connection was aborted, errno 10053
### situation
When using ``git clone https://...``, the error occurs.
  
### reason
I don't quite know why yet...  
  
### solution
```git
git config --global http.sslVerify false
```
This would cancel(?) the SSL certificate of https. 
