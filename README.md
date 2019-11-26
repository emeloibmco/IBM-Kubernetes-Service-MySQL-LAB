# IBM-Kubernetes-Service-MySQL-LAB



## Índice

* Creación de clúster desde IBM Cloud
* Sección de contenedores en la plataforma de IBM Cloud.
* Dashboard de Kubernetes de IBM Cloud
* Conexión al clúster de Kubernetes desde un entorno Ubuntu.
* Despliegue de MySQL.

## Introducción

En la siguiente guía puede observar cómo se realiza la conexión al clúster de Kubernetes y posteriormente el despliegue de MySQL.
Antes de conectarnos al clúster vamos a ver cómo crear uno desde la plataforma de IBM Cloud.

## Creación de clúster desde IBM Cloud

Para realizar la creación del clúster, se dirige a la página principal de IBM Cloud https://www.ibm.com/cloud, una vez allí va a iniciar sesión con su cuenta de IBM Cloud.

<img width="650" alt="1" src="https://user-images.githubusercontent.com/50923637/69644366-90aeb780-1032-11ea-88e9-47532a2b9469.png">

Una vez le haya dado click en log-in, va a aparecer la siguiente pantalla.

<img width="650" alt="2" src="https://user-images.githubusercontent.com/50923637/69644599-dd928e00-1032-11ea-86f2-da1af7377614.png">

Luego de la autenticación de usuario y contraseña, se va a ver la página inicial de IBM Cloud donde puede verificar los servicios y aplicaciones que tiene creados actualmente, Una vez allí se va a dirigir al apartado que dice “Catalogo”.

<img width="650" alt="3" src="https://user-images.githubusercontent.com/50923637/69644822-29453780-1033-11ea-85e7-fa7c2e2a7b15.png">

En el apartado de catálogo puede observar todos y cada uno de los servicios que ofrece IBM dentro de su nube, y allí se va a dirigir a la sección de contenedores.

<img width="650" alt="4" src="https://user-images.githubusercontent.com/50923637/69644928-54c82200-1033-11ea-9927-f7db66fb3ea2.png">

Y allí es donde va a proceder a crear el clúster, para eso seleccionamos el servicio que dice IBM Cloud Kubernetes Services.

<img width="650" alt="5" src="https://user-images.githubusercontent.com/50923637/69645039-7de8b280-1033-11ea-9312-47bed99aa7b5.png">

Una vez ingresemos al servicio de IBM Cloud Kubernetes Service (IKS), la pagina muestra las características y varios links de ayuda del servicio donde se puede encontrar por ejemplo la documentación correspondiente, luego vamos a hacer click en el banner que dice “Create”. 

<img width="650" alt="6" src="https://user-images.githubusercontent.com/50923637/69645170-bb4d4000-1033-11ea-9fe0-2df0bae2f54a.png">

A partir de ese momento se visualiza la página donde podemos crear el clúster con la configuración que más se adapte a la necesidad, por ejemplo: 

-	En la siguiente pantalla podemos ver y seleccionar las opciones que ofrece el servicio como el grupo de recursos, el tipo de clúster.

<img width="650" alt="7" src="https://user-images.githubusercontent.com/50923637/69645281-edf73880-1033-11ea-96dc-d30415d8a98e.png">

-	Luego vamos a ver la locación donde se puede aprovisionar el clúster según la oferta de IBM:

<img width="650" alt="7" src="https://user-images.githubusercontent.com/50923637/69646790-6b23ad00-1036-11ea-8e5c-f0bb032fe3e9.png">

-	Después de elegir la ubicación, hay que seleccionar la versión de Kubernetes que se quiera utilizar para el clúster que se está creando.

<img width="650" alt="7" src="https://user-images.githubusercontent.com/50923637/69646609-13854180-1036-11ea-8037-4648749792c7.png">

