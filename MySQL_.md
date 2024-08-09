
## INSTALL MYSQL PERSONALLY

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
