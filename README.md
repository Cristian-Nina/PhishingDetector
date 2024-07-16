# PhishingDetector

Este repositorio contiene dos scripts, app.py y recon.py, diseñados para detectar potenciales sitios de phishing basados en ciertos criterios y palabras clave.

Descripción
app.py
app.py utiliza la API de Certstream para monitorear la emisión de nuevos certificados TLS en tiempo real. Filtra los dominios basados en una lista de palabras clave y escribe los dominios potencialmente sospechosos en un archivo llamado potentialphishing.txt.

recon.py
recon.py utiliza Selenium para abrir y analizar las páginas web listadas en potentialphishing.txt. Busca la presencia de palabras clave específicas en el contenido HTML de las páginas y guarda las URLs sospechosas en un archivo llamado phishing.txt.

Instrucciones de Ejecución
Requisitos
Python 3.x
Selenium
Firefox
GeckoDriver
Instalación
Clonar el repositorio:
bash
Copiar código
git clone https://github.com/tuusuario/phishing-detection.git
cd phishing-detection
Crear un entorno virtual (opcional pero recomendado):
bash
Copiar código
python3 -m venv venv
source venv/bin/activate  # En Windows usa `venv\Scripts\activate`
Instalar las dependencias:
bash
Copiar código
pip install -r requirements.txt
Descargar e instalar Firefox y GeckoDriver, y asegurarse de que GeckoDriver esté en el PATH o especificar su ruta en recon.py.
Ejecución
Ejecutar app.py para comenzar a monitorear la emisión de certificados y registrar posibles dominios de phishing:
bash
Copiar código
python app.py
Ejecutar recon.py para analizar las páginas web listadas en potentialphishing.txt:
bash
Copiar código
python recon.py
Notas
Asegúrate de ajustar las palabras clave en ambas scripts (app.py y recon.py) según tus necesidades específicas.
Los resultados se almacenarán en los archivos potentialphishing.txt y phishing.txt en el directorio raíz del proyecto.
Si tienes alguna pregunta o necesitas asistencia adicional, no dudes en contactarme.
