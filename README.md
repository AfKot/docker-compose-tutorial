# docker-compose-tutorial

Install Docker by running the following commands:
'''
sudo apt-get update
sudo apt install curl -y
curl https://get.docker.com | sudo bash

sudo usermod -aG docker $(whoami)
'''

Then restart your VM. (Stop the Start)

Install Compose by running the following commands:
'''
# make sure jq & curl is installed
sudo apt update
sudo apt install -y curl jq
# set which version to download (latest)
version=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | jq -r '.tag_name')
# download to /usr/local/bin/docker-compose
sudo curl -L "https://github.com/docker/compose/releases/download/${version}/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
# make the file executable
sudo chmod +x /usr/local/bin/docker-compose
'''

To clear up at the end of your session run:
''' docker-compose down --rmi all '''
