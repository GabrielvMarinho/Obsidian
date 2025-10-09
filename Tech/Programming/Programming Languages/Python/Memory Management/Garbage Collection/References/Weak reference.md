A reference in [[Python]] that does not protect the object from being [[Garbage Collector|Garbage collected]]

This is a good use case:

```python
class Listener:
   def __init__(self, broadcaster):
      broadcaster.listeners.add(self.callback)
   def callback(self, msg):
      print('message received', msg)
  
class Broadcaster:
   def __init__(self):
      self.listeners = set()
   def broadcast(self):
      for listener in self.listeners:
         listener("notification")
  
b = Broadcaster()
l = Listener(b)
  
b.broadcast()
del l
print("deleted")
b.broadcast()
```

this will broadcast to the listener even after deletion, to avoid this memory leak we could tweak the code to look like this:

```python
import weakref
class Listener:
   def __init__(self, broadcaster):
      cb = self.callback
      weakself = weakref.ref(self)
      def cb(msg):
         self = weakself()
         self.callback(msg)
      broadcaster.listeners.add(cb)
      self._callbacks = set([cb])
   def callback(self, msg):
      print('message received', msg)
  
class Broadcaster:
   def __init__(self):
      self.listeners = weakref.WeakSet()
   def broadcast(self):
      for listener in self.listeners:
         listener("notification")
  
b = Broadcaster()
l = Listener(b)
  
b.broadcast()
del l
print("deleted")
b.broadcast()
```

all those changes were made because the bound method would be orphaned if we just changed it to a weakset in the broadcaster, making it be garbage collected (now the callback is being saved by the `def cb(msg)` line)

Weak ref can be created mostly only for custom classes.