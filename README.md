# 🍎 Control de Azúcar y Alimentación con IA

Esta aplicación nació de una necesidad personal y muy especial: ayudar a mi mujer a controlar sus niveles de azúcar durante su embarazo, ya que fue diagnosticada con diabetes gestacional. Sabemos lo importante que es llevar un control riguroso de la glucosa antes y después de cada comida, y queríamos una herramienta que hiciera este proceso más sencillo y eficiente.

> **IMPORTANTE PARA USUARIOS DEL EJECUTABLE (.exe):**
>
> Si usas el ejecutable generado (`control_azucar_app.exe`), debes colocar el archivo `.env` en la misma carpeta donde esté el ejecutable para que la aplicación pueda utilizar tu API_KEY de Abacus.AI y demás configuraciones. Si no existe `.env`, la app usará valores por defecto, pero no funcionará la IA sin tu clave personal.

## ✨ Características

- 📊 **Control de Azúcar**: Registro y seguimiento de niveles de glucosa
- 🤖 **IA de Abacus.AI**: Identificación automática de alimentos en fotos
- 🕐 **Clasificación Automática**: Determina automáticamente si es desayuno, almuerzo, comida, merienda o cena
- 📋 **Historial Completo**: Guarda todos los registros con fecha y hora
- 📤 **Exportación**: Exporta datos a CSV para análisis
- 🔒 **Seguridad**: Variables de entorno para proteger API keys

## 🚀 Instalación

### 1. Instalar dependencias
```bash
pip install -r requirements.txt
```

### 2. Configurar variables de entorno
Edita el archivo `.env` y agrega tu API key de Abacus.AI:

```env
ABACUS_API_KEY=tu_api_key_real_aqui
ABACUS_API_URL=https://api.abacus.ai/v1/chat/completions
APP_NAME=Control de Azúcar y Alimentación
DATA_FILE=control_alimentacion.json
```

### 3. Obtener tu API Key de Abacus.AI
1. Ve a [Abacus.AI RouteLLM APIs](https://abacus.ai/app/route-llm-apis)
2. Genera tu API key
3. Cópiala al archivo `.env`

### 4. Ejecutar la aplicación
```bash
python control_azucar_app.py
```

## 📱 Uso de la Aplicación

### Registro Básico
1. **Ingresa tu nivel de azúcar** en mg/dL
2. **Selecciona una foto** de tus alimentos
3. **Haz clic en "Analizar con IA"** - La IA de Abacus.AI identificará automáticamente los alimentos
4. **Guarda el registro** - Se clasificará automáticamente según la hora

### Funciones Avanzadas
- **Ver Historial**: Revisa todos tus registros anteriores
- **Configurar Horarios**: Personaliza las franjas horarias para cada comida
- **Exportar Datos**: Descarga tu historial en formato CSV

## 🤖 Integración con Abacus.AI

La aplicación utiliza el modelo **GPT-4o** de Abacus.AI con capacidades de visión para:
- Analizar imágenes de alimentos
- Identificar ingredientes específicos
- Generar listas precisas de alimentos detectados

## 📊 Estructura de Datos

Los registros se guardan en formato JSON con la siguiente estructura:
```json
{
  "fecha": "2024-01-15",
  "hora": "08:30",
  "tipo_comida": "desayuno",
  "nivel_azucar": 95.5,
  "alimentos": ["Avena", "Plátano", "Leche", "Nueces"],
  "foto_path": "/ruta/a/la/foto.jpg",
  "timestamp": "2024-01-15T08:30:00"
}
```

## 🔒 Seguridad

- Las API keys se almacenan en variables de entorno (`.env`)
- El archivo `.env` debe estar en `.gitignore` para no subir credenciales
- Las imágenes se procesan localmente antes de enviar a la API

## 🛠️ Requisitos del Sistema

- Python 3.8+
- Conexión a Internet (para API de Abacus.AI)
- Tkinter (incluido en Python)
- PIL/Pillow para procesamiento de imágenes

## 📝 Notas Importantes

1. **API Key**: Necesitas una API key válida de Abacus.AI
2. **Formatos de Imagen**: Soporta JPG, PNG, BMP, GIF
3. **Límites de API**: Respeta los límites de tu plan de Abacus.AI
4. **Backup**: Los datos se guardan en `control_alimentacion.json`

## 🆘 Solución de Problemas

### Error: "ABACUS_API_KEY no encontrada"
- Verifica que el archivo `.env` existe
- Asegúrate de que la API key esté correctamente configurada

### Error de conexión con la API
- Verifica tu conexión a Internet
- Confirma que tu API key es válida
- Revisa los límites de tu plan de Abacus.AI

### La aplicación no inicia
- Instala todas las dependencias: `pip install -r requirements.txt`
- Verifica que tienes Python 3.8 o superior

## 📈 Próximas Mejoras

- 📊 Gráficos de tendencias de azúcar
- 🍎 Base de datos nutricional
- 📱 Versión móvil
- 🔔 Recordatorios y alertas
- 📧 Reportes por email

## 🤝 Contribuciones

¡Las contribuciones son bienvenidas! Si encuentras bugs o tienes ideas para mejoras, no dudes en crear un issue o pull request.

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo LICENSE para más detalles.

---

**Desarrollado con ❤️ para el cuidado de la salud**
