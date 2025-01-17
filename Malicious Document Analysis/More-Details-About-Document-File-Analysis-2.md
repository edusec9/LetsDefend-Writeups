## Hay que analizar el siguiente archivo:
![image](https://github.com/user-attachments/assets/4b153e6f-2645-4fb0-91f9-152541535198)

**Does the file "/root/Desktop/QuestionFiles/PO-465514-180820.doc" contain a VBA macro?**

Usando el comando `oleid PO-465514-180820.doc` podemos ver que el archivo contiene VBA Macros

![image](https://github.com/user-attachments/assets/3d888628-4c61-4049-b85b-1a28a2d03270)

---

**Some malicious activity occurs when the document file "/root/Desktop/QuestionFiles/PO-465514-180820.doc" is opened. What is the macro keyword that enables this?**

Usando el comando `olevba PO-465514-180820.doc` la macro keyword es document_open. Esto quiere decir que cuando se abre el archivo `PO-465514-180820.doc` se ejecuta el codigo malicioso.

![image](https://github.com/user-attachments/assets/eefa0064-80eb-4616-adcf-6c3e24db99e6)

![image](https://github.com/user-attachments/assets/d4038b05-628e-4cd1-b557-242bd9e11c5f)
---

**Who is the author of the file "/root/Desktop/QuestionFiles/PO-465514-180820.doc"?**

Usando el comando `oleid PO-465514-180820.doc` el autor es el siguiente:

![image](https://github.com/user-attachments/assets/e6c07e6c-13b7-4abd-a9d5-eff587605416)

---

**What is the last saved time of the "/root/Desktop/QuestionFiles/PO-465514-180820.doc" file?**

Usando el comando `exiftool PO-465514-180820.doc` podemos saber la ultima hora en la que fue guardado el archivo.

![image](https://github.com/user-attachments/assets/134fbcb8-4989-45dc-8ddc-01c955e581f4)

---

**The malicious file "Siparis_17.xls" is trying to download files from an address. From which domain is it trying to download the file?**

`olevba Siparis_17.xls`

![image](https://github.com/user-attachments/assets/cba989d7-7d60-445c-9266-14e85eb9c40b)

---
**How many IOCs are in the "Siparis_17.xls" file according to the Olevba tool?**
IOC signfica Indicator of Compromise (Indicador de Compromiso). Son datos que ayudan a los analistas a identificar actividades sospechosas o maliciosas en un sistema o red. Pueden ser Direcciones IP maliciosas,C2 (command & control), dominios sospechosos y archivos maliciosos. 

![image](https://github.com/user-attachments/assets/d0857d1d-d230-4af6-8237-a5ef383fc7ca)

**En este caso hay 2 IOCs**
- `http://hocoso.mobi` URL malicioso
- `6LeGwKmrm.jar` Archivo ejecutable

---

## Analisis Avanzado

Luego de responder todas las preguntas del laboratorio me gustaria analizar profundamente el codigo de forma clara y deofuscado. Para eso lo primero que hay que hacer es pasar la extension del archivo de `.doc` a `.vba` para anlizarlo en **Visual Studio Code**. Hay que utilizar el comando: `olevba baddoc.doc > baddoc.vba`. Luego para deofuscar el codigo y que sea totalmente legible hay que utilizar el siguiente comando: `olevba --deobf --reveal baddoc.vba > baddoc-deofuscado.vba`. Luego en **Visual Studio** abrimos el archivo `baddoc-deofuscado.vba`.


