# osx_automated_install
Automated installation of additional tools and programs

This text is from Jeff Geerlings version of this repo @ [mac-dev-playbook](https://github.com/geerlingguy/mac-dev-playbook)

## Installation

  1. Ensure Apple's command line tools are installed (`xcode-select --install` to launch the installer).
  2. Clone or download this repository to your local drive and `cd` into it.
  3. Install Ansible in a local virtual environment:

     ```sh
     python3 -m venv .venv
     source .venv/bin/activate
     pip install --upgrade pip ansible
     ```

  4. Sign in to the App Store app (needed for `mas` to install App Store apps).
  5. Run `ansible-galaxy install -r requirements.yml` to install the required roles and collections.
  6. Run `caffeinate -simsu ansible-playbook main.yml`. Enter your macOS account password when prompted for the 'BECOME' password.

In a new terminal, run `source .venv/bin/activate` again before using `ansible-playbook`.

## Troubleshooting

If for whatever reason you want to re-run this playbook and get errors regarding "local modifications exist in the destination -> dotfiles", please perform a `git reset --hard` on the dotfiles repo locally
