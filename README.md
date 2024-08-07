# docker



### install docker first 

### to check it 

```bash

sudo docker run hello-world
```
### if you got hello world then continue to pul docker image if not then :-

#### TRY

```bash
sudo apt install docker.io
```

## AFTER THAT 
```bash
docker pull mysql
```
### YOU CAN DIRECTLY RUN FROM THIS LINE OF CODE IF DOCKER IS ALREADY PRESENT
```bash
 sudo docker run --name mysqldb -p 3307:3307 -v mysql_volume:/var/lib/mysql/ -d -e "MYSQL_ROOT_PASSWORD=1234" mysql
```

```bash
sudo docker exec -it mysqldb bash
```


```bash
mysql -u root -p

```
PASSWORD
```bash
1234
```
#### FOR THE FIRST TIME IF  YOU  GET ERROR , get out of the container by ``exit`` command

#### and then again try 

```bash
docker exec -it mysqldb bash
```


```bash
mysql -u root -p

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




