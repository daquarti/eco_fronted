# 🏥 ECO Frontend

Frontend web para el sistema ECO de generación automática de informes ecocardiográficos.

## 📋 Descripción

Interfaz web moderna y responsiva que permite a los profesionales médicos procesar archivos de estudios ecocardiográficos y generar informes médicos automatizados. Compatible con archivos generados por equipos Vinno y otros sistemas similares.

## ✨ Características

### 🎯 Funcionalidades Principales
- **Procesamiento Individual**: Subir y procesar un archivo .docx/.doc
- **Procesamiento por Lotes**: Hasta 50 archivos simultáneamente con resultado en ZIP
- **Detección Automática**: Identifica tipo de estudio (Cardíaco, Stress, Carotídeo, etc.)
- **Descarga Directa**: Links automáticos de descarga de resultados

### 🎨 Interfaz
- **Diseño Moderno**: Gradientes, animaciones y UI moderna
- **Responsive**: Funciona en desktop, tablet y móvil
- **Feedback Visual**: Barras de progreso, estados de carga, notificaciones
- **Indicadores**: Estado de conexión API en tiempo real

### 🔧 Características Técnicas
- **Vanilla JavaScript**: Sin dependencias externas
- **Progressive Web App**: Funciona offline parcialmente
- **Validación Client-side**: Tipos de archivo y límites
- **Error Handling**: Manejo robusto de errores
- **CORS Ready**: Configurado para APIs remotas

## 🚀 Instalación y Uso

### Opción 1: Uso Directo (Recomendado)
```bash
# Clonar repositorio
git clone <repo-url>
cd eco-frontend

# Abrir en navegador
open index.html
```

### Opción 2: Servidor Local
```bash
# Python
python -m http.server 8080

# Node.js (si tienes http-server instalado)
npx http-server -p 8080

# Acceder a http://localhost:8080
```

## 🌐 API Backend

El frontend se conecta automáticamente a:
- **Producción**: https://eco3.onrender.com
- **Desarrollo**: http://localhost:8001 (cuando se sirve localmente)

### Endpoints Utilizados
- `GET /` - Verificación de estado
- `POST /generar_informe` - Procesamiento individual
- `POST /generar_informes_multiples` - Procesamiento por lotes

## 📱 Compatibilidad

### Navegadores Soportados
- ✅ Chrome/Chromium 80+
- ✅ Firefox 75+
- ✅ Safari 13+
- ✅ Edge 80+

### Dispositivos
- 💻 **Desktop**: Experiencia completa
- 📱 **Móvil**: Optimizado para pantallas pequeñas
- 📊 **Tablet**: Interfaz adaptada

## 🔧 Configuración

### Variables de Configuración (en index.html)
```javascript
const CONFIG = {
    API_BASE: 'https://eco3.onrender.com',  // URL del backend
    API_CHECK_INTERVAL: 10000,              // Intervalo verificación API (ms)
    MAX_FILES: 50,                          // Máximo archivos por lote
    SUPPORTED_FORMATS: ['.docx', '.doc']    // Formatos soportados
};
```

### Personalización de Estilos
Las variables CSS están definidas en `:root`:
```css
:root {
    --primary-color: #4facfe;    /* Color principal */
    --secondary-color: #43e97b;  /* Color secundario */
    --error-color: #ff6b6b;      /* Color de error */
    /* ... más variables */
}
```

## 🧪 Testing

### Testing Manual
1. Abrir `index.html` en navegador
2. Verificar indicador de API (🟢 verde = conectada)
3. Probar con archivos .docx de ejemplo
4. Verificar descargas automáticas

### Testing de Responsividad
```bash
# Usar DevTools del navegador
# Probar diferentes tamaños:
# - Mobile: 375x667 (iPhone)
# - Tablet: 768x1024 (iPad)
# - Desktop: 1920x1080
```

## 📁 Estructura del Proyecto

```
eco-frontend/
├── index.html          # Aplicación principal
├── README.md          # Este archivo
├── docs/              # Documentación adicional
├── src/               # Archivos fuente (futura modularización)
└── public/            # Assets públicos (íconos, imágenes)
```

## 🚨 Solución de Problemas

### API Desconectada (🔴)
1. Verificar conexión a internet
2. Comprobar que https://eco3.onrender.com responde
3. Revisar CORS en el navegador (F12 → Console)

### Archivos no se procesan
1. Verificar que sean archivos .docx o .doc válidos
2. Comprobar tamaño de archivos (límite del backend)
3. Revisar logs de red en DevTools

### Descargas no funcionan
1. Verificar configuración de descargas del navegador
2. Permitir descargas automáticas para el sitio
3. Comprobar espacio en disco

## 🔗 Enlaces Relacionados

- **Backend Repository**: https://github.com/daquarti/eco
- **API Docs**: https://eco3.onrender.com/docs
- **Render Deploy**: https://eco3.onrender.com

## 📄 Licencia

Este proyecto forma parte del sistema ECO de generación de informes médicos.

## 🤝 Contribuciones

1. Fork el proyecto
2. Crear branch (`git checkout -b feature/nueva-funcionalidad`)
3. Commit cambios (`git commit -m 'Agregar nueva funcionalidad'`)
4. Push al branch (`git push origin feature/nueva-funcionalidad`)
5. Crear Pull Request

## 📞 Soporte

Para reportar bugs o solicitar funcionalidades, crear un issue en el repositorio.

---

**Versión**: 2.0  
**Última actualización**: Septiembre 2025  
**Estado**: ✅ Producción Ready