-	Ahora hay que seleccionar el aislamiento de hardware con servidores virtuales públicos y dedicados y por otra parte baremetal, según se ajuste a las necesidades del clúster que se esté creando.

<img width="650" alt="10" src="https://user-images.githubusercontent.com/50923637/69646948-a7570d80-1036-11ea-9e74-0c5c415613e5.png">

-	Una vez se haya seleccionado la capacidad de hardware requerida, muestra la opción de encriptar o no el disco local, el número de worker nodes y para finalizar hay que seleccionar el nombre deseado al clúster y dar click en el botón de “Create Cluster”.

<img width="650" alt="11" src="https://user-images.githubusercontent.com/50923637/69647034-ce154400-1036-11ea-90c8-630ab0032f72.png">

Una vez se haya creado el clúster hay que esperar alrededor de 15 minutos para que se aprovisione en la ubicación elegida y con las configuraciones elegidas para el clúster que creamos.

## Sección de contenedores en la plataforma de IBM Cloud.

Una vez se haya creado y aprovisionado el clúster nos va a al a sección de contenedores de IBM Cloud donde podemos observar algunas características y propiedades del clúster creado anteriormente.

-	Overview: En este apartado se puede crear varios clústeres 

<img width="650" alt="12" src="https://user-images.githubusercontent.com/50923637/69647186-0ae13b00-1037-11ea-8bd7-512a2fe23907.png">

-	Clusters: En la sección se revisa los clústeres que tenemos creados y varias de sus propiedades al ingresar en cada uno de ellos, como por ejemplo el acceso al clúster seleccionado que se va a tratar en este manual, el estado, la fecha de creación, los worker nodes y los worker pools.

<img width="650" alt="13" src="https://user-images.githubusercontent.com/50923637/69647286-33693500-1037-11ea-86ae-11a0a904d24d.png">

-	Registry: En el apartado de registry se puede observar los repositorios que tenemos, los namespaces y las imágenes que tenemos en los clústeres que tenemos creados.

<img width="650" alt="14" src="https://user-images.githubusercontent.com/50923637/69647378-5eec1f80-1037-11ea-9911-d2177c1e546b.png">

-	Vulnerability Advisor: En este entorno podemos añadir excepciones y configurar diferentes políticas según lo deseado

<img width="650" alt="15" src="https://user-images.githubusercontent.com/50923637/69647476-8d69fa80-1037-11ea-85bb-7cd204e20f17.png">

-	Solutions: Desde el apartado de soluciones podemos desplegar servicios o soluciones desde Helm Charts que lo cual permite realizar despliegues rápidos para el IKS y adicionalmente el catálogo de soluciones que se pueden desplegar desde allí.

<img width="650" alt="16" src="https://user-images.githubusercontent.com/50923637/69647552-b5f1f480-1037-11ea-97ed-e83ed443b0c1.png">

Y básicamente en esta sección de contenedores es donde podemos jugar con todas las características y agregados que ofrece IBM para este servicio.

## Dashboard de Kubernetes de IBM Cloud

En esta sección vamos a conocer brevemente la plataforma de Kubernetes donde podemos revisar todos y cada uno de los parámetros importantes de nuestro clúster creado como por ejemplo los nodos, los namespaces, los volúmenes persistentes, los despliegues, los pods y los servicios creados como se va a mostrar a continuación.

-	Tablero inicial: Aquí la plataforma va a mostrar varias métricas de nuestro clúster como por ejemplo la CPU usada y la memoria en uso y además despliega diferentes opciones nombradas anteriormente.

<img width="650" alt="16" src="https://user-images.githubusercontent.com/50923637/69647670-e6399300-1037-11ea-9106-838696eb0bf0.png">

-	Namespaces: En esta sección podemos ver los namespaces que están creados en nuestro clúster y poder revisar información de cada uno de ellos con solo hacer clic en su nombre.

