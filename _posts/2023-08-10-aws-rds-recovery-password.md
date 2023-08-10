---
layout: post
title:  Recuperando contraseña maestra AWS RDS Mysql 8.0
categories: [AWS,Mysql]
excerpt: Método para generar una nueva contraseña para una instancia AWS RDS de Mysql en su versión 8.0.
---
Cuando se elige una contraseña maestra generada por aws, al crear una instancia AWS RDS de Mysql solo la muestra una vez al ingresar al panel de configuración de la base de datos.

![alt text](/blog/images/awsrds01.png "Información instancia AWS RDS")

Lo primero sera conectarnos al aws cli o en nuestro caso desde AWS CloudShell.

![alt text](/blog/images/awsrds02.webp "AWS Cloudshell")

Para realizar este procedimiento es necesario tener el identificado de la base de datos, que el nombre con el que creamos nuestra instancia de AWS RDS.

Para recuperar una contraseña maestra de una instancia de AWS RDS MySQL desde AWS CLI, puede usar el comando rds ```modify-db-instance```. Este comando le permite modificar la configuración de una instancia de RDS, incluida la contraseña maestra.

Por ejemplo, para modificar la contraseña maestra de una instancia de RDS llamada ```my-db-instance``` a ```my-new-password```, usaría el siguiente comando:

```
aws rds modify-db-instance –db-instance-identifier my-db-instance –master-user-password my-new-password
```

El comando ```rds modify-db-instance``` modificará la contraseña maestra de la instancia de RDS y la nueva contraseña maestra entrará en vigor en la siguiente instancia de reinicio de la base de datos.

Una vez que la nueva contraseña maestra esté en vigor, podrá usarla para conectarse a la instancia de RDS MySQL.
