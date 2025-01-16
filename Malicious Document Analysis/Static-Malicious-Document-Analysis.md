## Hay que analizar los siguientes archivos:

![image](https://github.com/user-attachments/assets/8dc23c1c-7968-4273-8f2b-d3f62130abca)

El primer paso a la hora de analizar un archivo "malicioso" es subirlo a [virustotal](https://www.virustotal.com/gui/home/upload) ya que esta plataforma se encarga de analizar y verificar archivos mediante hashes, URLs y archivos.

---
![image](https://github.com/user-attachments/assets/ca40c527-55d8-4fcf-82dc-6dc7d909732d)

Podemos ver que se trata de un archivo malicioso el cual fue detectado por 47 antivirus de forma exitosa. Para ver mas informacion sobre el archivo, podemos usar una herramienta llamada **exiftool** la cual se usa para interactuar con metadatos de forma muy detallada y con mas de 130 formatos de archivos diferentes. Esta herramienta no es dedicada al analisis de malware pero nos sirve en este caso para analizar los metadatos, fecha de creacion, cuando fue modificado ese archivo, tipo de archivo y demas.

---

![image](https://github.com/user-attachments/assets/bca72d59-66ac-4b07-a867-e5b506fabecc)

En el analisis de metadatos lo siguiente se considera un hecho de sospechar sobre el archivo que estamos analizando:

- Comp Obj User Type              : �������� Microsoft Word 97-2003
- Create Date                     : 2015:02:08 19:56:00
- Modify Date                     : 2015:02:10 15:27:00
- Template                        : Normal.dotm *('.dotm' significa habilitado para macros, es muy probable que sea malware)*
- Heading Pairs                   : Название, 1

---

Para completar la el laboratorio se encuentran las siguientes preguntas:
![image](https://github.com/user-attachments/assets/5fc720fd-0251-4e62-888f-9942853a6a7e)

Se pueden completar mediante lo visto en este Writeup.
