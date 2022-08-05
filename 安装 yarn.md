```bash
$sudo apt install curl
#Import Yarn GPG key
$ curl -sL https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -

#Enable Yarn repository
$ echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

#Install Yarn on Ubuntu 22.04
$ sudo apt install yarn
$ yarn --version
0.32+git
```

## How to upgrade Yarn on Ubuntu 22.04

```bash
$ sudo apt install npm

#download the “Yarn” tarball and install its latest version 
$ sudo curl --compressed -o- -L https://yarnpkg.com/install.sh | bash
```



**Yarn install - No such file or directory 解决办法**

```bash
sudo apt remove cmdtest
sudo apt remove yarn
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt-get update
sudo apt-get install yarn -y
```

