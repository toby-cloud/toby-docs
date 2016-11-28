# Usage

## On the terminal:

```bash
npm install
npm start <config_file>         # start app
npm test <config_file>          # run tests
npm run coverage <config_file>  # run tests with coverage
npm run forever <config_file>   # run application forever
```


## How to launch on EC2 instance:

```bash
sudo apt-get update
sudo apt-get install git npm

# install node 6.x
curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
sudo apt-get install -y nodejs

git clone https://bitbucket.org/gafo/toby-mqtt.git
cd toby-mqtt
npm install

# run forever (logs saved in ~/.forever)
npm run forever

# run normally
npm start
```