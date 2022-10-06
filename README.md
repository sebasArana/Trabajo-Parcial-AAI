# (VRP) Vehicle Routing with Pickups and Deliveries

## 1. Descripción del problema a resolver.

![image](https://user-images.githubusercontent.com/64936813/194430918-7c13a48a-54c0-46ca-a8a2-6424ad261431.png)

Hay M paquetes distribuidos en diferentes puntos de recojo y cada uno debe ser llevado a su respectivo punto de entrega. Se tienen N vehículos en un punto específico que deben realizar dicha tarea y regresar al punto inicial. Se requiere que en conjunto los N vehículos realicen el delivery de los M paquetes de modo que la suma de las distancias o el tiempo de los recorridos sea el menor posible.

## 2. Motivación para resolver el problema. 

La industria del transporte de carga ha crecido enormemente en la última década. Los líderes de la industria operan redes de miles de vehículos terrestres y bodegas, en los cuáles sus procesos de reparto utilizan mucho tiempo para poder completarlos. Por lo tanto, es realmente necesario optimizar los procesos de reparto, y así aprovechar al máximo los envíos en un determinado tiempo.


## 3. Planteamiento y ejemplos del espacio de solución.

El espacio de solución se comprende de todas las posibles rutas y se encontrará la ruta más óptima que puede tomar los N vehículos a los 2*M puntos (M puntos de recojo y M puntos de entrega). Se describe como: {*P0* M_2 M_4 M_1 … P0 M_15 M_12 … P0 }, donde P0 es el punto de inicio para cada vehículo y aparece N + 1 veces en la lista.
 
Ejemplos:

{0 3 6 7 10 4 1 0 2 5 9 8 0}
{0 8 9 6 3 0 7 10 4 1 2 5 0}
{0 1 2 3 4 5 6 7 8 9 10 0 0}

## 4. Planteamiento y ejemplos del espacio de búsqueda.

El espacio de búsqueda es el espacio de solución sin considerar las rutas no válidas. La ruta no es válida si al terminar el recorrido el vehículo que ha corregido el paquete no pasa por el punto de entrega.

{ …0 3 6 0… } pertenece al espacio de solución pero **no pertenece al espacio de búsqueda** ya que el paquete que se recoge en el punto 6 no se entrega al punto 3 en el recorrido que realiza el vehículo.

![image](https://user-images.githubusercontent.com/64936813/194431026-fb68cd76-f4cb-4793-9643-07b4a5dd48b8.png)

Ejemplos:

{0 6 3 7 10 4 1 0 2 5 9 8 0}
{0 6 9 8 3 0 7 10 4 1 2 5 0}

## 5. Implementación de representación usando un lenguaje de programación

Representación de: [0, 6, 3, 7, 10, 4, 1, 0, 2, 5, 9, 8, 0]

![image](https://user-images.githubusercontent.com/64936813/194431094-80005ef6-cad0-4561-b0ea-c273917ba566.png)
