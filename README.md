# cc-lab7

## Windows: WSL Instructions

Install a Ubuntu VM:
```
wsl --install -d Ubuntu
````

Edit the /etc/wsl.conf file:
```
sudo nano /etc/wsl.conf
````

Add these lines to the file and save it:
```
[boot]
systemd=true
```

Restart the WSL:
```
wsl --shutdown
````

## Linux: Canonical Multipass Instructions

Install multipass:
```
sudo snap install multipass
```
Start a Ubuntu VM:
```
multipass launch 24.04 --name k8s-master --cpus 2 --memory 4G --disk 10G
```
Open the Shell:
```
multipass shell k8s-master
```

## macOS: Lima Instructions

Install Lima:
```
brew install lima
```
Start a Ubuntu VM:
```
limactl start template://ubuntu --name k8s-master --vm-type=vz
```
Open the Shell:
```
limactl shell k8s-master
```

Install K3s
```
curl -sfL https://get.k3s.io | sh -
```

Give right permissions to the Kubectl Config File
```
sudo chmod 755 /etc/rancher/k3s/k3s.yaml
```
