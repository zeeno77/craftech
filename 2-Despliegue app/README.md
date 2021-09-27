To deploy the app locally just build and run it with the following commands:  
  
1- docker-compose build  
2- docker-compose up  
  
  
To deploy the app on AWS:  
  
1- docker-compose build
2- Configure your Amazon credentials  
3- Create new docker context for ecs  
   docker context create ecs "myContextName"   
4- docker context use myContextName
5- docker-compose up  
