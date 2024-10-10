# 16ejercicios

#1- Contar Ocurrencias de Elementos
#Colección: Lista
#Descripción: Dada una lista de palabras, crea una función que devuelva un diccionario con la cantidad de veces que aparece cada palabra.

#Ejemplo:
#palabras = ["python", "java", "python", "c++"]
# Salida: {"python": 2, "java": 1, "c++": 1}


def contar_ocurrencias(palabras):
    ocurrencias = {}
    for palabra in palabras:
        if palabra in ocurrencias:
            ocurrencias[palabra] += 1
        else:
            ocurrencias[palabra] = 1
    return ocurrencias


palabras = ["python", "java", "python", "c++"]
resultado = contar_ocurrencias(palabras)
print(resultado)

# RESPUETA {"python": 2, "java": 1, "c++": 1}

#/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

#2- Combinar Diccionarios
#Colección: Diccionario
#Descripción: Escribe una función que combine dos diccionarios, sumando los valores de las claves comunes.
#Ejemplo:

#dic1 = {'a': 1, 'b': 2}
#dic2 = {'b': 3, 'c': 4}
# Salida: {'a': 1, 'b': 5, 'c': 4}


def combinar_diccionarios(dic1, dic2):
    combinado = dic1.copy()
    for clave, valor in dic2.items():
        if clave in combinado:
            combinado[clave] += valor  
        else:
            combinado[clave] = valor
    return combinado  

dic1 = {'a': 1, 'b': 2}
dic2 = {'b': 3, 'c': 4}

resultado = combinar_diccionarios(dic1, dic2)

print(resultado)

#RESPUESTA  {'a': 1, 'b': 5, 'c': 4}


#/////////////////////////////////////////////////////////////////////////////////////////////////

#3- Listas de Frecuencia
#Colección: Lista
#Descripción: Dada una lista de números, devuelve un diccionario con la frecuencia de cada número.
#Ejemplo:

#numeros = [1, 1, 2, 3, 3, 3]
# Salida: {1: 2, 2: 1, 3: 3}

def frecuencia_numeros(numeros):
    frecuencia = {}
    for numero in numeros:
        if numero in frecuencia:
            frecuencia[numero] += 1
        else:
            frecuencia[numero] = 1
    return frecuencia


numeros = [1, 1, 2, 3, 3, 3]
resultado = frecuencia_numeros(numeros)

print(resultado)  
#RESPUESTA  {1: 2, 2: 1, 3: 3}


#//////////////////////////////////////////////////////////////

#4- Filtrar Palabras Largas
#Colección: Lista
#Descripción: Crea una función que reciba una lista de palabras y un número entero, devolviendo una nueva lista con palabras que tienen más de ese número de caracteres.
#Ejemplo:

#Palabras = ["hola", "mundo", "python", "programación"]
#longitud = 5
# Salida: ["programación"]


def filtrar_palabras_largas(palabras, longitud):
    return [palabra for palabra in palabras if len(palabra) > longitud]


palabras = ["hola", "mundo", "python", "programación"]
longitud = 5
resultado = filtrar_palabras_largas(palabras, longitud)
 

print(resultado) 
# RESPUESTA ["programación"]


#/////////////////////////////////////////////////////////////////////

#5- Inversión de Tuplas en Lista
#Colección: Lista de Tuplas
#Descripción: Dada una lista de tuplas, crea una función que devuelva una lista con las tuplas invertidas.
#Ejemplo:

#tuplas = [(1, 2), (3, 4), (5, 6)]
# Salida: [(2, 1), (4, 3), (6, 5)]

def invertir_tuplas(tuplas):
    return [(b, a) for (a, b) in tuplas]


tuplas = [(1, 2), (3, 4), (5, 6)]
resultado = invertir_tuplas(tuplas)

print(resultado)  
# RESPUESTA [(2, 1), (4, 3), (6, 5)]


