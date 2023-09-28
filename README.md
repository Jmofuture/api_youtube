# api_youtube

## Descripción
Este proyecto consiste en un Jupyter Notebook que consume la API de YouTube y guarda los datos en un archivo Excel.

## Librerías utilizadas
- pandas
- openpyxl
- googleapiclient
- isodate

## Configuración
- API_KEY = 'tu_api_key'
- channel_id = ['UC2pmfLm7iq6Ov1UwYrWYkZA']

## Código

```python
# Importar librerías
import pandas as pd
import openpyxl as opxl
from googleapiclient.discovery import build
from IPython.display import JSON
import isodate

# Definir la clave de la API
API_KEY = 'tu_api_key'

# Definir el ID del canal
channel_id = ['UC2pmfLm7iq6Ov1UwYrWYkZA']

# Configurar el servicio de la API de YouTube
api_service_name = "youtube"
api_version = "v3"
youtube = build(api_service_name, api_version, developerKey = API_KEY)

# Función para obtener información del canal
def get_channel_info(youtube, channel_id):
    # ...
    return pd.DataFrame(all_data)

# Obtener estadísticas del canal
channel_stats = get_channel_info(youtube, channel_id)

# Obtener IDs de videos de la playlist
playlist_id = "UU2pmfLm7iq6Ov1UwYrWYkZA"

def get_video_ids(youtube,playlist_id):
    # ...
    return video_ids

video_ids = get_video_ids(youtube,playlist_id)

# Obtener detalles de los videos
def get_video_details(youtube, video_ids):
    # ...
    return pd.DataFrame(all_video_info)

video_df = get_video_details(youtube, video_ids)

# Data Pre-processing
# Comprobación de valores nulos
video_df.isnull().any()

# Conversión de tipos de datos
numeric_cols = ['viewCount', 'likeCount', 'favouriteCount', 'commentCount']
video_df[numeric_cols] = video_df[numeric_cols].apply(pd.to_numeric, errors = 'coerce', axis = 1)