<img width="650" alt="16" src="https://user-images.githubusercontent.com/50923637/69647757-0e28f680-1038-11ea-9c81-5e101b9e58e4.png">

-	Nodos: En la sección de nodos como su nombre lo dice podemos ver cada uno de los nodos de nuestro clúster para este caso serian dos, además podemos ver los recursos que cada uno de ellos consume.

<img width="650" alt="16" src="https://user-images.githubusercontent.com/50923637/69647851-39134a80-1038-11ea-8786-4eb8a47aa4a5.png">

-	Persistent Volumes: En este apartado puede revisar los volúmenes creados para realizar despliegues desde el Helm Chart de la plataforma de contenedores de IBM Cloud.

<img width="650" alt="16" src="https://user-images.githubusercontent.com/50923637/69647975-695ae900-1038-11ea-951b-862499c0dc11.png">

-	Deployments: En esta sección se puede evidenciar cada uno de los despliegues realizados desde el clúster creado.

<img width="650" alt="16" src="https://user-images.githubusercontent.com/50923637/69648068-9ad3b480-1038-11ea-8c59-6a34ebdfda88.png">

-	Pods: En este caso en la parte de pods podemos revisar el pod o pods creados a partir de nuestro primer despliegue

<img width="650" alt="16" src="https://user-images.githubusercontent.com/50923637/69648228-df5f5000-1038-11ea-8162-6712eec6a8d4.png">

-	Services: En esta sección se evidencian los servicios que son necesarios crear para realizar un despliegue como se muestra en este manual.

<img width="650" alt="16" src="https://user-images.githubusercontent.com/50923637/69648245-e9814e80-1038-11ea-9663-ba55868edade.png">

Y esta fue una breve introducción de la plataforma de Kubernetes de IBM Cloud, y como podemos interactuar más de cerca con cada una de las características del clúster creado y en dado caso despliegues realizados.

## Conexión al clúster de Kubernetes desde un entorno Ubuntu.

Iniciar el servicio de Kubernetes desde el terminal de Linux: ```ibmcloud cs init```.

<img width="650" alt="24" src="https://user-images.githubusercontent.com/50923637/69648403-45e46e00-1039-11ea-8b85-04f05bf28075.png">

Loguearse y hacer target a la cuenta: ```ibmcloud login --sso``` abrir la cuenta de IBM Cloud en el navegador; copiar y pegar el código que nos arroja la página luego de esto seleccionar la cuenta deseada, como se ve a continuación: 

<img width="650" alt="25" src="https://user-images.githubusercontent.com/50923637/69648508-73311c00-1039-11ea-8185-1cffcef80ed6.png">

Una vez ejecute el comando, el terminal le preguntara si quiere abrir el link para obtener el código que se usara una vez, tendrá que digitar la tecla “Y” para que así abra el navegador y pueda acceder a su cuenta de IBM Cloud como lo puede ver:

<img width="650" alt="26" src="https://user-images.githubusercontent.com/50923637/69648641-b55a5d80-1039-11ea-9228-a8748aaaa622.png">

<img width="650" alt="27" src="https://user-images.githubusercontent.com/50923637/69648689-c7d49700-1039-11ea-8daf-014f1522fe3f.png">

<img width="650" alt="28" src="https://user-images.githubusercontent.com/50923637/69648697-ca36f100-1039-11ea-9889-20408c4f7b18.png">

Una vez obtenga el código de un solo uso, lo tiene que copiar y pegar en el termina para que le dé a elegir la cuenta con la cual desea iniciar sesión.

<img width="650" alt="29" src="https://user-images.githubusercontent.com/50923637/69648789-f6eb0880-1039-11ea-9e08-58a88969406c.png">

Una vez ingrese a su cuenta debe conectarse a la región donde se encuentra el clúster con el siguiente comando: ```ibmcloud cs region-set us-east```.

<img width="650" alt="30" src="https://user-images.githubusercontent.com/50923637/69648791-f8b4cc00-1039-11ea-8690-17099de07f70.png">