#//////////////////////////////////////////////////////////////////////////////////////////////////////////
#6- Encontrar el Valor Más Frecuente
#Colección: Lista
#Descripción: Dada una lista de números, crea una función que encuentre y devuelva el número que aparece con mayor frecuencia.
#Ejemplo:

#numeros = [1, 2, 3, 1, 2, 1]
# Salida: 1

from collections import Counter

def valor_mas_frecuente(numeros):
    if not numeros:
        return None 
    contador = Counter(numeros)
    return contador.most_common(1)[0][0]


numeros = [1, 2, 3, 1, 2, 1]
resultado = valor_mas_frecuente(numeros)

print(resultado)  
# RESPUESTA 1


#/////////////////////////////////////////////////////////////////////////////////////////////
#7- Comprobar Subconjunto
#Colección: Conjunto
#Descripción: Escribe una función que determine si un conjunto es un subconjunto de otro.
#Ejemplo:

#conjunto1 = {1, 2, 3}
#conjunto2 = {1, 2, 3, 4, 5}
# Salida: True

def es_subconjunto(conjunto1, conjunto2):
    return conjunto1.issubset(conjunto2)


conjunto1 = {1, 2, 3}
conjunto2 = {1, 2, 3, 4, 5}
resultado = es_subconjunto(conjunto1, conjunto2)
print(resultado)  
# RESPUESTA True


#/////////////////////////////////////////////////////////////////////////////////

#8- Agrupación por Clave
#Colección: Lista de Diccionarios
#Descripción: Dada una lista de diccionarios que representan personas (con claves "nombre" y "edad"), agrúpalos por edad.
#Ejemplo:

#personas = [{"nombre": "Ana", "edad": 25}, {"nombre": "Luis", "edad": 25}, {"nombre": "Carlos", "edad": 30}]
# Salida: {25: ['Ana', 'Luis'], 30: ['Carlos']}


def agrupar_por_edad(personas):
    agrupados = {}
    for persona in personas:
        edad = persona['edad']
        nombre = persona['nombre']
        if edad not in agrupados:
            agrupados[edad] = []
        agrupados[edad].append(nombre)
    return agrupados


personas = [{"nombre": "Ana", "edad": 25}, {"nombre": "Luis", "edad": 25}, {"nombre": "Carlos", "edad": 30}]
print(agrupar_por_edad(personas))  

# RESPUESTA  {25: ['Ana', 'Luis'], 30: ['Carlos']}

#////////////////////////////////////////////////////////////////////////////////////////

#9- Merge Sort utilizando Listas
#Colección: Lista
#Descripción: Implementa el algoritmo Merge Sort para ordenar una lista de números.
#Ejemplo:

#numeros = [5, 3, 8, 6, 2]
# Salida: [2, 3, 5, 6, 8]


def merge_sort(numeros):
    if len(numeros) <= 1:
        return numeros
    medio = len(numeros) // 2
    izquierda = merge_sort(numeros[:medio])
    derecha = merge_sort(numeros[medio:])
    return merge(izquierda, derecha)

def merge(izquierda, derecha):
    resultado = []
    i = j = 0
    while i < len(izquierda) and j < len(derecha):
        if izquierda[i] < derecha[j]:
            resultado.append(izquierda[i])
            i += 1
        else:
            resultado.append(derecha[j])
            j += 1
    resultado.extend(izquierda[i:])
    resultado.extend(derecha[j:])
    return resultado


numeros = [5, 3, 8, 6, 2]
print(merge_sort(numeros))  

# RESPUESTAS [2, 3, 5, 6, 8]

#////////////////////////////////////////////////////////////////////////////////////////

#10- Eliminar Elementos por Condición
#Colección: Lista
#Descripción: Crea una función que reciba una lista y elimine todos los elementos que sean menores que un valor dado.
#Ejemplo:

#numeros = [1, 2, 3, 4, 5]
#limite = 3
# Salida: [3, 4, 5]

def eliminar_menores(numeros, limite):
    return [num for num in numeros if num >= limite]


