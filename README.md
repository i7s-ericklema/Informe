# EMU8086


## 1. PLANTEAMIENTO
Con el fin de emular el funcionamiento del microprocesador del 8086 e implementar un codigo sencillo en lenguaje ensamblador para lo cual se plantea el procediento acontinuación:
- Se busca un emulador del 8086 compatible con el Sistema Operativo que tengamos a disposición.
- Para la simulación se utiliza un programa en lenguaje esamblador (asm).
- Se verifica en el correcto funcionamiento del emulador.


## 2. OBJETIVOS
### **Objetivo General**
- Emular el compartamiento del microprocesador 8086.
### **Objetivos específicos**
- Instruirse en el uso básico del software para la simulación de programas aptos para el aprendizaje.
- Adquirir nociones básicas del lenguaje esamblador (asm).
- Implementar un programa sencillo en lenguaje esamblador.
- Analizar el comportamiento del software ****


## 3. ESTADO DEL ARTE



## 4. MARCO TEORIÓCO 
El Intel 8086 y el Intel 8088 son los primeros microprocesadores de 16 bits diseñados por Intel. Son los primeros miembros de la arquitectura x86. Fue lanzado al mercado en 1978 y el 8088 en 1979.
El 8086 y 8088 ejecutan el mismo número de instrucciones. Comparándolos internamente son idénticos a excepción del 8086 que posee una cola de 6 bytes para instrucciones y el 8088 solo posee 4. Exteriormente la diferencia es que el
8086 tiene un bus de 16 bits y el 8088 su bus es de 8 bits, por lo tanto, el 8086 es más rápido, aunque el 8088 permite la fabricación de sistemas más económicos.
En la primera computadora personal de IBM fue utilizado el microprocesador 8088, la IBM PC.

#### Características
- El 8086 dispone de instrucciones especiales para el tratamiento de cadenas de caracteres. 

- Los registros del 8086 tienen una misión específica, por lo que se podría decir que cada uno de ellos tiene su propia personalidad, aunque varios comparten tareas comunes. 

- El encapsulado del 8086 está formado por 40 patillas, simplificando así el hardware, aunque por contra, es necesario la multiplicación del bus de datos con el de direcciones.

- El 8086 requiere una señal de reloj exterior, siendo 5 y 8 Mhz las frecuencias típicas de funcionamiento.

- El 8086 dispone de un conjunto de registros, denominados ‘cola de instrucciones’, en el cual se van almacenando de forma anticipada los códigos de las instrucciones, consiguiendo que este aumente su velocidad de trabajo.

- El 8086 dispone de una arquitectura “pipe line”, es decir, que la CPU puede seguir leyendo instrucciones en los tiempos en que el bus no se utiliza

#### Estructura Interna

##### Unidad de interfaz del bus y unidad de ejecución
El 80886 y el 8088 tienen internamente dos componentes, la Unidad de Interfaz del Bus (BIU) y la Unidad   de   ejecución (EU).   La Unidad de ejecución procesa las instrucciones del CPU, mientras que la   Unidad   de   Interfaz   del   Bus maneja la lectura y escritura desde y hacia la memoria y los puertos de entrada/salida.
La ventaja de esta división fue el ahorro de esfuerzo necesario para producir el 8088. Sólo una mitad del 8086 (el BIU) tuvo que rediseñarse para producir el 8088.
Registros de uso general del 8086/8088:

##### **Tienen 16 bits cada uno y son ocho:**
- **AX=** Registro acumulador, dividido en AH y AL (8 bits cada uno). Usándolo se produce (en general) una instrucción que ocupa  un  byte  menos  que  si  se utilizaran otros registros de uso general. Su parte más baja, AL, también tiene esta propiedad. El último registro mencionado es el equivalente al acumulador de los procesadores anteriores (8080 y 8085). Además, hay instrucciones como DAA; DAS; AAA; AAS; AAM; AAD; LAHF; SAHF; CBW; IN y OUT que trabajan con AX o con uno de sus dos bytes (AH o AL). También se utiliza este registro (junto con DX a veces) en multiplicaciones y divisiones.

- **BX=** Registro base, dividido en BH y BL. Es el registro base de propósito similar (se usa para direccionamiento indirecto) y es una versión más potente del par de registros HL de los procesadores anteriores.

- **CX=** Registro contador, dividido en CH y CL. Se utiliza como contador en bucles (instrucción LOOP), en operaciones con cadenas (usando el prefijo REP) y en desplazamientos y rotaciones (usando el registro CL en los dos últimos casos).

