a bridge for separate processes (parent, child) in [[Tech/Software/Arquitecture/Proxy/IPC/IPC|Inter processes Communication]]  

Has names, exist in disk, exist until deleted

python impl:
server
```python
import multiprocessing.connection

address = r'\\.\pipe\mypipe'

listener = multiprocessing.connection.Listener(address, authkey=b"test")

while True:
    print("Waiting for a client...")
    conn = listener.accept()
    conn.send("message from server")
    print("Client connected:", listener.last_accepted)
    conn.close()
    print("Client disconnected.\n")
```

client
```python
import multiprocessing.connection
address = r'\\.\pipe\mypipe'
conn = multiprocessing.connection.Client(address, authkey=b"test")

msg = conn.recv()

print(msg)
```