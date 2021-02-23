#Comandos para construir el servidor http python


sudo docker build . -t m2-http
#comandos para construir el servidor


sudo docker build . -t m2-motivate 
#Levantar servidor http


sudo docker run -p 8000:8000 -v /home/johan/Documents/Docker/M2/contenerizacion-docker/archivos:/http/http --name=m2-http m2-http
#Levantar servidor ftp


sudo docker run -d -e USERS="one|1234" -v  /home/johan/Documents/Docker/M2/contenerizacion-docker/archivos:/ftp/one delfer/alpine-ftp-server 
#Ejecutar contenedor motivate


sudo docker run m2-motivate
