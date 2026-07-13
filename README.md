# Algoritmo-p1
Algoritmo para revisar inventario y controlar stock de productos.

## 1. Descripción del caso
El algoritmo tiene como finalidad ayudar a una tienda en línea a revisar el estado de su inventario. Para realizar el proceso, el algoritmo lee el stock (en unidades) de N productos y verifica que los valores ingresados sean correctos, es decir, que sean mayores o iguales a cero. Luego realiza el cálculo del total de unidades disponibles y revisa si existen productos sin stock. Como resultado, muestra la cantidad total de unidades disponibles y las posiciones del arreglo donde se encuentran los productos con stock igual a cero.

## Pseudocódigo completo
ALGORITMO Control_Stock_Productos
    N, i : ENTERO
    stock : ARREGLO[N] DE ENTERO
    totalStock : ENTERO
    posicionAgotado : ENTERO

INICIO

    ESCRIBIR "Ingrese la cantidad de productos:"
    LEER N

    totalStock ← 0
    posicionAgotado ← -1

    PARA i ← 1 HASTA N HACER

        ESCRIBIR "Ingrese el stock del producto ", i
        LEER stock[i]

        MIENTRAS stock[i] < 0 HACER
            ESCRIBIR "El valor debe ser mayor o igual a cero"
            LEER stock[i]
        FIN_MIENTRAS

    FIN_PARA


    PARA i ← 1 HASTA N HACER

        totalStock ← totalStock + stock[i]

        SI stock[i] = 0 ENTONCES
            posicionAgotado ← i
        FIN_SI

    FIN_PARA


    ESCRIBIR "Total de unidades disponibles: ", totalStock

    SI posicionAgotado <> -1 ENTONCES
        ESCRIBIR "Producto sin stock encontrado en la posición: ", posicionAgotado
    SINO
        ESCRIBIR "No existen productos con stock igual a cero"
    FIN_SI

FIN

## 3. Diagrama de flujo
![Diagrama de flujo](diagrama_flujo.png)

## 4. Tabla de trazado
Datos de prueba utilizados:

| Producto | Stock 
|---|--- |
| 1 | 25 |
| 2 | 0  |
| 3 | 10 |
| 4 | 0  |
| 5 | 40 |

| Iteración (i) | stock[i] | totalStock antes | ¿stock[i] = 0? | posicionAgotado | totalStock después |
|---|--- |--- |--- |--- |--- | 
| 1 | 25 | 0  | No | -1 | 25 |
| 2 | 0  | 25 | Sí | 2  | 25 |
| 3 | 10 | 25 | No | 2  | 35 |
| 4 | 0  | 35 | Sí | 4  | 35 |
| 5 | 40 | 35 | No | 4  | 75 |

Resultado final:

- Total de unidades disponibles: 75
- Posición del producto sin stock encontrado: 4