- **DX=** Registro de datos, dividido en DH y DL. Se utiliza junto con el registro AX en multiplicaciones y divisiones, en la instrucción CWD y en IN y OUT para direccionamiento indirecto de puertos (el registro DX indica el número de puerto de entrada/salida).

- **SP=** Puntero de pila (no se puede subdividir). Aunque es un registro de uso general, debe utilizarse sólo como puntero de pila, la cual sirve para almacenar las direcciones de retorno de subrutinas y los datos temporarios (mediante las instrucciones PUSH y POP). Al introducir (push) un valor en la pila a este registro se le resta dos, mientras que al extraer (pop) un valor de la pila este a registro se le suma dos.

- **BP=** Puntero base (no se puede subdividir). Generalmente se utiliza para realizar direccionamiento indirecto dentro de la pila.

- **SI=** Puntero índice (no se puede subdividir). Sirve como puntero fuente para las operaciones con cadenas. También sirve para realizar direccionamiento indirecto.

- **DI=** Puntero destino (no se puede subdividir). Sirve como puntero destino para las operaciones con cadenas. También sirve para realizar direccionamiento indirecto.

#### Instrucciones
Las instrucciones del 8086/88 se pueden dividir en varios grupos:

##### 1. Instrucciones de transferencia de datos
Las instrucciones de transferencia de datos copian datos de un sitio a otro y son los siguientes: MOV, XCHG, XLAT, LEA, LDS, LES, LAHF, SAHF, PUSH, PUSHF, POP, POPF.

- **MOV:** Realiza la transferencia de datos del operando de origen al destino. 

