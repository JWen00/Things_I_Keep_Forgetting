# Generate a new ssh key 

Generate the key
```
ssh-keygen -t rsa -b 2048 -C "{email}"
```

Save it under a relevant name (in the case you have multiple keys for different locations) 

```
~./ssh/id_rsa_{name}
```

Copy it! 

```
pbcopy < ~/.ssh/id_rsa_{name}.pub          // macOS 

xclip -sel clip < ~/.ssh/id_rsa_{name}.pub // Linux 

cat ~/.ssh/id_rsa_{name}.pub | clip        // Git bash on windows

```

Note: Don't copy it without the `.pub` as that's ur private key (very secret, do not share). 
