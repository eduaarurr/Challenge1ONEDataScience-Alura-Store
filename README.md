# Análisis de Rendimiento de Tiendas Online - Sr Juan

Este proyecto analiza el desempeño de cuatro tiendas online de la empresa Sr Juan para identificar cuál presenta el peor rendimiento y debería ser cerrada.

---

## Contenido

1. **Importación y Preparación de Datos**  
   Se cargan datos de ventas, productos, calificaciones y ubicaciones de cuatro tiendas desde fuentes externas (CSV en GitHub).

2. **Análisis de Facturación**  
   Cálculo y visualización de ingresos totales por tienda.

3. **Ventas por Categoría**  
   Distribución de ventas segmentada por categorías de productos para cada tienda.

4. **Calificación Promedio**  
   Evaluación de satisfacción del cliente a través de las calificaciones promedio por tienda.

5. **Productos Más y Menos Vendidos**  
   Identificación y visualización de los productos con mayor y menor volumen de ventas.

6. **Costo Promedio de Envío**  
   Cálculo y comparación del costo promedio de envío por tienda.

7. **Análisis Geográfico**  
   Visualización de ubicaciones y densidad de ventas con mapas de calor usando `folium`.

8. **Resumen y Recomendaciones**  
   Tabla resumen con indicadores clave y recomendación final basada en análisis multidimensional.

---

## Tecnologías y Librerías

- Python 3.x  
- Pandas  
- Matplotlib  
- Folium  
- Jupyter Notebook / Google Colab

---

## Instalación

Clona este repositorio y asegúrate de instalar las dependencias:

```bash
pip install pandas matplotlib folium
```
Uso
1)Abre el notebook en Jupyter o Google Colab.

2)Ejecuta las celdas en orden para cargar datos, analizar y visualizar resultados.

3)Consulta la tabla resumen y la recomendación para tomar decisiones.

Código principal
```bash
python
Copiar
Editar
import pandas as pd
import matplotlib.pyplot as plt
import matplotlib as mpl
import folium
from folium.plugins import HeatMap

urls = [
    "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_1%20.csv",
    "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_2.csv",
    "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_3.csv",
    "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_4.csv"
]

tiendas = [pd.read_csv(url) for url in urls]
nombres = ['Tienda1', 'Tienda2', 'Tienda3', 'Tienda4']

for df, nombre in zip(tiendas, nombres):
    df['Tienda'] = nombre

df_tiendas = pd.concat(tiendas, ignore_index=True)
```
# ... resto del análisis y visualización ...
| Aspecto                   | Tienda 1                                        | Tienda 2                                    | Tienda 3                             | Tienda 4                        |
| ------------------------- | ----------------------------------------------- | ------------------------------------------- | ------------------------------------ | ------------------------------- |
| **Ingresos Totales**      | \$1.150.880.400 (más alto)                      | \$1.116.343.500                             | \$1.098.019.600                      | \$1.038.375.700 (más bajo)      |
| **Ventas Principales**    | Muebles, Electrónicos                           | Muebles, Electrónicos, Instrumentos, Libros | Muebles, Electrónicos                | Muebles, Electrónicos, Juguetes |
| **Calificación Promedio** | 3.98 (más baja)                                 | 4.04                                        | 4.05 (más alta)                      | 4.00                            |
| **Costo Promedio Envío**  | \$26.019 (más alto)                             | \$25.216                                    | \$24.806                             | \$23.459 (más bajo)             |
| **Rendimiento General**   | Alta facturación, baja satisfacción, costo alto | Equilibrada en ventas y satisfacción        | Mejor calificación y buen equilibrio | Peor rendimiento general        |

Recomendación final
Se recomienda eliminar la Tienda 4 debido a su bajo rendimiento en ingresos, calificación y ventas, a pesar de tener costos de envío más bajos. Optimizar el negocio enfocándose en las otras tiendas permitirá mejorar la rentabilidad y eficiencia general.

Autor
Sr Eduaro Urrutia - Data Science       