Luego de esto tiene que obtener la configuración del clúster con el siguiente código: ```ibmcloud cs cluster-config <nombre del cluster>```.

<img width="650" alt="31" src="https://user-images.githubusercontent.com/50923637/69648957-47626600-103a-11ea-961c-ae67fb200188.png">

Para exportar la configuración del clúster para así poder habilitar y usar la línea de comandos de Kubernetes tiene que copiar la salida que nos generó cuando ingresamos a la configuración del clúster de la siguiente manera:

<img width="650" alt="32" src="https://user-images.githubusercontent.com/50923637/69649128-8e505b80-103a-11ea-876c-b1a877fe6ea5.png">

Una vez habilitado la línea de comandos de Kubernetes, podemos revisar las propiedades de nuestro clúster desde la consola como lo vamos a ver con los siguientes comandos: 

•	kubectl get pods: Nos permite revisar los pods que tenemos creados en el clúster.

<img width="650" alt="33" src="https://user-images.githubusercontent.com/50923637/69649181-a88a3980-103a-11ea-9be6-704bc47f6b6f.png">

•	kubectl get nodes: Nos permite revisar los nodos que tenemos actualmente en nuestro clúster e información varia de los mismos.

<img width="650" alt="34" src="https://user-images.githubusercontent.com/50923637/69649415-00c13b80-103b-11ea-8e46-367155511cce.png">

Una vez esté conectado al clúster y habilitada la línea de comandos de Kubernetes, vamos a ver cómo realizar el despliegue de MySQL.

## Despliegue de MySQL

Para comenzar a realizar este despliegue primero hay que tener claros varios conceptos como, por ejemplo:

-	Persistant Volume (PV): Los volúmenes persistentes en Kubernetes es una pieza de almacenamiento aprovisionada por el administrador, este es un recurso del clúster al igual que un nodo. Son complementos del volumen del clúster, pero estos tienen un ciclo de vida independiente de cualquier pod individual, este API object captura los detalles de la implementación en la nube o sobre cualquier otro protocolo.

-	Persistant Volume Claim (PVC): La reclamación del volumen persistente es una solicitud de almacenamiento por parte del usuario, su comportamiento es similar al de los pods, los pods consumen recursos del nodo mientras que los PVC consumen recursos de los volúmenes persistentes, los pods solicitan varios recursos como por ejemplo (CPU y memoria); los PVC pueden solicitar diferentes tipos de tamaño y accesos específicos por ejemplo (montarse una vez con permisos de lectura/escritura).

Una vez aclarados los dos conceptos se procede a realizar el despliegue de una imagen de MySQL en Kubernetes.

Para crear el despliegue es necesario ejecutar el siguiente archivo desde la consola de comando de Kubernetes en el entorno Ubuntu para que así toma el archivo YAML y cree el volumen persistente y su respectivo claim.

```
kind: PersistentVolume
apiVersion: v1
metadata:
  name: mysql-pv-volume-2
  labels:
    type: local
spec:
  storageClassName: manual
  capacity:
    storage: 1Gi
  accessModes:
    - ReadWriteOnce
  hostPath:
    path: "/mnt/data"
---
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: mysql-pv-claim-2
spec:
  storageClassName: manual
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 1Gi
```

Con la siguiente línea de comandos vamos a ejecutar este archivo y así a crear el despliegue ```kubectl create -f <ruta donde se encuentra alojado el archivo YAML>``` para que genere el despliegue en el cluster de la siguiente manera.

<img width="650" alt="35" src="https://user-images.githubusercontent.com/50923637/69649721-762d0c00-103b-11ea-9652-26e51a7caf4d.png">

