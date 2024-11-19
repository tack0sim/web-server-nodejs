# Step 1: Preparing Linux VM for Node.js:

A: Initial try to install node.js from terminal on Linux failed. 

Issue 1: No Homebrew package manager found

Solution to Issue 1: Installing Homebrew package manager

Issue 2: No curl tool found

Solution to Issue 2: installing curl on terminal, using:

```bash
$ sudo apt install curl

$ curl --version
# curl 7.74.0
```

B: Installing Homebrew (instructions on brew.sh):

```bash
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Issue 1: no sudo access to user under the standard PATH

Solution to Issue 1:  Log into root user → add user to sudo group:

###solution found on unix.stackexchange.com###

```bash
$ su -
#root password
$ usermod -aG sudo your_username
```

Issue 2: Git not installed

Solution to Issue 2 on Homebrew site: install build tools (including git) :

```bash
$ sudo apt-get install build-essential procps curl file git
```

Re-installing Homebrew using:

```bash
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Install successful!

# Step 2: Install node.js on Linux VM:

A: Install Node.js on the terminal using [nodejs.org](http://nodejs.org) documentation:

```bash
# NOTE:
# Homebrew is not a Node.js package manager.
# Please ensure it is already installed on your system.
# Follow official instructions at https://brew.sh/
# Homebrew only supports installing major Node.js versions and might not support the latest Node.js version from the 22 release line.

# download and install Node.js
brew install node@22

# verifies the right Node.js version is in the environment
node -v # should print `v22.11.0`

# verifies the right npm version is in the environment
npm -v # should print `10.9.0`
```

Install successful!

# Step 3: Starting a local web server

A: Preparing web server:

```bash
$ npx http-server -o /Test-Codes/calculator\ app -p 8080
```

Web server active!
