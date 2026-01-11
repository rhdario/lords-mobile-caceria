# 🏰 Lords Mobile - Guía de Cacería v1.0

Aplicación web completa para consultar equipos de héroes, drop rates y estrategias para cazar monstruos en Lords Mobile.

![Lords Mobile](https://img.shields.io/badge/Lords%20Mobile-Hunting%20Guide-gold?style=for-the-badge)
![Version](https://img.shields.io/badge/version-1.0-blue?style=for-the-badge)
![License](https://img.shields.io/badge/license-proprietary-red?style=for-the-badge)

---

## ✨ Características

- 📱 **Multiplataforma**: Funciona en Android, iOS, PC y tablets
- 🎮 **25 Monstruos**: Todos los monstruos del juego incluidos
- ⚔️ **57 Héroes LATAM**: Nombres en español latinoamericano
- 👥 **Teams F2P y P2P**: Equipos recomendados por nivel (1-3, 4, 5)
- 🎁 **Drop Rates**: Porcentajes de recompensas y rarezas
- 💾 **Equipos Personalizados**: Guarda tus propias formaciones
- 📤 **Exportar/Importar**: Respalda tu configuración en JSON
- 🎨 **Diseño Premium**: Colores oficiales de Lords Mobile
- 🛡️ **Protección Anti-Copia**: Código protegido
- 🚀 **PWA**: Instalable como app nativa
- ⚡ **Ligera**: Solo 90KB + imágenes

---

## 📂 Estructura del Proyecto

```
lords-mobile-caceria/
├── index.html          # Aplicación principal (90KB)
├── manifest.json       # Configuración PWA
├── README.md          # Este archivo
└── img/               # Carpeta de imágenes
    ├── fondo_epico.webp
    ├── monstruos/     # 25 imágenes de monstruos (.webp)
    │   ├── abeja_reina.webp
    │   ├── alaescarcha.webp
    │   ├── caballero_fantasma.webp
    │   └── ...
    └── heroes/        # 57 imágenes de héroes (.webp)
        ├── cuervo_negro.webp
        ├── matademonios.webp
        └── ...
```

---

## 🚀 Despliegue en GitHub Pages

### Paso 1: Crear Repositorio

1. Ve a https://github.com/new
2. Nombre del repositorio: `lords-mobile-caceria`
3. Marca como **Público**
4. **NO** inicialices con README
5. Crea el repositorio

### Paso 2: Subir Archivos

```bash
# En tu terminal/consola, dentro de la carpeta del proyecto
git init
git add .
git commit -m "Lords Mobile Hunting Guide v1.0"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/lords-mobile-caceria.git
git push -u origin main
```

### Paso 3: Activar GitHub Pages

1. Ve a tu repositorio en GitHub
2. Click en **Settings** (Configuración)
3. Click en **Pages** (menú lateral izquierdo)
4. En **Source**, selecciona **main** branch
5. Click **Save**
6. Espera 1-2 minutos

### Paso 4: Acceder a tu App

Tu app estará disponible en:
```
https://TU-USUARIO.github.io/lords-mobile-caceria/
```

---

## 🌐 Alternativas de Despliegue

### Opción 2: Netlify (MÁS FÁCIL)

1. Ve a https://www.netlify.com
2. Regístrate gratis
3. Arrastra la carpeta completa al área de "Deploy"
4. ¡Listo! URL: `https://random-name.netlify.app`

### Opción 3: Vercel

1. Ve a https://vercel.com
2. Regístrate gratis
3. Click "Add New" → "Project"
4. Importa desde GitHub
5. ¡Listo! URL: `https://lords-mobile.vercel.app`

---

## 📱 Instalar como App

### Android (Chrome)

1. Abre la URL en Chrome
2. Presiona los **3 puntos** (menú)
3. Selecciona **"Agregar a pantalla de inicio"**
4. ¡Listo! La app aparecerá como una app nativa

### iOS (Safari)

1. Abre la URL en Safari
2. Presiona el botón **Compartir** (⬆️)
3. Selecciona **"Agregar a inicio"**
4. Dale un nombre y presiona **Agregar**

### PC

Simplemente abre la URL en cualquier navegador moderno:
- Chrome
- Firefox
- Edge
- Safari

---

## 🎮 Monstruos Incluidos (25)

1. Abeja Reina
2. Alaescarcha
3. Alanegra
4. Ballena Ártica
5. Bestia de Nieve
6. Buen Apetito
7. Buho Carroñero
8. Caballo de Troya
9. Chamán Voodoo
10. Drider Infernal
11. Gargantua
12. Gorila
13. Grifo
14. Guiverno Jade
15. La Muerte
16. Megalarva
17. Moai Milenario
18. Necrosis
19. Noceros
20. Rugido Feroz
21. Saberfang
22. Serpiente Gladiador
23. Titán de Marea
24. Terrospín
25. **Caballero Fantasma** ⭐ (Estructura especial)

---

## 🔧 Tecnología

- **HTML5 + CSS3 + JavaScript Vanilla**
- **Sin frameworks** (React, Vue, Angular)
- **Sin dependencias externas**
- **PWA** (Progressive Web App)
- **localStorage** para persistencia de datos
- **Imágenes .webp** (optimizadas)

---

## 🛡️ Protecciones Implementadas

- ✅ Clic derecho deshabilitado
- ✅ DevTools bloqueadas (F12, Ctrl+Shift+I, Ctrl+U)
- ✅ Selección de texto deshabilitada
- ✅ Copyright visible
- ✅ Código optimizado

---

## 📧 Contacto

**Desarrollador:** knayus  
**Email:** knayus@gmail.com

Para reportar bugs, sugerencias o consultas.

---

## 📄 Licencia

© 2026 Lords Mobile Hunting Guide - by knayus  
Todos los derechos reservados.

---

## 🎯 Funcionalidades Principales

### Equipos por Nivel
- **Nivel 1-3**: Equipos F2P y P2P con opciones principal y alternativa
- **Nivel 4**: Equipos optimizados para dificultad media
- **Nivel 5**: Equipos para máxima dificultad

### Equipos Personalizados
- Crea tus propios equipos
- Guarda 5 héroes por nivel y tipo (F2P/P2P)
- Datos guardados en tu navegador (localStorage)

### Exportar/Importar
- Exporta tu configuración a archivo JSON
- Importa configuración desde archivo
- Comparte equipos con otros jugadores

### Drop Rates
- Tabla completa de recompensas
- Porcentajes de drop
- Clasificación por rareza

---

## 📸 Capturas

*(Agrega aquí capturas de pantalla de tu app cuando la tengas desplegada)*

---

## 🔄 Actualizaciones

**v1.0** (11 Enero 2026)
- ✅ Lanzamiento inicial
- ✅ 25 monstruos completos
- ✅ 57 héroes LATAM
- ✅ Sistema de equipos personalizados
- ✅ Exportar/Importar configuración
- ✅ Diseño responsive
- ✅ PWA instalable

---

**¡Disfruta cazando monstruos!** 🐉⚔️🏰
