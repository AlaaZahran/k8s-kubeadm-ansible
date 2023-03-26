
# Project Title

Setup k8s kubeadm cluster using ansible.




## Virtual machine 
Need 3 vm as follwing:
- ansible controller
 - k8s master
  - k8s client

## Users
Create user ansible on every machines and add it to sudoers user 

## Local DNS
Add hosts to /etc/hosts   

```bash
  sudo vim /etc/hosts
```
![image](https://user-images.githubusercontent.com/46306526/226140004-2442dab4-11a7-4a4b-ad2f-b5f7de663764.png)
## Passwordless ssh
Generate ssh key in ansible controller and copy key to each vm 

## Install ansible on ansible controller
First ensure that the CentOS 7 EPEL repository is installed

```bash
  sudo yum install epel-release
```
Install Ansible with yum
```
sudo yum install ansible
```

## Deployment
1- Create inventory file as following :

![image](https://user-images.githubusercontent.com/46306526/226140083-b835c5a1-817f-480c-aa73-526aa0c246a9.png)

2- Create ansible.cfg file as following:
 
 ![image](https://user-images.githubusercontent.com/46306526/226140174-7c55b59d-26b0-4bcb-b844-6e9d429f045b.png)

3- create roles directory wuch include many directories as following each directory represent task or more using ansible modules :
- client   
 - docker  
  - join  
  - kub  
  - kubeadm  
  - kubectl  
  - kubelet  
  - pre  
  - restart

  4- Create playbook.yml which include plays and roles






## Output
![client11](https://user-images.githubusercontent.com/46306526/226140751-7ed4f126-53d7-406c-b69f-59e95a61ddd2.png)

![master11](https://user-images.githubusercontent.com/46306526/226140766-4f53da9f-1dfa-4a2e-abb2-3f45451acfc1.png)

![pk3](https://user-images.githubusercontent.com/46306526/226140772-7e501581-cc5b-40b1-90f7-25aebc199fe1.png)

![pkg2](https://user-images.githubusercontent.com/46306526/226140787-4b99f652-3ac0-49e6-8862-00dddedd88c1.png)

![pkg4](https://user-images.githubusercontent.com/46306526/226140808-51618abc-de2c-4dff-b2fb-956607bb6a29.png)

![pkg111](https://user-images.githubusercontent.com/46306526/226140818-a3914490-93cb-4cf2-9f19-24be074296d4.png)

![Untitled222](https://user-images.githubusercontent.com/46306526/226140858-d1d17635-5c67-4170-98c5-0b4a5d3d8a97.png)

## Test 
ssh to master node and run that command 

```
kudectl get node
```
output

![verification](https://user-images.githubusercontent.com/46306526/226141040-74f16157-6fd1-4b96-8d68-28bb82e93f18.png)

