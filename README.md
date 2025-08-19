# **Proyecto de ETL: Limpieza y Análisis Inicial de Churn - Challenge Alura ONE (Parte 1)**

¡Bienvenido a la primera fase de mi proyecto de Data Science para Telecom X! Este repositorio documenta el proceso fundamental de **ETL (Extracción, Transformación y Carga)**, donde convertí datos crudos y complejos en un dataset limpio y listo para el análisis.

- **Autor:** Gonzalo Malca Garcia
- **Programa:** Oracle Next Education (ONE) + Alura Latam
- **Tecnologías Clave:** Python, Pandas, Seaborn, Google Colab

---

### **🎯 El Reto: Poniendo Orden en el Caos**

La empresa **Telecom X** me encomendó una misión crucial: investigar por qué estaban perdiendo tantos clientes. Sin embargo, antes de poder responder a esa pregunta, me enfrenté a un desafío común en el mundo real: los datos no estaban listos.

Mi objetivo en esta primera etapa fue:
1.  **Conectarme** a la fuente de datos original (una API JSON).
2.  **Limpiar, estructurar y validar** la información.
3.  **Realizar un primer análisis exploratorio** para obtener los primeros insights.
4.  **Generar un dataset de alta calidad** que sirviera como base para futuros modelos predictivos.

---

### **🛠️ Mi Metodología: Un Pipeline de ETL Detallado**

Para asegurar la integridad de los datos, implementé un pipeline de ETL paso a paso:

1.  **Extracción (`Extract`):**
    *   Me conecté a una API para obtener los datos de los clientes en formato **JSON**, que venían en una estructura anidada.

2.  **Transformación (`Transform`):**
    *   **Aplanado de Datos:** Utilicé la función `pd.json_normalize()` para convertir la compleja estructura JSON en una tabla plana y manejable de 21 columnas.
    *   **Diagnóstico de Calidad:** Usé `.info()` y `.isnull().sum()` para realizar un chequeo completo, descubriendo un tipo de dato incorrecto en la columna de cargos totales.
    *   **Limpieza de Datos Numéricos:** Convertí la columna `account.Charges.Total` a formato numérico y eliminé 11 filas que contenían valores no válidos.
    *   **Limpieza de Datos Categóricos:** Identifiqué y eliminé 24 registros que tenían un valor inconsistente ("fantasma") en la columna `Churn` mediante el uso de `.str.strip()`.
    *   **Enriquecimiento de Datos:** Creé una nueva columna, `customer.Charges.Daily`, para obtener una visión más granular del gasto de los clientes.

3.  **Carga (`Load`):**
    *   El resultado final del pipeline es el archivo **`telecom_x_datos_limpios.csv`**, un dataset con **7,032 registros de clientes y 22 columnas**, completamente limpio y listo para el análisis.

---

### **🔎 Primeros Hallazgos: Las Pistas Iniciales**

El análisis exploratorio sobre el dataset limpio reveló una **tasa de Churn del 26.58%** y nos dio las primeras pistas sobre los perfiles de riesgo:
*   **Servicio de Internet:** El plan de **Fibra Óptica** muestra una tasa de cancelación alarmantemente alta.
*   **Antigüedad:** Los **clientes nuevos** son los más propensos a cancelar.
*   **Servicios Adicionales:** La falta de **Soporte Técnico y Seguridad Online** está fuertemente correlacionada con el Churn.

---


### **💻 Archivos en este Repositorio**

1.  **`Solucion_Challenge_ETL_GMG.ipynb`:** El notebook de Google Colab con todo el código del proceso ETL y el análisis.


---

### **👨‍💻 Desarrollado por**

**Gonzalo Malca Garcia**

