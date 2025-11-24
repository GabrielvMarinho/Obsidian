[[HTTP]] parsers basically call recv() from [[TCP]] plenty of times to read the entire request/response, until if finds a stop point, like "\r\n" and goes to the next line, finishing with "\r\n\r\n"

## Previous Misunderstanding on Content-Length 

When i implemented my own http server implementation [here]([GabrielvMarinho/http-server-python-implementation](https://github.com/GabrielvMarinho/http-server-python-implementation)), I did

```python
while b"\r\n\r\n" not in msg_buffer:
	data = socket_.recv(16)
	msg_buffer = msg_buffer+ data   
```

this only works to get the request headers, not the body itself, for that, we would need to  read the content length header and then read that amount of content with recv(), considering that tcp doesnt control the end of the message.