numeros = [1, 2, 3, 4, 5]
limite = 3
print(eliminar_menores(numeros, limite))  
#  RESPUESTA [3, 4, 5]



#///////////////////////////////////////////
#11- Flatten List of Lists
#Colección: Lista de Listas
#Descripción: Dada una lista que contiene otras listas, crea una función que "aplane" la lista, es decir, devuelva una sola lista con todos los elementos.
#Ejemplo:

#lista_de_listas = [[1, 2], [3, 4], [5]]
# Salida: [1, 2, 3, 4, 5]


def aplanar_lista(lista_de_listas):
    return [elemento for sublista in lista_de_listas for elemento in sublista]


lista_de_listas = [[1, 2], [3, 4], [5]]
print(aplanar_lista(lista_de_listas))  

# RESPUESTA  [1, 2, 3, 4, 5]

#///////////////////////////////////////////////////
#12- Cálculo de Mediana
#Colección: Lista
#Descripción: Crea una función que calcule la mediana de una lista de números.
#Ejemplo:

#numeros = [1, 3, 2, 4, 5]
# Salida: 3

def calcular_mediana(numeros):
    numeros.sort()
    n = len(numeros)
    mitad = n // 2
    
    if n % 2 == 0:
        return (numeros[mitad - 1] + numeros[mitad]) / 2
    else:
        return numeros[mitad]


numeros = [1, 3, 2, 4, 5]
print(calcular_mediana(numeros)) 

# RESPUESTA 3


#////////////////////////////////////////////////////////////

#13- Duplicar Elementos en una Lista
#Colección: Lista
#Descripción: Dada una lista de números, crea una función que devuelva una nueva lista donde cada número se duplique.
#Ejemplo:

#numeros = [1, 2, 3]
# Salida: [1, 1, 2, 2, 3, 3]

def duplicar_elementos(lista):
    return [elemento for elemento in lista for _ in range(2)]


numeros = [1, 2, 3]
print(duplicar_elementos(numeros))  

# RESPUESTA [1, 1, 2, 2, 3, 3]



#//////////////////////////////////////////////////

#14-Contar Palabras en Frases
#Colección: Lista
#Descripción: Dada una lista de frases, crea una función que devuelva un diccionario con la cantidad de palabras en cada frase.
#Ejemplo:

#frases = ["Hola mundo", "Python es genial", "Me gusta programar"]
# Salida: {0: 2, 1: 3, 2: 3}


def contar_palabras_en_frases(frases):
    return {i: len(frase.split()) for i, frase in enumerate(frases)}


frases = ["Hola mundo", "Python es genial", "Me gusta programar"]
print(contar_palabras_en_frases(frases)) 

# RESPUESTA {0: 2, 1: 3, 2: 3}


#///////////////////////////////////////////////////////////
#15- Encontrar Clave Máxima en Diccionario
#Colección: Diccionario
#Descripción: Crea una función que encuentre la clave con el valor máximo en un diccionario.
#Ejemplo:

#diccionario = {'a': 10, 'b': 20, 'c': 5}
# Salida: 'b'


def clave_maxima(diccionario):
    return max(diccionario, key=diccionario.get)


diccionario = {'a': 10, 'b': 20, 'c': 5}
print(clave_maxima(diccionario))  

# RESPUESTA b

#///////////////////////////////////////////////////////////

#16- Palíndromos en una Lista
#Colección: Lista
#Descripción: Escribe una función que devuelva una lista de palabras que son palíndromos de una lista dada.
#Ejemplo:

#palabras = ["ana", "oso", "hola", "level"]
# Salida: ["ana", "oso", "level"]


def encontrar_palindromos(palabras):
    return [palabra for palabra in palabras if palabra == palabra[::-1]]

palabras = ["ana", "oso", "hola", "level"]
print(encontrar_palindromos(palabras))


# RESPUESTA  ["ana", "oso", "level"]
