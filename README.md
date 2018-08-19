# Installing Neovim from source
Basic installation of neovim from source. 

Has the following variables

| Variable | Default Value | Description |
| -------- | ------------- | ----------- |
| nvim_version | 0.3.1 | Version of nvim tar |
| nvim_install_dest | $HOME/neovim | Location to store neovim bin/ and share/ |
| nvim_install_root | false | Whether to install neovim artifacts as root |


## Installation for CentOS 7 and RHEL7
The following will install in a users `$HOME` or a common location like `/usr/local`. `--become` is used for installing any required dependencies with `yum`. Use `nvim_install_root` to dictate whether to install the neovim artifacts as `root`.

### Install in users $HOME
```bash
ansible-playbook install.yml \
    -i inventory \
    -e "target_hosts=YOUR_HOST" \
    -e "nvim_install_dest=$HOME/neovim" \
    -e "nvim_install_root=false" \
    --become \
    --ask-become-pass
```
### Install in /usr/local
```bash
ansible-playbook install.yml \
    -i inventory \
    -e "target_hosts=YOUR_HOST" \
    -e "nvim_install_dest=/usr/local" \
    -e "nvim_install_root=true" \
    --become \
    --ask-become-pass
```
