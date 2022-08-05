https://phoenixnap.com/kb/update-node-js-version

```bash
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash

$ source ~/.bashrc

$ nvm --version

# Before upgrading Node.js, check which version you have running on the system:
$ nvm ls

# Now you can check for newly available releases with:
$ nvm ls-remote


#To install the latest version, use the **`nvm`** command with the specific Node.js version:
$ nvm install [version.number]
$ nvm install v16.16.0 #示例
```
