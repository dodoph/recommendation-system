# recommendation-system
Project: Recommendation System

## Deploy application on Amazon EC2

1. Build instance on EC2 (include private key)
2. Connect to the instance(ubuntu terminal)
```  
chmod 600 ~/Downloads/mykey.pem
ssh -i ~/Downloads/mykey.pem ubuntu@YOUR_INSTANCE_IP
```
3. Install docker in my EC2
4. Zip your file :  In Eclipse, select File -> Export -> Web, and choose WAR file
5. Upload to your instance in another terminal (make sure key and .war are in Download)
```
scp -i ~/Downloads/mykey.pem  ~/Downloads/Jupiter.war ubuntu@YOUR_INSTANCE_IP:~/
```
6. Build a docker image and Dockerfile
```
sudo docker build -t jupiter .
```
7. Run image
```
sudo docker run -d -p 8080:8080 jupiter
```
8. Stop container (if you want to upload new vision, please stop old container first)
```
sudo docker stop <container_id>
```
Check your container_id: ```sudo docker ps```
