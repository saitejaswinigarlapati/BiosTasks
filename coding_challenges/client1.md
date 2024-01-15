```python
import socket
from cryptography.fernet import Fernet

key=b'phVvTagHwRi1xB-m9E3rvVtBtBpLO7eTtp3h0fa1FY4='
fernetkey=Fernet(key)

def client_socket():
    c=socket.socket()
    c.connect(("localhost",8080))
    while True:
        m=input("A : ")
        em=fernetkey.encrypt(m.encode())
        c.send(em)
        r=c.recv(1024)
        dr=fernetkey.decrypt(r.decode())
        print("B :",dr.decode())

client_socket()
        
```

    A : Hii
    B : Hello
    A : What's up
    B : Ntg.
    A : Hoo
    B : You?
    A : Me too
    B : Do u have any plane for the day ?
    A : Noo . Do u?
    B : Noo.
    


```python

```


```python

```
