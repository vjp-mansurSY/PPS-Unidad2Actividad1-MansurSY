# PPS-Unidad2Actividad1-MansurSY

# Trazado de una vulnerabilidad.
Actividad 1 de la Unidad 1 de Puesta en Producción Segura. Tabajaremos con los Entornos de Desarrollo

Tenemos varios objetivos:

> [Conocer las diferentes listas que tienen que ver con amenazas de seguridad.](#Listas)

> [Obtener información de una vulnerabilidad navegando por las webs de los organismos que mantienen esas listas.](#Trazado)

> [Actividad del trazado de la vulnerabilidad GoAnywhere MFT.](#Trazado-de-la-vulnerabilidad)

---
## Listas

En [este enlace](https://moodle.educarex.es/ccff_iesvjp/pluginfile.php/27882/mod_resource/content/17/PresentacionUnidad2NivelesSeguridadAplicaciones2025.pdf) puedes ver la presentación donde se pueden encontrar información sobre las organizaciónes y agencias que mantienen información sobre amenazas, vulnerabilidades, debilidades etc.

Vemos que es grande la información en fuentes abiertas que podemos consultar. Aquí nos centraremos en obtener información principalmente de las siguientes listas:
- [Lista de vulnerabilidades comunes: CVE.](https://www.cve.org/)

- [Base de datos de vulnerabilidades: NVD.](https://www.nist.gov/)

- [Lista de debilidades comunes: CWE.](https://cwe.mitre.org/)

- [Lista de plataformas comunes: CPE.](https://cpe.mitre.org/)

- [Lista de patrones de ataque: CAPEC.](https://capec.mitre.org/)


También vamos a ver información de información adicional:

- [Ver el grado de criticidad de una vulnerabilidad y a partir de qué datos se calcula: CVSS.](https://www.first.org/cvss/)

[- [Ver el marco MITRE ATT&CK ](https://attack.mitre.org/)]:#

## Trazado
Vamos a seguir el trazado de una vulnerabilidad a partir del [este artículo del INCIBE](https://www.incibe.es/empresas/avisos/autodesk-ha-publicado-multiples-vulnerabilidades-que-afectan-autocad).

Como vemos nos informan de varias vulnerabilidades presentes en la aplicación AutoCad, desarrollado por Autodesk.

Como en este artículo no nos dán información sobre el número de la vulnerabilidad, nos vamos al apartado de referencias, donde encontramos enlaces a las noticias publicadas por el desarrollador:

Dándole al enlace nos lleva a la página: [https://www.autodesk.com/trust/security-advisories/adsk-sa-2023-0018](https://www.autodesk.com/trust/security-advisories/adsk-sa-2023-0018)

![image](https://github.com/user-attachments/assets/acb7c3cd-9f9f-46d8-8746-16592e78811f)


## Información sobre Vulnerabilidades
Allí vemos una descripción de los problemas y cómo, son varias las vulnerabilidades detectadas:

Además el desarrollador, nos informa de los productos y versiones afectadas y desde dónde nos podemos descargar los parches de seguridad o software con las vulneravilidades ya corregidas.

![image](https://github.com/user-attachments/assets/e7df15fd-0ac4-4a87-9791-81de5864b481)

Vamos a proceder con el trazado de la primera vulnerabilidad presente, en nuestro caso, la __CVE-2023-29073__.

Para ver información sobre dicha vulnerabilidad podemos acudir al menos a dos fuentes:

- [La sección de CVE que mantiene cve.org.](https://cve.org)

- [La base de datos de vulnerabilidades de la NIST: NVD.](https://nvd.nist.gov/vuln/detail/CVE-2023-29073)

## Información sobre el riesgo o criticidad de una vulnerabilidad

Desde la [entrada correspondiente a la vulnerabilidad en la NVD](https://nvd.nist.gov/vuln/detail/CVE-2023-29073), lo primero que nos encontramos, es la información de la criticidad que la vulnerabilidad presenta, así como el vector asociado a dicho nivel en la CVSS. En este caso vemos que tiene una valoración de 9.8, y está marcada como __crítica__.
 
![image](https://github.com/user-attachments/assets/56c8e5a7-e0f8-48a6-bbdb-87b4fc2fe617)

Si ponemos el cursor sobre el Vector nos aparecerán los valores correspondientes a las diferentes métricas que se han usado para calcularlo.

![image](https://github.com/user-attachments/assets/7db17e57-1b19-410a-a4ba-be0831c9a110)

## Información sobre las debilidades explotadas.

Otra información importante a obtener son las debilidades que son explotadas. Podemos obtener también esta información tanto en la información de la NVD como en la de CVE.ORG.

![image](https://github.com/user-attachments/assets/c3dadeea-ce64-4395-ae2f-fe847d79f0de)

En esta ocasión podemos ver como son dos las debilidades explotadas por esta vulnerabilidad: CWE-787 y CWE-122. Vamos a ver información sobre ellas.

- CWE-787

> [Podemos ver información de esta debilidad en la página de cwe.mitre.org](https://cwe.mitre.org/data/definitions/787.html)
>
> Dentro de la información mostrada en dicha página, podemos tener diferentes vistas, tal y como podemos ver en la imagen siguiente. Si le damos a __Complete__ tendremos toda la información visible.
>
> ![](images/cwe1.org)
>
> De la información mostrada, podemos extraer, que la debilidad explotada, consiste en la escritura en posiciones fuera de los límites de la memoria, y esto podría ser utilizado para modificar los datos de control, direcciones de retorno e incluso ejecutar código.
>
> Las posibles soluciones o mitigaciones que nos ofrecen son usar lenguajes donde no se produzca el desbordamiento del buffer o sea más fáciles de evitar. 
>
> También podemos ver las posibles mitigaciones que podemos efectuar en las fases de arquitectura y diseño, como utilizar diferentes librerías y métodos.
>
> Más información a obtener... por ejemplo podemos observar como son debilidades presentes en lenguajes como C y C++, por lo que seguramente la aplicación está escrita en alguno de ellos. 
>
> ![image](https://github.com/user-attachments/assets/445934c3-e2ed-4cf1-ba7c-30b662942287)
>
> También, por último, podemos ver las relaciones entre ésta y otras debilidades, ya que como podemos ver en la imagen ![](images/cwe3.org), esta debilidad ha surgido a partir de la CWE-119 y es padre de la CWE-121 y CWE-122 que es la otra debilidad presente en la vulnerabilidad que estamos estudiando.
>
> ![image](https://github.com/user-attachments/assets/bd6a18bd-14ec-4811-91a5-fc7b5572284a)



- CWE-122
> [Podemos ver información de esta debilidad en la página de cwe.mitre.org](https://cwe.mitre.org/data/definitions/122.html)
>
> Si leemos, podemos ver cómo nos encontramos ante la debilidad de desbordamiento de pila y que se considera una variación de la anterior debilidad, por lo que es hijo de ella.
>
> También vemos que es una debilidad presente en los lenguajes C y C++ y aquí en está página podemos encontrar la relación de esta debilidad con otro listado el de patrones de ataque. Tal y como vemos en la imagen, ![](images/capec.png) para acometer esta debilidad usamos el patrón de ataque catalogado como CAPEC-92. ![image](https://github.com/user-attachments/assets/6fa691f0-4d81-49f3-a838-73dd510028f2)


## Información sobre patrones de ataque

Podemos acceder a información sobre los patrones de ataque en la lista mantenida por la Mitre en la dirección [capec.mitre.org](https://capec.mitre.org/)

En el caso que nos atañe, hemos llegado a que la vulnerabilidad que estudiamos se puede explotar mediante el [patrón de ataque CAPEC-92. Aquí tenemos enlace a él.](https://capec.mitre.org/data/definitions/92.html)

![image](https://github.com/user-attachments/assets/45df8848-8c81-41c4-957e-32b194a88841)

Como nos pasaba en la página cwe.mitre.org, aquí también podemos seleccionar la información a mostrar, dependiendo de nuestras necesidades. En caso de que queramos ver toda la información, selecionamos la vista Complete.

> Por la información suministrada, vemos que el ataque se denomina desbordamiento de enteros y consiste en obligar a una variable, dicho valor suele ser una posición de memoria, y utilizando valores fuera del rango de los valores enteros, se le asigna un valor no admitido para forzar un comportamiento inesperado.
>
> ![image](https://github.com/user-attachments/assets/328faca0-813f-4e09-a64b-2864076fd59d)
>
> Podemos ver cómo se realiza el flujo de ejecución, los requisitos previos, etc. así como las habilidades requeridas para la realización de este patrón de ataque.
>
> Por otra parte también vemos las consecuencias respecto a la integridad, confidencialidad, etc., la lista de debilidades que se pueden explotar con este patrón de ataque, así como las posibles mitigaciones que podemos realizar.
>
>![image](https://github.com/user-attachments/assets/304c39e5-900f-4d0c-97a0-7ba9d12beb43)


## Descarga del Registro CVE de la vulnerabilidad

El registro de CVE o CVE Record es un registro con información dela vulnerabilidad donde incluye información de dicha vulnerabilidad. 

Este registro se utiliza para el tratamiento automatizado de la información, pudiendo ser utilizado por diferentes utilidades de seguridad. 

En él está comprendida información en formato xml o JSON sobre CWE, CPE, CAPEC, etc..

Podemos descargarla o acceder a su información, desde la página de cve.org dándole al enlace __View JSON__
![image](https://github.com/user-attachments/assets/d954630f-9a42-4e57-865f-15dd45d9fbc7)

En algunas ocasiones nos podemos encontrar que en él figura información que no aparece en la página de la cve.

![image](https://github.com/user-attachments/assets/a184e7fb-4741-4386-a319-f74566a7fcff)

----
## Trazado de la [vulnerabilidad](https://www.incibe.es/empresas/avisos/vulnerabilidad-critica-de-omision-de-autenticacion-en-goanywhere-mft-de-fortra)

Esta es la vulenrabilidad

![image](/images/C1.png)

Primero en la propia pagina de FORTRA ya tienen clasificada la vulnerabilidad con información básica referenciando el CVE, CWE y CVSS entre otras cosas

![image](/images/C2.png)

Buscamos en la lista de CVE

![image](/images/C3.png)

Y nada mas de entrada ya nos referencia el CWE a la que afecta

![image](/images/C4.png)

También nos muestra la puntuación de impacto, el CVSS y mas referencias 

![image](/images/C5.png)

En NIST buscamos por el cve también

![image](/images/C6.png)

![image](/images/C7.png)

En las métricas volvemos a ver el vector de ataque (CVSS)

![image](/images/C8.png)

Nos muestra más información sobre el vector de ataque

![image](/images/C18.png)

Y nos referencia varias listas CPE

![image](/images/C9.png)

Vemos el CWE al que le afecta esta vulnerabilidad

![image](/images/C10.png)

Aqui tenemos bastante información como patrones de ataque, taxonomia, relaciones etc..

![image](/images/C11.png)

![image](/images/C12.png)

![image](/images/C13.png)

Buscamos en alguno de los CPE que referenciaba en el NIST, vemos información relacionada

![image](/images/C14.png)

Y los metadatos

![image](/images/C15.png)

En CAPEC también buscamos por el cve

![image](/images/C16.png)

Donde nos muestra muchos mecanismos de ataque y patrones de ataque

![image](/images/C17.png)

En la pagina de CVE le damos a la opción que pone "view json" y nos sale esto

![image](/images/C19.png)

En formato json
```
{
  "dataType": "CVE_RECORD",
  "dataVersion": "5.1",
  "cveMetadata": {
    "cveId": "CVE-2024-0204",
    "assignerOrgId": "df4dee71-de3a-4139-9588-11b62fe6c0ff",
    "state": "PUBLISHED",
    "assignerShortName": "Fortra",
    "dateReserved": "2024-01-03T00:12:28.436Z",
    "datePublished": "2024-01-22T18:05:13.194Z",
    "dateUpdated": "2025-02-13T17:27:06.436Z"
  },
  "containers": {
    "cna": {
      "affected": [
        {
          "defaultStatus": "affected",
          "product": "GoAnywhere MFT",
          "vendor": "Fortra",
          "versions": [
            {
              "lessThan": "7.4.1",
              "status": "affected",
              "version": "6.0.1",
              "versionType": "semver"
            }
          ]
        }
      ],
      "descriptions": [
        {
          "lang": "en",
          "value": "Authentication bypass in Fortra's GoAnywhere MFT prior to 7.4.1 allows an unauthorized user to create an admin user via the administration portal."
        }
      ],
      "metrics": [
        {
          "cvssV3_1": {
            "attackComplexity": "LOW",
            "attackVector": "NETWORK",
            "availabilityImpact": "HIGH",
            "baseScore": 9.8,
            "baseSeverity": "CRITICAL",
            "confidentialityImpact": "HIGH",
            "integrityImpact": "HIGH",
            "privilegesRequired": "NONE",
            "scope": "UNCHANGED",
            "userInteraction": "NONE",
            "vectorString": "CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H",
            "version": "3.1"
          }
        }
      ]
    }
  }
}
```

----
## ENTREGA
> __Realiza el trazado de la vulnerabilidad de la que informa [este artículo](https://www.incibe.es/empresas/avisos/vulnerabilidad-critica-de-omision-de-autenticacion-en-goanywhere-mft-de-fortra)__

>__Crea un repositorio  con nombre PPS-Unidad2Actividad1-Tu-Nombre donde desarrolles dicho trazado.__

> No te olvides de documentarlo convenientemente con explicaciones, capturas de pantalla, etc.

>__Sube a la plataforma, tanto el repositorio comprimido como la dirección a tu repositorio de Github.__