![](https://github.com/Rafa1104/Informe/blob/master/img/o%201%20MOV.png)

- **XCHG:** Realiza el intercambio entre los valores de los operando. Puede tener operando en registros y en memoria.

![](https://github.com/Rafa1104/Informe/blob/master/img/o%202%20XCHG.png)

- **XLAT:** Carga en AL el contenido de la dirección apuntada por [BX+AL].

![](https://github.com/Rafa1104/Informe/blob/master/img/o%203%20XLAT.png)

- **LEA:** Carga en un registro especificado la dirección efectiva especificada como en el operando origen:

![](https://github.com/Rafa1104/Informe/blob/master/img/o%204%20LEA.png)

- **LDS y LES:** Carga el contenido de una dirección de memoria de 32 bits de la siguiente manera: la parte baja en el registro especificado y la parte alta en el registro DS y ES respectivamente.

![](https://github.com/Rafa1104/Informe/blob/master/img/o%205%20LDS%20y%20LES.png)

- **PUSH y POP:** Realizan las operaciones de apilado y desapilado en la pila del procesador respectivamente, admiten todos los tipos de direccionamiento (excepto inmediato). Los operandos deben ser siempre de 16 bits.

![](https://github.com/Rafa1104/Informe/blob/master/img/o%206%20PUSH%20y%20POP.png)

- **PUSHF y POPF:** Apila y desapila el registro de estado, respectivamente. 

- **LAHF:** Carga la parte baja del registro de estado en AH. 

- **SAHF:** Carga AH en el la parte baja del registro de estado.


##### 2. Instrucciones aritméticas
Este tipo de instrucciones realizan operaciones aritméticas con los operandos. Y son: ADD, ADC, DAA, AAA, SUB, SBB, DAS, AAS, NEG, MUL, IMUL, AAM, DIV, IDIV, AAD, CBW, CWB, INC, DEC.

- **ADD y ADC:** Realizan la suma y la suma con acarreo (bit CF del registro de estado) de dos operandos, respectivamente, y guardan el resultado en el primero de ellos. Admiten todos los tipos de direccionamiento (excepto que ambos operando estén en memoria).

![](https://github.com/Rafa1104/Informe/blob/master/img/o%207%20ADD%20y%20ADC.png)

- **DAA:** Realizan la corrección BCD empaquetado del resultado de una suma en AL.
El 8086/88 realiza las sumas asumiendo que los operados son ambos valores binarios, de manera que se suman dos valores codificados en BCD empaquetado el resultado puede no ser un valor válido en este formato:

![](https://github.com/Rafa1104/Informe/blob/master/img/o%208%20DAA.png)

- **SUB y SBB:** Realizan la resta y la resta con acarreo, respectivamente, de dos operandos y guardan el resultado en el primero de ellos. Admiten todos los modos de direccionamiento, excepto dos operando en memoria.

![](https://github.com/Rafa1104/Informe/blob/master/img/o%209%20SUB%20y%20BBS.png)

- **DAS:** Realizan la corrección BCD empaquetado del resultado de una resta en AL. Actúan de manera similar a la instrucción de ajuste de la suma 

- **NEG:** Realiza la operación aritmética de negado de un operando y guarda el resultado en el mismo operando. Admite todos los tipos de direccionamiento, excepto inmediato.

![](https://github.com/Rafa1104/Informe/blob/master/img/o%2010%20NEG.png)

- **MUL e IMUL:** Realizan la multiplicación y multiplicación con signo, respectivamente, de contenido de AX y del operando indicado, guardando el resultado en AX, para operaciones de 8 bits y en DX:AX para operaciones de 16 bits. Los formatos son:

![](https://github.com/Rafa1104/Informe/blob/master/img/o%2011%20MUL%20e%20IMUL.png)

- **DIV e IDIV:** Realizan la división y la división con signo, respectivamente. De AX entre el operando para operaciones de 8 bits, guardando el cociente en AL y el resto en AH; y DX:AX entre el operando para operaciones de 16 bits guardando el cociente en AX y el resto en DX.

![](https://github.com/Rafa1104/Informe/blob/master/img/o%2012%20DIV%20e%20IDIV.png)

- **CBW y CWD:** Realizan la extensión del bit de signo de byte a WORD y de WORD a DWORD, actuando sobre AX y DX:AX, respectivamente. Tal y como se muestra en el figura. Tras esta operación el contenido de AH es FFh.
![](https://github.com/Rafa1104/Informe/blob/master/img/o%2013%20CBW%20y%20CWD.png)

- **INC y DEC:** Realizan las operaciones de incremento y decremento, respectivamente, de un operando, guardando el resultado en el mismo operando. Admiten todos los modos de direccionamiento excepto el inmediato.

![](https://github.com/Rafa1104/Informe/blob/master/img/o%2014%20INC%20y%20DEC.png)


##### 3. Instrucciones lógicas
Realizan las operaciones lógicas y son: OR, XOR, AND, NOT, TEST, CMP.

- **OR, XOR y AND:** Realizan las operaciones lógicas “O”, “O exclusiva” e “Y”, respectivamente, de dos operandos, guardando el resultado en el primero de ellos. Estas operaciones son bit a bit. La tabla de verdad de estas funciones es:

![](https://github.com/Rafa1104/Informe/blob/master/img/o%2015%20OR%2C%20XOR%2C%20AND.png)

- **NOT:** Realiza la operación de negado lógico de los bits del operando, guardando el resultado en el mismo operando. Admite todos los modos direccionamiento excepto inmediato.

![](https://github.com/Rafa1104/Informe/blob/master/img/o%2016%20NOT.png)

##### 4. Instrucciones de comparación
Estas instrucciones realizan funciones de comparación no guardando el resultado, pero si afecta al registro de estado (no cambian a los operandos).

- **TEST:** Realiza la operación lógica “Y” de dos operandos, pero NO afecta a ninguno de ellos, SÓLO afecta al registro de estado. Admite todos los tipos de direccionamiento excepto los dos operandos en memoria.

![](https://github.com/Rafa1104/Informe/blob/master/img/o%2017%20TEST.png)

- **CMP:** Realiza la resta de los dos operandos (como la instrucción SUB) pero NO afecta a ninguno de ellos, SÓLO afecta al registro de estado.

![](https://github.com/Rafa1104/Informe/blob/master/img/o%2018%20CMP.png)


##### 5. Instrucciones de desplazamiento y rotaciones
Realizan operaciones de desplazamiento y rotaciones de bits, y son: SAL/SHL, SAR, SHR, ROL, ROR, RCL, RCR. 

- **SAL/SHL:** Realiza desplazamiento a la izquierda del primer operando tantos bits como indique el segundo operando, introduciendo un 0 y guardando el bit que sale en el bit CF del registro de estado.

![](https://github.com/Rafa1104/Informe/blob/master/img/o%2019%20SAL%2C%20SHL.png)

- **SAR:** Realiza el desplazamiento a la derecha del operando, repitiendo el bit de signo y guardando el resultado en el bit CF del registro de estado.

![](https://github.com/Rafa1104/Informe/blob/master/img/o%2020%20SAR.png)

- **SHR:** Realiza el desplazamiento a la derecha del operando, introduciendo un 0 y guardando el resultado en el bit CF del registro de estado.

![](https://github.com/Rafa1104/Informe/blob/master/img/o%2021%20SHR.png)

- **RCL:** Realiza la rotación a la izquierda de los bits del operando a través del bit CF (acarreo) del registro de estado.

![](https://github.com/Rafa1104/Informe/blob/master/img/o%2022%20RCL.png)

- **RCR:** Realiza la rotación a la derecha de los bits de operando a través del bit CF del registro de estado.

![](https://github.com/Rafa1104/Informe/blob/master/img/o%2023%20RCR.png)

- **ROL:** Realiza la rotación a la izquierda de los bits del operando, ignorando el bit CF del registro de estado, aunque en CF se almacena el bit que se rota.

![](https://github.com/Rafa1104/Informe/blob/master/img/o%2024%20ROL.png)

- **ROR:** Realiza la rotación a la derecha de los bits del operando, ignorando el bit CF del registro de estado, aunque en CF se almacena el bit que se rota.

![](https://github.com/Rafa1104/Informe/blob/master/img/o%2025%20ROR.png)


##### 6. Instrucciones de E/S

##### 7. Instrucciones de control del programa

##### 8. Instrucciones de llamada a procedimiento CALL y RET

##### 9. Instrucciones de cadena de caracteres 

### 5. DIAGRAMAS
- **Diagrama Esquemático**

**Arquitectura 8086**

![](https://github.com/Rafa1104/Informe/blob/master/img/Arquitectura%208086.png)
![](https://github.com/Rafa1104/Informe/blob/master/img/8086.PNG)

### 6. LISTA DE COMPONENTES
| **COMPONENTE** | **DESCRIPCIÓN** |
| :---: | :---: |
| Computadora | Sistema Operativo *Windows 10* |
| Internet | Descarga de ***EMU8086*** |

### 7. MAPA DE VARIABLES


### 8.EXPLICACIÓN DEL CODIGO FUENTE


### 9. DESCRIPCIÓN DE PREREQUISITOS Y CONFIGURACIÓN
Para la simulación del microprocesador 8086, se utilizó el **EMU808** el cual es scompatible para los sistemas operativos de *Windows XP/Vista/7/8/10* y tener un programa que descomprima archivos .rar para poder realizar la instalación del software, para lo cual se siguen los siguientes pasos.

##### 1. Se busca en el navegador ***EMU8086***
![](https://github.com/Rafa1104/Informe/blob/master/img/instalacion%201.png)

#####  2. Ingresamos [EMU8086 Microprocessor Emulator ](https://download.cnet.com/Emu8086-Microprocessor-Emulator/3000-2069_4-10392690.html)
![](https://github.com/Rafa1104/Informe/blob/master/img/instalacion%202.png)

#### 3. Hacemos click en la Opcion de *Download now* para realizar la descarga del archivo .rar
![](https://github.com/Rafa1104/Informe/blob/master/img/instalacion%203.png)

#### 4. Una vez descragado el archivo descomprimimos la carpeta
![](https://github.com/Rafa1104/Informe/blob/master/img/instalacion%204.png)

#### 5. Ejecutamos el archivo *setup.exe*
![](https://github.com/Rafa1104/Informe/blob/master/img/instalacion%205.png)

#### 6. Al ejecutar el instalador debemos de poner *next* para siguiente y asi completar la instalación
![](https://github.com/Rafa1104/Informe/blob/master/img/instalacion%206.png)

#### 7. Para finalizar la instalación hacemos click en el boton de ***Install***
![](https://github.com/Rafa1104/Informe/blob/master/img/instalacion%207.png)

#### 8. Cuando se termina la instalación podemos interactuar con el emulador 
![](https://github.com/Rafa1104/Informe/blob/master/img/instalacion%208.png)


### 10. APORTACIONES


### 11. CONCLUSIONES
El EMU8086 permite la oportunidad de simular programas capaces de ser ejecutados por el microprocesador 8086 diseñado por Intel. El software posee una interfaz gráfica que permite observar los registros, la pila de memoria, entre otros. Esto es una ayuda en el caso de tener errores en la ejecución del programa, ya que se puede observar el comportamiento interno y permite encontrar los errores de código.


### 12. RECOMENDACIONES


### 13. CRONOGRAMA


### 14. BIBLIOGRAFIA
