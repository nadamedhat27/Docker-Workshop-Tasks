# Session 3 Task
- ## Q1
    ### Old Method
    - ### by volume mapping:
        ``` 
        sudo docker run -it --memory=500MB --network=host -v dbVolume:/var/lib/postgresql/data -d --name db1 -e POSTGRES_PASSWORD=pass1234 postgres
        ```
    - ### by bind mounting:
        ```
        sudo docker run -it --memory=500MB --network=host -v /MyFiles/OSC/Docker-Workshop-Tasks/Session3/data:/var/lib/postgresql/data -d --name db1 -e POSTGRES_PASSWORD=pass1234 postgres
        ```
    ### New Method
    - ### by volume mapping:
        ```
        sudo docker run -it --memory=500MB --network=host --mount type=volume,source=dbvolume,target=/var/lib/postgresql/data -d --name db1 -e POSTGRES_PASSWORD=pass1234 postgres
        ```
    - ### by bind mounting:
        ```
        sudo docker run -it --memory=500MB --network=host --mount type=bind,source=/MyFiles/OSC/Docker-Workshop-Tasks/Session3/data,target=/var/lib/postgresql/data -d --name db1 -e POSTGRES_PASSWORD=pass1234 postgres
        ```
- ## Q2 
    - ### firstly, used this command for c1, c2, c3, and c4
        ```
        sudo docker run --name c1 -itd --network=session3 alpine
        ``` 
    - ### ping from c1 to c2 by name:
    ![Q2-1](Screenshot%20from%202024-02-09%2002-59-56.png)
    - ### ping from c3 to c4 by ip:
    ![Q2-2](Screenshot%20from%202024-02-09%2003-00-43.png)
- ## Q3
    ![Q3](Screenshot%20from%202024-02-09%2003-14-33.png)

- ## Q4
    - ### db1 --> 127.0.0.1
    - ### c1 --> 172.18.0.2
    - ### c2 --> 172.18.0.3
    - ### c3 --> 172.18.0.4
    - ### c4 --> 172.18.0.5
     
   