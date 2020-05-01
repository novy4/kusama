# KUSAMA AUTOMATION #

## kusama-node-update ## 
This playbook allows to update your nodes using two methods: 
* rebuild - recompile from source code
* replace - download the binary from polkadot github and replace with existing one

### Some requirments:

* python2 or python3 is installed
* polkadot repo is located in $HOME/polkadot directory
* polkadot binary is located in $HOME/polkadot/target/release diretory

#### usage:
```
ansible -i hosts.yaml -m ping (ping your nodes)
ansible-playbook -i hosts.yaml kusama-node-update.yml -e "current_branch=v0.7.32" -t replace --ask-become-pass
```
#### where:
```
-i hosts.yaml - your nodes list
-e "current_branch=v0.7.32" - new version of kusama release
-t replace - download binaries and replace with the current one, make sure that binary in built and pushed to polkadot github
-t rebuild - rebuild from source
--ask-become-pass - use this to restart the systemd unit in case non root user.
```

## HAVE FUN!
