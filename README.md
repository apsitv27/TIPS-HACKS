# mysql in docker

## IF YOU WANT YOU  DIRECTLY RUNT THE MYSQL SERVER ( SHORTCUT)

```bash
docker run -it apsitv27/mysql
```

( make sure you are connected to the internet before executing this)
### AFTER THAT you will see this 
![image](https://github.com/user-attachments/assets/7d3e2e2b-3e5a-43b1-8572-caddb5d4aeaa)

### JUST TYPE 

```bash
mysql
```


## AND YOU ARE GOOD TO GO !!🫡💯

--------------------------------------


---------------


-----------


--------


-------



# LONG METHOD TO RUN MYSQL


-------
## INSTALL THIS IF DOCKER IS NOT PRESENT ALREADY 
```bash
sudo apt install docker.io
```

## AFTER THAT 
```bash
sudo docker pull mysql
```
### YOU CAN DIRECTLY RUN FROM THIS LINE OF CODE IF DOCKER IS ALREADY PRESENT

### IT WILL AUTOMATICALLY PULL THE DOCKER IMAGE REQUIRED!
```bash
 sudo docker run --name mysqldb -p 3307:3307 -v mysql_volume:/var/lib/mysql/ -d -e "MYSQL_ROOT_PASSWORD=1234" mysql
```

```bash
sudo docker exec -it mysqldb bash
```


```bash
mysql -u root 

```
PASSWORD IF PROMPTED 
```bash
1234
```
#### FOR THE FIRST TIME IF  YOU  GET ERROR , get out of the container by ``exit`` command

#### and then again try 

```bash
docker exec -it mysqldb bash
```


```bash
mysql -u root 

```
### OR TRY TYPING MANUALLY ```mysql -u root -p``` if problem still persists

### if installed then good to go 

-----


---------

-------

----------



## if not [then](https://github.com/kimroy99/Docker/blob/main/Guide) 

### ONLY TRY THESE STEPS , IF PROBLEM STILL PERSISTS!!
```bash
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

```
```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

```bash
sudo apt-get update
```
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

```bash
docker pull mysql
```
```bash
 docker run --name mysqldb -p 3307:3307 -v mysql_volume:/var/lib/mysql/ -d -e "MYSQL_ROOT_PASSWORD=1234" mysql
```

```bash
docker exec -it mysqldb bash
```


```bash
mysql -u root -p

```
PASSWORD
```bash
1234
```




