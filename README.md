# RETO 7
## 1.
Imprimir un listado con los números del 1 al 100 cada uno con su respectivo cuadrado

```
for i in range(1, 101):
    print(f"{i} -> {i**2}")

```

## 2.
Imprimir un listado con los números impares desde 1 hasta 999 y seguidamente otro listado con los números pares desde 2 hasta 1000
```
print("Impares del 1 al 999:")
for i in range(1, 1000, 2):
    print(i, end=", ")

print("\n\nPares del 2 al 1000:")
for i in range(2, 1001, 2):
    print(i, end=", ")

```

## 3.
Imprimir los números pares en forma descendente hasta 2 que son menores o iguales a un número natural n ≥ 2 dado
```
n = int(input("Ingrese un número natural n (n ≥ 2): "))
print(f"Pares desde {n} hasta 2:")
for i in range(n, 1, -1):
    if i % 2 == 0:
        print(i, end=", ")

```

## 4.
Imprimir los números de 1 hasta un número natural n dado, cada uno con su respectivo factorial
```
n = int(input("Ingrese un número natural: "))

for i in range(1, n + 1):
    factorial = 1
    for j in range(1, i + 1):
        factorial *= j
    print(f"{i}! = {factorial}")

```
## 5.
Calcular el valor de 2 elevado a la potencia n usando ciclos *for*.
```
n = int(input("Ingrese el valor de n: "))
resultado = 1

for i in range(n):
    resultado *= 2

print(f"2 elevado a la {n} es {resultado}")

```
## 6.
Leer un número natural n, leer otro dato de tipo real x y calcular x^n usando ciclos for. **Disclaimer:** Trate de no utilizar el operador de potencia (**).
```
x = float(input("Ingrese el valor de x: "))
n = int(input("Ingrese el valor de n: "))

resultado = 1
for i in range(n):
    resultado *= x

print(f"{x} elevado a la {n} es {resultado}")

```
## 7.
Diseñe un programa que muestre las tablas de multiplicar del 1 al 9.
```
for i in range(1, 10):
    print(f"Tabla del {i}")
    for j in range(1, 11):
        print(f"{i} x {j} = {i * j}")
    print("-" * 15)

```
## 8.
Diseñar una función que permita calcular una aproximación de la función exponencial alrededor de 0 para cualquier valor x (real), utilizando los primeros n términos de la serie de Taylor. **Nota:** use *math* para traer la función exponencial y mostrar la diferencia entre el valor real y la aproximación.
$$e^x \approx exp(x,n) \approx \sum_{i=0}^{n}\frac{x^i}{i!}$$
```
import math

def exp_aprox(x, n):
    suma = 0
    for i in range(n + 1):
        # Calcular x^i / i!
        pot = 1
        for j in range(i):
            pot *= x
        fact = 1
        for j in range(1, i + 1):
            fact *= j
        suma += pot / fact
    return suma

x = float(input("Ingrese el valor de x: "))
n = int(input("Ingrese el número de términos: "))

aprox = exp_aprox(x, n)
real = math.exp(x)

print(f"exp_aprox({x}) = {aprox}")
print(f"exp_real({x}) = {real}")
print(f"Diferencia = {abs(real - aprox)}")

```
## 9.
Diseñar una función que permita calcular una aproximación de la función seno alrededor de 0 para cualquier valor x (real), utilizando los primeros n términos de la serie de Maclaurin. **Nota:** use *math* para traer la función seno y mostrar la diferencia entre el valor real y la aproximación.
$$sin(x) \approx sin(x,n) \approx \sum_{i=0}^{n} (-1)^i \frac{x^{2i+1}}{(2i+1)!}$$
```
import math

def sin_aprox(x, n):
    suma = 0
    for i in range(n + 1):
        signo = (-1) ** i
        pot = 1
        for j in range(2*i + 1):
            pot *= x
        fact = 1
        for j in range(1, 2*i + 2):
            fact *= j
        suma += signo * (pot / fact)
    return suma

x = float(input("Ingrese el valor de x (en radianes): "))
n = int(input("Ingrese el número de términos: "))

aprox = sin_aprox(x, n)
real = math.sin(x)

print(f"sin_aprox({x}) = {aprox}")
print(f"sin_real({x}) = {real}")
print(f"Diferencia = {abs(real - aprox)}")

```
Eso es todo, gracias.
