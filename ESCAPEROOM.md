# ESCAPE ROOM 2026

**Nombre:** Joel David Simbaña Tasintuña
**Manual de placa base:** Gigabyte Z690 AORUS ELITE DDR4 (pdf parte1)  
**Trabajo con IA y documentos (manual Placa Base) como contexto (Skill)**

---

## FASE 1: Identificación del Factor de Forma (El Tamaño Sí Importa)

### El problema:
El cliente ha comprado una caja de ordenador ultra compacta para el salón, pero la placa base que ha intentado meter dentro es demasiado grande y no encaja en los anclajes del chasis.

### El Reto en el Manual:
Id a la primera página de especificaciones generales o al índice del manual, donde se describen las características físicas de la placa (Hardware Installation / Introduction).

### Pregunta / Desafío:
¿Según el manual de esta placa base, cuál es su factor de forma o tamaño exacto (por ejemplo: ATX, Micro-ATX, Mini-ITX, etc.)?

> La placa base tiene un formato ATX, ya que se puede ver en el layout los puertos ATX o ATX_12V_2X2, sus dimensiones son 30,5 x 24,4 cm.

### Código para avanzar:
El nombre exacto del formato físico de la placa.  
`ATX`

---

## FASE 2: El Zócalo de la CPU (Cuidado con los Pines)

### El problema:
Un compañero va a instalar el procesador en el zócalo y os pregunta cómo debe orientarlo correctamente para no doblar ningún pin ni forzar el anclaje metálico.

### El Reto en el Manual:
Buscad en la sección de instalación del procesador (CPU Installation) el nombre del zócalo.

### Pregunta / Desafío:
¿Cómo se denomina exactamente el modelo de socket o zócalo de esta placa base (por ejemplo: LGA 1700, AM5, LGA 1151, etc.)?

> Tiene el zócalo Intel LGA 1700.

¿Los pines de conexión están en este zócalo de la placa o en la parte inferior de la CPU?

> Los pines están en el zócalo

### Código para avanzar:
El código alfanumérico del socket.  
`LGA 1700`

---

## FASE 3: Los Puertos de Vídeo Traseros (La Gráfica Integrada)

### El problema:
El cliente enciende el ordenador por primera vez sin tarjeta gráfica dedicada y conecta el cable del monitor directamente a la placa base, pero no ve imagen en pantalla. Queréis comprobar qué salidas de vídeo físicas ofrece la placa de serie.

### El Reto en el Manual:
Buscad el diagrama del Panel de E/S Trasero (Back Panel Connectors / I/O Back Panel), donde se detallan todos los puertos de la parte posterior.

### Pregunta / Desafío:
¿Qué puertos de vídeo integrados (como HDMI, DisplayPort, etc.) incluye esta placa base en su parte trasera para usar con la gráfica integrada del procesador?

> Tiene un DisplayPort 1.2, con resolución f 4096x2304 a 60 Hz.

### Código para avanzar:
El tipo de puerto de vídeo principal disponible.  
`DisplayPort`

---

## AÑADIR PARTE 2 del MANUAL de la PLACA BASE

