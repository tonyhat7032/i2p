
# OnionScan on Google Cloud Shell

NOTE! This repo is a patched version of https://github.com/s-rah/onionscan and is designed to be run from a Google Cloud Shell.

1. To get a free cloud shell account: https://console.cloud.google.com/getting-started?pli=1

2. Open your Cloud shell you click here:

![Screen Shot 2022-02-08 at 3 35 31 PM](https://user-images.githubusercontent.com/12143192/153079726-0332a2f7-8dae-4786-81c5-d70e71fc4dd1.png)

3. From your Cloud Shell:

`wget https://raw.githubusercontent.com/hunchly/funchly/main/onionscan/cloudshell_install_onionscan.sh`

`chmod +x cloudshell_install_onionscan.sh`

`./cloudshell_install_onionscan.sh`

4. You now need a way to connect into Tor, and we can use Docker (already setup in Google Cloud Shell) for this:

`docker run -it -p 127.0.0.1:9050:9050 –-name torproxy -d dperson/torproxy`

`docker inspect torproxy`

5. Note the IP address listed in the IPAddress field and then run onionscan:

`onionscan -torProxyAddress <IP ADDRESS OF DOCKER CONTAINER>:9050 -verbose <ONION ADDRESS>`

You will need to re-run the Tor Proxy / docker commands above each time you drop into a cloud shell.

# What is OnionScan?

Head to the original repo: https://github.com/s-rah/onionscan

