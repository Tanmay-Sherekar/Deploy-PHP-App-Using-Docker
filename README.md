# Deploy-PHP-App-Using-Docker
Steps to deploy php app using docker
---------------------------------------------------

🚀 Deploy PHP App Using Docker
📁 Step 1: Project Structure
php-docker-app/
│
├── index.php
├── Dockerfile
└── docker-compose.yml
📄 Step 2: Create index.php
<?php
echo "Hello from PHP Docker App!";
?>
🐳 Step 3: Create Dockerfile
FROM php:8.2-apache

COPY . /var/www/html/

EXPOSE 80

This will:

Use official PHP + Apache image

Copy your PHP files into container

Run app on port 80

⚙️ Step 4: Create docker-compose.yml
version: '3.8'

services:
  php-app:
    build: .
    ports:
      - "8080:80"
    volumes:
      - .:/var/www/html
▶️ Step 5: Run the App

Open terminal inside project folder:

docker-compose up --build
🌐 Step 6: Open in Browser
http://localhost:8080

You will see:

Hello from PHP Docker App!
-------------------------------------------
🔥 Deploy on Server (AWS EC2)
1️⃣ Install Docker on EC2
sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
2️⃣ Upload Project
git clone your-repo-link
cd php-docker-app
3️⃣ Run Container
sudo docker build -t php-app .
sudo docker run -d -p 80:80 php-app

Now open:

http://your-ec2-public-ip
