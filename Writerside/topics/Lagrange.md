# Ejercicio 04: Interpolación de Lagrange
Para resolver el problema de la interpolación de Lagrange, utilizamos la fórmula general de interpolación de Lagrange. Dado que se nos proporcionan los puntos:

$$
(1, 1), (2, 4), (3, 9)
$$

La fórmula de interpolación de Lagrange es la siguiente:

$$
P(x) = \sum_{i=0}^{n} y_i \prod_{j \neq i} \frac{x - x_j}{x_i - x_j}
$$

Donde $( y_i )$ son los valores de la función en los puntos $( x_i )$.

### Paso 1: Definir los puntos

Los puntos dados son:

- $( x_0 = 1 $), $( y_0 = 1 $)
- $( x_1 = 2 $), $( y_1 = 4 $)
- $( x_2 = 3 $), $( y_2 = 9 $)

### Paso 2: Calcular los términos de Lagrange

Para cada punto, necesitamos calcular los polinomios $( L_i(x) )$.

#### $( L_0(x) )$:

$$
L_0(x) = \prod_{j \neq 0} \frac{x - x_j}{x_0 - x_j} = \frac{x - x_1}{x_0 - x_1} \cdot \frac{x - x_2}{x_0 - x_2}
$$

Sustituyendo los valores:

$$
L_0(x) = \frac{x - 2}{1 - 2} \cdot \frac{x - 3}{1 - 3} = \frac{x - 2}{-1} \cdot \frac{x - 3}{-2}
$$

Simplificando:

$$
L_0(x) = \frac{(x - 2)(x - 3)}{2}
$$

#### $( L_1(x) )$:

$$
L_1(x) = \prod_{j \neq 1} \frac{x - x_j}{x_1 - x_j} = \frac{x - x_0}{x_1 - x_0} \cdot \frac{x - x_2}{x_1 - x_2}
$$

Sustituyendo los valores:

$$
L_1(x) = \frac{x - 1}{2 - 1} \cdot \frac{x - 3}{2 - 3} = (x - 1) \cdot \frac{x - 3}{-1}
$$

Simplificando:

$$
L_1(x) = -(x - 1)(x - 3)
$$

#### $( L_2(x) )$:

$$
L_2(x) = \prod_{j \neq 2} \frac{x - x_j}{x_2 - x_j} = \frac{x - x_0}{x_2 - x_0} \cdot \frac{x - x_1}{x_2 - x_1}
$$

Sustituyendo los valores:

$$
L_2(x) = \frac{x - 1}{3 - 1} \cdot \frac{x - 2}{3 - 2} = \frac{x - 1}{2} \cdot (x - 2)
$$

Simplificando:

$$
L_2(x) = \frac{(x - 1)(x - 2)}{2}
$$

### Paso 3: Calcular el polinomio de Lagrange

El polinomio de interpolación de Lagrange es la suma ponderada de estos términos:

$$
P(x) = y_0 L_0(x) + y_1 L_1(x) + y_2 L_2(x)
$$

Sustituyendo los valores de $( y_0 = 1 )$, $( y_1 = 4 )$, $( y_2 = 9 )$:

$$
P(x) = 1 \cdot \frac{(x - 2)(x - 3)}{2} + 4 \cdot -(x - 1)(x - 3) + 9 \cdot \frac{(x - 1)(x - 2)}{2}
$$

### Paso 4: Simplificar el polinomio

Ahora, simplificamos cada término.

1. El primer término es:

   $$
   \frac{(x - 2)(x - 3)}{2} = \frac{x^2 - 5x + 6}{2}
   $$

2. El segundo término es:

   $$
   -4(x - 1)(x - 3) = -4(x^2 - 4x + 3) = -4x^2 + 16x - 12
   $$

3. El tercer término es:

   $$
   9 \cdot \frac{(x - 1)(x - 2)}{2} = 9 \cdot \frac{x^2 - 3x + 2}{2} = \frac{9x^2 - 27x + 18}{2}
   $$

Finalmente, sumamos los tres términos:

$$
P(x) = \frac{x^2 - 5x + 6}{2} - 4x^2 + 16x - 12 + \frac{9x^2 - 27x + 18}{2}
$$

Combinando términos semejantes:

$$
P(x) = \frac{x^2 - 5x + 6 + 9x^2 - 27x + 18}{2} - 4x^2 + 16x - 12
$$

$$
P(x) = \frac{10x^2 - 32x + 24}{2} - 4x^2 + 16x - 12
$$

Simplificando aún más:

$$
P(x) = 5x^2 - 16x + 12 - 4x^2 + 16x - 12
$$

$$
P(x) = x^2
$$

### Resultado Final

El polinomio de interpolación de Lagrange es:

$$
P(x) = x^2
$$