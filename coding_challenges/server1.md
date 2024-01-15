```python
import socket
from cryptography.fernet import Fernet

key=b'phVvTagHwRi1xB-m9E3rvVtBtBpLO7eTtp3h0fa1FY4='
fernetkey=Fernet(key)

def server_respondingtoclient(c):
    while True:
        cr=c.recv(1024)
        dcr=fernetkey.decrypt(cr.decode())
        print("A: ",dcr.decode())
        sr=input("B : ")
        esr=fernetkey.encrypt(sr.encode())
        c.send(esr)
    c.close()
def server_socket():
    s=socket.socket()
    s.bind(("localhost",8080))
    s.listen(5)
    while True:
        c,adrr=s.accept()
        server_respondingtoclient(c)
server_socket()
        
```

    A:  Hii
    B : Hello
    A:  What's up
    B : Ntg.
    A:  Hoo
    B : You?
    A:  Me too
    B : Do u have any plane for the day ?
    A:  Noo . Do u?
    B : Noo.
    


```python

```


```python

```
