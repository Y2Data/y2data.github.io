---
layout: post
date: 2021-05-25 16:07:28 +0900
Title: How to run SQL locally on Docker from M1 macs
categories: Essay
author:  Yuhao Dai
---

Firstly, you need [Docker desktop](https://docs.docker.com/docker-for-mac/apple-silicon).

Then, you'll need an SQL image that can run on M1 macs. Microsoft has recently developed an image called SQL Azure Edge, and it has been implemented for ARM. Run this in the terminal to both pull and run the image locally:

{% highlight shell %}
docker run -e "ACCEPT_EULA=1" -e "MSSQL_SA_PASSWORD=Really_strong_password" -e "MSSQL_PID=Developer" -e "MSSQL_USER=SA" -p 1433:1433 -d --name=sql mcr.microsoft.com/azure-sql-edge
{% endhighlight %}

Of course, change the value of "MSSQL_SA_PASSWORD" to the password you desire, but remember to follow mssql's password policy:
* The password does not contain the account name of the user.
* The password is at least eight characters long.
* The password contains characters from three of the following four categories:
* Latin uppercase letters (A through Z)
* Latin lowercase letters (a through z)
* Base 10 digits (0 through 9)
* Non-alphanumeric characters such as: exclamation point (!), dollar sign ($), number sign (#), or percent (%).

And when you try to connect to it, you need to use the server _*127.0.0.1*_, and set the username to be _*sa*_.

Connection type is of course, _*Microsoft SQL Server*_.

And voila, that should do it.