**Manual:** [https://download.gigabyte.com/FileList/Manual/mb_manual_z690-ap-series_e_1101.pdf](https://download.gigabyte.com/FileList/Manual/mb_manual_z690-ap-series_e_1101.pdf)

**Instrucciones:** Sois un equipo de técnicos de soporte de nivel 2. Un cliente os ha enviado un ordenador de alta gama recién montado que no arranca, se queda la pantalla en negro y los ventiladores giran de forma extraña. Tenéis el manual oficial de la placa base en la pantalla y 3 fases que superar para descifrar el error y levantar el sistema. ¡El tiempo corre!

---

## FASE 4: El Diagnóstico del Panel Frontal (Los "Front Panel Connectors")

### El problema:
El cliente intentó cambiar la caja del PC y ahora, al pulsar el botón de encendido (Power Button) de la torre, absolutamente nada se enciende. No hay corriente ni chispa.

### El Reto en el Manual:
Buscad en el manual de la placa el apartado dedicado a las conexiones del panel frontal (suele llamarse Front Panel Header, en los manuales de Gigabyte suele estar en la sección de instalación de hardware bajo la etiqueta F_PANEL).

### Pregunta / Desafío:
¿En qué pines exactos del bloque F_PANEL debe ir conectado obligatoriamente el interruptor de encendido (PWR_BTN / Power Switch)?

> El Power Switch debe ir conectado a los pines 6 y 8 del F_PANEL (PW+ y PW-), es decir los pines 3 y 4 empezando a contar en línea recta desde la esquina superior izquierda.

Si por error el alumno hubiera conectado los pines del Power Switch en los pines de Reset o en los de los LEDs del disco duro, ¿por qué el ordenador no muestra ninguna señal de vida?

> Porque para que el ordenador se encienda debe recibir la señal de encendido mediante los pines de encendido. En caso del Reset el botón intentará reiniciar el ordenador. En caso de los LED, no se enviará la señal de encendido y el se quedará apagado.

### Código para avanzar:
Demostrad que habéis localizado la página exacta del diagrama de pines del Front Panel en el manual.

>Página 28 
![](assets/image-20261109-19193100.png)
---

## FASE 5: El Laberinto de la Memoria RAM (Canales y Slots)

### El problema:
Tras solucionar el botón de encendido, el ordenador por fin da señal de vídeo, pero la pantalla se queda congelada mostrando un código de error de memoria y la placa base emite una secuencia de pitidos cortos continuos. El cliente ha colocado los dos módulos de memoria RAM DDR4 en los zócalos AMC_1 y AMC_2 (los dos primeros empezando desde el socket del procesador).

### El Reto en el Manual:
Buscad en el manual el apartado de Installation / Recommended Population for 2 DIMMs (Instalación de memoria en arquitectura de doble canal).

### Pregunta / Desafío:
Según el fabricante de esta placa, si solo se van a instalar dos módulos de RAM, ¿en qué ranuras específicas (por nombre de slot, ej. A2 y B2 o DDR4_1 y DDR4_2) deben colocarse obligatoriamente para activar el Dual Channel y evitar el fallo de arranque?

> Para evitar el fallo de arranque y activar el Dual Channel, los módulos de memoria RAM se deben instalar en las ranuras de expansión DDR4_A2 y DDR4_B2(2a y 4a ranura).

### Código para avanzar:
Indicad los nombres exactos de los dos zócalos recomendados por el fabricante.  
`DDR4_A2 y DDR4_B2`

---

## FASE 6: El Enigma de la UEFI y la Actualización de la BIOS (Q-Flash)

### El problema:
El PC ya arranca y entra al sistema, pero al montar un procesador de decimotercera o decimocuarta generación en esta placa Z690, el sistema no reconoce la CPU correctamente o se cuelga en el logo inicial. Necesitáis actualizar la BIOS/UEFI. Lo fascinante es que esta placa cuenta con un botón físico trasero para actualizarla sin necesidad de tener CPU ni RAM instaladas.

### El Reto en el Manual:
Buscad en el manual el apartado de la tecnología de actualización sin procesador (en Gigabyte se llama Q-Flash Plus).

### Pregunta / Desafío:
¿Cómo se llama exactamente el puerto USB trasero de color especial (o serigrafiado) donde obligatoriamente se debe conectar el pendrive USB con el archivo de la BIOS para usar esta función?

> Se llama USB 3.2 Gen 2 (rojo), identificado como Q-Flash Plus Port.

¿Qué nombre exacto debe tener obligatoriamente el archivo de la BIOS dentro del pendrive para que la placa lo reconozca al pulsar el botón Q-Flash Plus?

> El nombre del archivo debe ser gigabyte.bin.

### Código para avanzar:
El nombre del fichero o del puerto USB específico.  
`gigabyte.bin`