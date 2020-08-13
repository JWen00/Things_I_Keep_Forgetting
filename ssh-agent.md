# ssh-agents 

I kept getting permission error (private) even though I set up my public/private keys correct. 

Turns out that my ssh-agent did not have any identities linked. 

## How to fix this 

Get ssh-agent to start 
``` 
eval `ssh-agent`
```
This should return a `Agent pid {pid} 

Check that you it is running 
```
echo $SSH_AGENT_SOCK
```
$SSH_AUTH_SOCK contains the path of the unix file socket that the agent uses for communication with other processes. This is essential for ssh-add. If you do not have that envrionment variable, see [3]

Check if you have any private keys accessible. 
```
ssh-add -l
```
To add in your keys, run 
```
ssh-add {path} 

Note: Your keys are usually contained in `~/.ssh/rsa_id*
```
Check that it's been successfully added with 
```
ssh-add -l
```


## References 

[1] https://www.ssh.com/ssh/agent
[2] https://stackoverflow.com/questions/22154423/how-is-ssh-auth-sock-setup-and-used-by-ssh-agent
[3] http://blog.joncairns.com/2013/12understanding-ssh-agent-and-ssh-add/