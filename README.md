# osx_automated_install
Automated installation of additional tools and programs

This text is from Jeff Geerlings version of this repo @ [mac-dev-playbook](https://github.com/geerlingguy/mac-dev-playbook)

## Installation

  1. Ensure Apple's command line tools are installed (`xcode-select --install` to launch the installer).
  2. [Install Ansible](https://docs.ansible.com/ansible/latest/installation_guide/index.html):

     1. Run the following command to add Python 3 to your $PATH: `export PATH="$HOME/Library/Python/3.9/bin:/opt/homebrew/bin:$PATH"`
     2. Upgrade Pip: `sudo pip3 install --upgrade pip`
     3. Install Ansible: `pip3 install ansible`

  3. Clone or download this repository to your local drive.
  4. Run `ansible-galaxy install -r requirements.yml` inside this directory to install required Ansible roles.
  5. Run `ansible-playbook main.yml --ask-become-pass` inside this directory. Enter your macOS account password when prompted for the 'BECOME' password.

## Troubleshooting

If for whatever reason you want to re-run this playbook and get errors regarding "local modifications exist in the destination -> dotfiles", please perform a `git reset --hard` on the dotfiles repo locally
