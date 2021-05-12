# LiCloud

a [Sails v1](https://sailsjs.com) application


### Links

+ [Get started](https://sailsjs.com/get-started)
+ [Sails framework documentation](https://sailsjs.com/documentation)
+ [Version notes / upgrading](https://sailsjs.com/documentation/upgrading)
+ [Deployment tips](https://sailsjs.com/documentation/concepts/deployment)
+ [Community support options](https://sailsjs.com/support)
+ [Professional / enterprise options](https://sailsjs.com/enterprise)


### 3rd Services 

+ lidar360online.com
    + Domain: GoDaddy
    + Server: AWS EC2
    + DNS: AWS Route53
    + Email: SendCloud

+ licloud.net.cn
    + Domain: TencentCloud(Xinnet)
    + Server: Aliyun ECS
    + DNS: DNSPOD
    + Email: SendCloud

### Deploy with Docker
Open a bash in this folder then use the following command to build docker image for this project
```
#prod-licloud (need sudo in ubuntu)
docker-compose -f docker-compose-prod-licloud.yml up --build -d

#prod-lidar360online (need sudo in ubuntu)
docker-compose -f docker-compose-prod-lidar360online.yml up --build -d

#stop all container (need sudo in ubuntu)
docker stop $(docker ps -a -q)

#remove all container (need sudo in ubuntu)
docker rm $(docker ps -a -q)

#view logs
docker logs -f -t licloud
```

### Deploy without Docker

#### Install MySQL
Install MySQL5.7
Set root password as *greenvalley*
Set character-set-server=utf8mb4
Set collation-server=utf8mb4_unicode_ci

#### Install Redis
Set password as *greenvalley*

### Install NodeJS

### Build and run this project
Open a bash in this folder then use the following commands to build this project
```
// (Windows only) install build tools globally
npm install -g windows-build-tools --vs2015
// install sails globally
npm install -g sails
// install node modules
npm install
```

Run this project
```
// dev
sails lift
// staging
NODE_ENV=staging sails lift --alter
// prod
sails lift --prod
// prod forever
forever start -a -l forever.log -o out.log -e err.log app.js --prod
// prod forever restart
forever restartall
```
