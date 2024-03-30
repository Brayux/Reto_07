# Reto_07
1. Imprimir un listado con los números del 1 al 100 cada uno con su respectivo cuadrado.

python
i = 1  
while i <= 100:  
    print(i, i ** 2)
    i += 1

mermaid
flowchart TD
    A[Inicio] --> B[Inicialización: i = 1]
    B --> C{¿i <= 100?}
    C -- Sí --> D[Calcula cuadrado: cuadrado = i ** 2]
    D --> E[Imprime 'El cuadrado de i es cuadrado']
    E --> F[Incrementa i: i += 1]
    F --> C
    C -- No --> G[Fin]

2. Imprimir un listado con los números impares desde 1 hasta 999 y seguidamente otro listado con los números pares desde 2 hasta 1000.

python
x=1
while x <= 1000:
    if x % 2 == 0:
        print("El número ",x," es par")
    if x % 2 == 1:
        print("El número ",x," es impar")
    x += 1
print("Ciclo terminado")

mermaid
flowchart TD;
    A(Inicio) --> B[Determinar si un número es par o impar en la
    siguiente lista comprendida...]; 
    B --> C; C[X <= 1000]--> E; E{X % 2 == 0} -- Sí --> 
    F[X es par]; E -- No --> G[X = X+1]; 
    G --> C
    F --> H; H(Fin)

3. Imprimir los números pares en forma descendente hasta 2 que son menores o iguales a un número natural n ≥ 2 dado

python
n=int(input("Digite numero desde el cual descenderan los numeros primos siempre y cuando sea mayor o igual que 2: "))  
i = n
while i >= 2:
    i -= 1
    if i % 2 == 0:
       print(i)

mermaid
graph TD;
    A(Digite número n) --> B{Verificar n ≥ 2}
    B -- No --> C[Imprimir: n no cumple condición]
    B -- Sí --> D{Verificar n es par}
    D -- No --> E[Acercar n a par más cercano]
    E --> F[Iniciar ciclo]
    D -- Sí --> F
    F --> G[Imprimir n]
    G --> H{Disminuir n en 2}
    H --> I{n < 2}
    I -- Sí --> J[Fin]
    I -- No --> G

4. En 2022 el país A tendrá una población de 25 millones de habitantes y el país B de 18.9 millones. Las tasas de crecimiento anual de la población serán de 2% y 3% respectivamente. Desarrollar un algoritmo para informar en que año la población del país B superará a la de A.

python
B = 18900000  
A = 25000000
tasa_A = 0.02  # 2%
tasa_B = 0.03  # 3%
año=int(input("Ingrese un año: "))
while B <= A:
    A *= (1 + tasa_A)
    B *= (1 + tasa_B)
    año += 1

print("La población del país B superará a la del país A en el año:", año)

5. Imprimir el factorial de un número natural n dado.

python
x = int(input("Digite un número natural: "))
if x >=0:
    a = 1
    b = 1
    while a <= x:
        b = b * a
        a += 1
        print ("El factorial de ",x," es: ",b)
else:
    print("Digtaste un número fuera de los parámetros")

6. Implementar un algoritmo que permita adivinar un número dado de 1 a 100, preguntando en cada caso si el número es mayor, menor o igual.

python
import random

cualquierNumero = random.randrange (1,100)

def intro():
    print("Adivina el Número")

def juego():
    intentos = 0
    while True:
        numeroDigitado = int(input("Digite un número entre el 1 y el 100"))
        if numeroDigitado > cualquierNumero:
            intentos += 1
            print("Creo que el numero es más pequeño")
        elif numeroDigitado < cualquierNumero:
            intentos += 1
            print("Tal vez el número sea mas grande")
        else:
            intentos +=1
            print(f"Enhorabuena, tu número es ",cualquierNumero )
            break

7. Implementar un programa que ingrese un número de 2 a 50 y muestre sus divisores.

python
i = int(input("Digite un número entre 2 y 50: "))

if i < 2 or i > 50:
    print("El número digitado es inválido")
else:
    print(f"Divisores de {i}:")
    for n in range(1, i + 1):
        if i % n == 0:
            print(n)

8. Implementar el algoritmo que muestre los números primos del 1 al 100. Nota: use funciones

python
def es_primo(i):
    if i < 2:
        return False
    for n in range(2, int(i**0.5) + 1):
        if i % n == 0:
            return False
    return True

i = 1
while i <= 100:
    if es_primo(i):
        print(i)
    i += 1
