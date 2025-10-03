# Email Scraper Python

Este repositorio contiene **scripts en Python** para realizar búsquedas en Google y extraer posibles correos electrónicos de páginas web.  
El proyecto está pensado **con fines educativos y de referencia**, no para uso en producción ni para envío de spam.  

Este proyecto es estrictamente para uso educativo. 
---

## Flujo de trabajo

### 1. `busqueda_google_api.py` → obtener URLs desde Google
- Tú defines una **frase clave (keyword)**.  
- El script llama a la **Google Custom Search API** y devuelve una lista de resultados (enlaces).  
- Esos enlaces puedes guardarlos en un archivo `urls.txt`.  

👉 Este paso sirve para construir la base de sitios que quieres analizar.  

---

### 2. `contacto_en_paginas.py` → extraer emails de esas URLs
- Lee tu `urls.txt`.  
- Visita cada web.  
- Busca direcciones de correo en el texto de la página (regex).  
- Exporta un CSV con dos columnas: `url` y `email`.  

👉 Aquí ya obtienes tu primer listado de correos de contacto asociados a las webs que buscaste.  

---

### 3. `python_scrapper.py` → alternativa “todo en uno”
- Este script no usa el archivo `urls.txt`.  
- Hace la búsqueda en Google directamente (con la librería `googlesearch`, no con la API oficial).  
- Extrae los correos de cada resultado encontrado.  
- Guarda todo en `scrapper.txt`.  

👉 Es como un atajo: búsqueda + scraping en un solo paso, sin pasar por los dos scripts anteriores.  

⚠️ Pero tiene dos inconvenientes:  
- Menos control que con la API oficial (`busqueda_google_api.py`).  
- `googlesearch` hace scraping de resultados de Google, lo cual es más inestable y puede incumplir sus Términos de servicio.  

---

## Requisitos
- Python 3.8+  
- Librerías:  
  ```bash
  pip install requests beautifulsoup4 googlesearch-python

#IMPORTANTE:
- Estos scripts son solo para aprendizaje.
- No usar para recolección masiva ni envío de spam.
- Respeta siempre los Términos de servicio de Google y de los sitios que visites.
