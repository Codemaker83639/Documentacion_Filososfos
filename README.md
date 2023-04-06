# Documentacion_Filososfos

### Francisco Ogando (2021-0160)
[Link a mi explicación]()

***Esta es mi documentación acerca del código en python que utilicé para la resolución del problema de los filósofos, este código implementa una simulación de los filósofos comensales, utilizando hilos y candados en Python. En la simulación, cada filósofo es representado por un hilo, y cada palillo es representado por un candado. Los filósofos intentan tomar los palillos adyacentes para comer, y si no pueden hacerlo, esperan un tiempo aleatorio y vuelven a intentar. Si un filósofo no puede tomar los palillos después de un número determinado de intentos, muere de inanición. Además, los filósofos alternan entre comer y filosofar. El usuario puede establecer los parámetros de la simulación a través de argumentos de línea de comandos.***

***Además una variación importante es, que Para los fines de la práctica se agrega la condición de que si un filósofo ha intentado 10 veces obtener un palillo y no ha podido entonces este muere de*** 
**inanición.**

***La solución consiste en tener un arreglo de RLock, que representarán los palillos y la estrategia consiste en tomar el palillo de la izquierda, y revisar si está disponible el de la derecha, si este es el caso, entonces se toma el de la derecha y se empieza a comer.***

**El código principal para esta lógica es el siguiente:**
<p>  
palillo_izq.acquire()
<p/> 
<p> 
if palillo_der.acquire(blocking=False):
    return True
<p/>
<p>  
else:
    palillo_izq.release()
    return False
<p/> 