# Análisis de Rendimiento de Tiendas - Proyecto de Ventas

Este proyecto tiene como objetivo analizar y visualizar el rendimiento de varias tiendas a partir de datos de ventas. Se trabaja con datos que incluyen información de productos vendidos, ubicación geográfica, calificaciones, métodos de pago y más.

## Estructura del Proyecto

El análisis se divide en varias etapas, utilizando `Python`, `Pandas` y `Matplotlib`.

### 1. Preparación de Datos

Se trabajó con un dataset que contiene los siguientes campos principales:

- Producto, Categoría del producto
- Precio, Costo de envío
- Fecha de compra
- Vendedor, Lugar de compra
- Calificación, Método de pago
- Latitud (`lat`) y Longitud (`lon`)

Cada tienda tiene su propio DataFrame, y se los organizó como una lista de tuplas para facilitar la modularización:

```python
lista_tiendas = [
    ('Tienda N°1', tienda),
    ('Tienda N°2', tienda2),
    ('Tienda N°3', tienda3),
    ('Tienda N°4', tienda4)
]
```

### 2. Análisis de Costo de Envío Promedio

Se creó una función para calcular el costo promedio de envío por tienda:

```python
def calcular_envio_promedio_tienda(lista_tiendas):
    costos_envio_promedio = {}
    for nombre_tienda, df in lista_tiendas:
        costos_envio_promedio[nombre_tienda] = df['Costo de envío'].mean()
    return costos_envio_promedio
```

También se identificaron las tiendas con el costo de envío promedio más bajo y más alto.

### 3. Visualización de Costos Promedio

Se generó un gráfico de barras con `Matplotlib` para visualizar los costos de envío promedio por tienda. Además, se destacaron con colores diferentes el menor y mayor promedio:

```python
colors = ['green' if tienda == tienda_mas_barata else 'red' if tienda == tienda_mas_cara else 'gray' for tienda in tiendas]
```

### 4. Análisis Geográfico

Se utilizó la latitud y longitud de las ventas para realizar un gráfico de dispersión geográfica de las ventas por tienda:

```python
plt.scatter(longitudes, latitudes, c=facturaciones, cmap='viridis', alpha=0.7)
```

Cada punto representa una venta, y su color depende del total facturado. Esta visualización permite observar patrones regionales y áreas con mayor volumen de ventas.

---

## Herramientas Utilizadas

- Python
- Pandas
- Matplotlib

---


## Autor

Proyecto desarrollado por Joaquín Peralta Corbellini como parte del Challenge de AluraLatam
