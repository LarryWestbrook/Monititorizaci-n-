# Procesos

**ps**: Muestra información de los procesos activos.

**top**: Proporciona una visión en tiempo real de los procesos que consumen más recursos,
como la CPU y la memoria.

**htop**: Similar a top, pero con una interfaz más visual y funciones adicionales, como la
capacidad de desplazarse y filtrar procesos de manera más intuitiva.

**atop**: Registra e informa de la actividad de todos los procesos del servidor. Guarda estádisticas del sistema. Empieza a tomar datos desde el momento qu ese instala. Es un servicio: systemctl status atop. Fichero de configuración: /etc/default/atop. Veremos un fichero loginterval=600s. /var/log/atop/atop_FECHA la fecha va variendo. Una vez dentro del archivo g=generico, m=memoria, c=CPU, d=discos, t=vana instantaneas, T=retrocede instantaneas, b=202311201222 busca lo que ha pasado en esa fecha y hora.

## Comandos sobre los procesos

```sh
$ ps --> muestra una lista de procesos en ejecución en el terminal. 

$ ps a --> Este comando muestra una lista de todos los procesos en ejecución en el sistema.

$ ps au --> Este comando muestra información más detallada sobre los procesos, incluyendo el nombre del usuario que inició el proceso y más detalles sobre el uso de recursos.

$ ps aux --> muestra todos los procesos que se ejecutan en segundo plano. 

$ ps -C nano --> Busca todos los procesos relacionados con la herramienta nano por ejemplo.

$ ps -U alumno --> Muestra los procesos en ejecución con el usuario alumno
```

```sh
$ top --> Nos da información sobre procesos, memoria (M), cpu (P), pid (N), etc. Tambien se pueden para ordenar por distintos procesos poniendo en mayuscula la letra del proceso. Se pueden seleccionar los cambios que nos interesan con la letra f y para desactivar los campos pulsamos espacio. 

$ top -b -n 3 >top.info --> nos hace tres capturas o instantaneas sobre los procesos y nos las envia a un documento. 

$ top -b -n 3 -o +%CPU |head -n 10  > larry3.info --> selecciona las 10 primeras lineas del proceso y me da informacion de la CPU.
```

```sh
$ atop -r /var/log/atop/atop_FECHA = cat o nano
```
```sh
# kill -9 [nº del proceso] detiene los procesos en segundo plano
# pkill -9 -u alumno --> cierra session del usuario
# killall xclock --> cierra todos los procesos de xclock &
```

# MEMORIA, ESPACIO Y RENDIMIENTO DEL DISCO

**free**: Muestra la cantidad de memoria libre y utilizada en el sistema.

**df**: Muestra el espacio utilizado y disponible en los sistemas de archivos montados.

**du**: Muestra el espacio ocupado por un fichero o directorio.

**iostat**: Se utiliza para rastrear los problemas de rendimiento de los dispositivos de
almacenamiento.


```sh
$ free --> se utiliza para mostrar información sobre el uso de la memoria en el sistema.

$ free -s 3 --> Esta opción actualiza la salida del comando cada 3 segundos. La salida se refrescará automáticamente cada tres segundos, mostrando la evolución del uso de la memoria durante ese tiempo.

$ free -c 3 --> especificas el número de veces que se mostrará la salida del comando. En este caso, la salida se mostrará tres veces y luego el comando finalizará.

```

```sh 
$ df -h --> te muestra lo que esta montado en el disco
$ df -hT --> se utiliza para mostrar información sobre el uso del espacio en disco en el sistema de archivos.
```
