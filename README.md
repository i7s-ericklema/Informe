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
#### Estructura Interna

##### **Unidad de interfaz del bus y unidad de ejecución**
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
Para la simulación del microprocesador 8086, se utilizó el **EMU808** el cual es scompatible para los sistemas operativos de *Windows XP/Vista/7/8/10* y tener un programa que descomprima archivos .rar para poder realizar la instalación del software.


### 10. APORTACIONES


### 11. CONCLUSIONES
El EMU8086 permite la oportunidad de simular programas capaces de ser ejecutados por el microprocesador 8086 diseñado por Intel. El software posee una interfaz gráfica que permite observar los registros, la pila de memoria, entre otros. Esto es una ayuda en el caso de tener errores en la ejecución del programa, ya que se puede observar el comportamiento interno y permite encontrar los errores de código.


### 12. RECOMENDACIONES


### 13. CRONOGRAMA


### 14. BIBLIOGRAFIA
