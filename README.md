# Stack

**A personal project for understanding GenServers**

#### Some commands

Calling `init` callback with the initial state that has been established by `init`
```
iex(9)> {:ok, pid} = Stack.start_link
{:ok, #PID<0.237.0>}
```

Communicating with the spawned process using `GenServer`. This sends messages to the process
spawned by `init`
```
iex(10)> Stack.push(pid, "Hello world")
:ok
iex(11)> Stack.push(pid, "Good morning")
:ok
iex(12)> Stack.push(pid, "Good afternoon")
:ok
```
then
```
iex(13)> Stack.pop(pid)
"Good afternoon"
iex(14)> Stack.pop(pid)
"Good morning"
iex(15)> Stack.pop(pid)
"Hello world"
```

`Stack.push/2` is asynchronous. `Stack.pop/1` is synchronous
