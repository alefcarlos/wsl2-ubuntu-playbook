# WSL2 Ubuntu Playbook

![Ansible Lint](https://github.com/alefcarlos/wsl2-ubuntu-playbook/workflows/Ansible%20Lint/badge.svg)

## Instaling WS2

Follow [this link](https://docs.microsoft.com/en-us/windows/wsl/install-win10#update-to-wsl-2) to install.

## Windows Terminal

Install lastest [Windows Terminal](https://github.com/microsoft/terminal) version to enjoy all the amazing features

### Fonts

I use [FiraCode Nerd Font](https://github.com/ryanoasis/nerd-fonts/blob/master/patched-fonts/FiraCode/Regular/complete/Fura%20Code%20Regular%20Nerd%20Font%20Complete.ttf) on  Windows Terminal configuration `profiles.defaults.fontFace`

I can use `ligatures` using this font ;)

### oh-my-posh

Run `setup_wt.ps1` to setup oh-my-posh on Powershell, then configure PowerShell profile:

```powershell
notepad $PROFILE
```

And add following content:
```powershell
Import-Module posh-git
Import-Module oh-my-posh
Set-Theme Zash
```

## Running this playbook

```
sudo apt update -y && sudo apt install git ansible -y

mkdir ~/git && git clone http://github.com/alefcarlos/wsl2-ubuntu-playbook ~/git/wsl2-ubuntu-playbook/

cd ~/git/wsl2-ubuntu-playbook/ && /
ansible-playbook playbook.yml --extra-vars="user_name=$USER" --ask-become-pass

rm -rf ~/git/wsl2-ubuntu-playbook/
```

## TODO:

- Ansible for setuping Windows Terminal + Windows WSL2 + Ubuntu
