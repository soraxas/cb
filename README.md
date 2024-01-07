# Easy clipboard 

## Getting started

You can directly supply arguments as input string

```sh
$ cb "Hey! How you doing?"
Copied to clipboard: Hey! How you doing?
```

Or you can just pipe inputs to `cb`

```sh
$ cat /etc/profile | cb
Copied to clipboard: # /etc/profile

# Append "$1" to $PATH when not already in.
# This function API ...
```

... and `cb` will preserve all newlines.

## Clipboard across `ssh`

`ssh` to you remote machine with 
```sh
$ ssh madao@myhomeserver.org -R 15756:localhost:15756
```

You also need to start a local `cb` process in your local machine (client)
```sh
$ cb -r
Listening to remote @ localhost:15756...
```

Then, you can run `cb` as usual
```sh
madao@myhomeserver.org $ pwd | cb
>> Detected inside ssh, setting current role as remote sender.
Sending to remote @ localhost:15756...
Copied to clipboard: myhomeserver.org
```


