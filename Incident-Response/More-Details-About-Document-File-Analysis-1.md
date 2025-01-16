## Hay que seguir analizando los siguientes archivos:

![image](https://github.com/user-attachments/assets/8dc23c1c-7968-4273-8f2b-d3f62130abca)

En este analisis nos vamos a centrar en el analisis de **VBA Macros*. Los macros VBA (Visual Basic for Applications) se utilizan en aplicaciones de Microsoft Office, como Excel, Word y PowerPoint, para automatizar tareas repetitivas. Sin embargo, algunas macros pueden convertirse en malware si son diseñadas con intenciones maliciosas. Existen herramientas como **oleid** y **olevba** que detectan si hay uso de VBA Macros maliciosos.

## oleid
- A diferencia de `olevba`, esta herramienta es para hacer un analisis basico
- Se usa para detectar rapidamente la presencia de macros
- Comprobar si el archivo esta cifrado
- Indica si hay enlaces externos maliciosos
Comando utilizado: `oleid baddoc.doc`

![image](https://github.com/user-attachments/assets/fc33a9af-9a0d-432b-8417-81548b070834)

Indica que hay VBA Macros por lo que el siguiente paso es usar `olevba` para un analisis mas profundo.

## olevba
Es una herramienta más avanzada que extrae y analiza macros VBA (Visual Basic for Applications) de archivos OLE. Su objetivo principal es detectar y examinar código VBA malicioso.
- Extraer macros VBA de un archivo.
- Detectar patrones comunes de malware en macros.

Comando utilizado: `olevba baddoc.doc`
![image](https://github.com/user-attachments/assets/f47691c9-aaee-423f-b464-d6e34609cd07)

> - Indica lo que hace cada parte del codigo, por ejemplo `User-Agent` el cual podria descargar archivos de internet.
>
> ![image](https://github.com/user-attachments/assets/54dceb06-3826-4fa5-978d-9f0c7dd6e171)

 
> - `Kill` elimina archivos.
>   
> ![image](https://github.com/user-attachments/assets/b0daf486-ac62-4e2f-b2bd-741143904213)

> - `Base64 Strings`,`Hex strings` y `Chr` es una manera de ofuscar el codigo para que no sea detectado como malware.
>
> ![image](https://github.com/user-attachments/assets/7239f99b-e906-41f4-a5b7-be6e83baf83a)
>
> ![image](https://github.com/user-attachments/assets/6fefe10e-3b16-4a5a-8ed1-d6454392b1ba)



  


