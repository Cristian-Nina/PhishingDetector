# PhishingDetector

Este repositorio contiene dos scripts, `app.py` y `recon.py`, diseñados para detectar potenciales sitios de phishing basados en ciertos criterios y palabras clave.

## Descripción

### app.py
`app.py` utiliza la API de Certstream para monitorear la emisión de nuevos certificados TLS en tiempo real. Filtra los dominios basados en una lista de palabras clave y escribe los dominios potencialmente sospechosos en un archivo llamado `potentialphishing.txt`.

### recon.py
`recon.py` utiliza Selenium para abrir y analizar las páginas web listadas en `potentialphishing.txt`. Busca la presencia de palabras clave específicas en el contenido HTML de las páginas y guarda las URLs sospechosas en un archivo llamado `phishing.txt`.

## Requisitos

### Software
- Python
- Firefox
- GeckoDriver

### Librerías de Python
- certstream
- selenium

## Instalación y Configuración

### 1. Clonar el Repositorio
Clona el repositorio en tu máquina local:
```bash
git clone https://github.com/Cristian-Nina/PhishingDetector.git
cd PhishingDetector
```

### 2. Instalar las Dependencias
Instala las dependencias necesarias utilizando pip:
```bash
pip install certstream selenium
```

### 3. Instalar Firefox y GeckoDriver
-Firefox: Descarga e instala Firefox desde https://www.omgubuntu.co.uk/2022/04/how-to-install-firefox-deb-apt-ubuntu-22-04
-GeckoDriver: Descarga GeckoDriver y extrae el archivo. Coloca el ejecutable de GeckoDriver en una ubicación accesible y asegúrate de que esté en tu PATH, o especifica su ruta en el script recon.py:
```python
service = Service(executable_path=r'/ruta/a/tu/geckodriver')
```


### Ejecución

### 1. Ejecutar app.py
app.py monitorea la emisión de certificados y guarda los dominios sospechosos en potentialphishing.txt:
```bash
python app.py
```
### 2. Ejecutar recon.py
recon.py analiza las páginas listadas en potentialphishing.txt y guarda las URLs confirmadas como phishing en phishing.txt:
```bash
python recon.py
```

### Archivos de Salida
-potentialphishing.txt: Contiene los dominios que coinciden con las palabras clave especificadas en app.py.
-phishing.txt: Contiene las URLs confirmadas como phishing basadas en el análisis de recon.py.

### Notas Adicionales
-Palabras clave: Ajusta las palabras clave en app.py y recon.py según tus necesidades específicas.
-Rutas: Asegúrate de que las rutas a GeckoDriver y cualquier otro recurso estén correctamente configuradas en el script recon.py.

Si tienes alguna pregunta o necesitas asistencia adicional, no dudes en contactarme.