Una vez arroje la consola el mensaje de que fueron creados exitosamente vamos a revisar el otro archivo YAML que es donde se encuentran los parametros para realizar el despliegue, y se ingresa en consola el siguiente comando, ```kubectl create -f <ruta donde se encuentra el archivo YAML del despliegue>```, el archivo debe buscarlo dentro del repositorio y hacer las acciones que se le indican en la guia, el archivo esta nombredo como ```mysql-deployment.yaml```.

Luego de esto acceder se da validacion como falso, esto se hace para dar un permiso de despliegue que por defecto no está dado, esto se realiza de la siguiente forma:

<img width="650" alt="36" src="https://user-images.githubusercontent.com/50923637/69650165-2f8be180-103c-11ea-96c4-4ddd6b96dea0.png">

<img width="650" alt="37" src="https://user-images.githubusercontent.com/50923637/69650173-3286d200-103c-11ea-8848-0a456187ecba.png">

Una vez ingresa el comando la consola responde con dos mensajes unos donde indica que el despliegue ha sido creado y otro notificando que el servicio “mysql” ha sido creado.

Una vez se haya hecho el proceso anterior vamos a la consola de kubernetes a verificar que efectivamente se creó lo anteriormente nombrado.

Para el caso del volumen persistente se puede observar en el apartado de persistant volume que fue creado correctamente.

<img width="650" alt="38" src="https://user-images.githubusercontent.com/50923637/69650369-81346c00-103c-11ea-93f4-1a8341cf9245.png">

Para el caso del despliegue se puede observar en el apartado de deployments.

<img width="650" alt="39" src="https://user-images.githubusercontent.com/50923637/69650493-b0e37400-103c-11ea-9965-67f84e07a468.png">

El servicio igualmente fue creado en el procedimiento anterior

<img width="650" alt="39" src="https://user-images.githubusercontent.com/50923637/69650603-d8d2d780-103c-11ea-863e-946feceb775b.png">

El persistant volume claim ya fue creado, cabe agregar que el codigo YAML puede ser editado para configurar parametros como por ejemplo el tamaño de cada uno 

<img width="650" alt="39" src="https://user-images.githubusercontent.com/50923637/69650756-12a3de00-103d-11ea-948f-efc70ca97573.png">

Adicionalmente podemos ver la descripción de cada uno de los elementos que se crearon anteriormente.

*Volumen persistente*

<img width="650" alt="39" src="https://user-images.githubusercontent.com/50923637/69650989-66aec280-103d-11ea-8d39-8709c3288595.png">

Pods

<img width="650" alt="39" src="https://user-images.githubusercontent.com/50923637/69651139-a1185f80-103d-11ea-92c2-ea8d3418ee3a.png">

Reclamo del volumen persistente 

<img width="650" alt="39" src="https://user-images.githubusercontent.com/50923637/69651246-c907c300-103d-11ea-8fc6-059bdf555755.png">

Para empezar a correr MySQL en Kubernetes debe digitar el siguiente comando en la consola.

```kubectl run -it --rm --image=mysql:5.6 --restart=Never mysql-client -- mysql -h mysql -ppassword```

<img width="650" alt="39" src="https://user-images.githubusercontent.com/50923637/69651758-94483b80-103e-11ea-958c-651f2e23d8d9.png">

Como puede ver ya puede escribir comandos de MySQL en la consola de Ubuntu.

El siguiente comando se utiliza para ejecutar el comando en el container.

```kubectl exec -h```

<img width="650" alt="46" src="https://user-images.githubusercontent.com/50923637/69652624-f7869d80-103f-11ea-9025-2e39da3875c8.png">

Luego se da el siguiente comando para acceder al cluster y poder luego ingresar los comandos correspondientes de MySQl en el ejemplo se ejecuta un comando en MySQl para ver las tablas existentes.

```kubectl exec -it mysql-<Nombre de su archivo>  /bis/sh ```

<img width="650" alt="47" src="https://user-images.githubusercontent.com/50923637/69652890-54825380-1040-11ea-9e53-457d60320fde.png">

