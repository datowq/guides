###### UBUNTU 22.04.1 LTS (WSL2)
# NODE, NPM, and NVM
USING NVM (NODE VERSION MANAGER) TO MANAGE NODE/NPM VERSIONS IS HIGHLY RECOMMENDED FOR VERSION CONTROL

Make a symbolic link to Windows desktop with:

`ln -s /mnt/c/Users/<User>/Desktop/ Desktop`
Note: this isn't required but symbolic links save a lot of time for projects when using wsl

## INSTALLING NVM
Update the system:

`sudo apt update && sudo apt upgrade`

Install curl:

`sudo apt-get install curl`

Install nvm:

`curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash`

Update again:

`sudo apt update && sudo apt upgrade`

Make sure nvm is installed correctly (restart terminal if there is no output and run again):

`command -v nvm`

This should output:

`nvm`

## INSTALLING/USING NODE/NPM

Now install the version of node that you want:

`nvm install --lts` (this is for latest lts version and is recommended)

`nvm install node` (this is for latest version)

`nvm install v16` (use whatever version number)

Make sure that node is installed:

`node -v`

You can switch node/npm versions with:

`nvm use --lts`

`nvm use node`

`nvm use v16` (again, whatever version you want)

## UNINSTALL
You can uninstall node versions with:

`nvm uninstall <version>`

Uninstall npm with:

`sudo npm uninstall npm -g`

Note: npm versions are shipped with certain node versions when using nvm, so using --lts/project version is recommended.
