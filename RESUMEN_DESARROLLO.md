# 📋 RESUMEN COMPLETO - Lords Mobile Guía de Cacería v1.0

**Documentación técnica completa para clonar esta aplicación en otro chat de Claude**

---

## 🎯 DESCRIPCIÓN GENERAL

**Aplicación:** PWA (Progressive Web App) - Guía de cacería de monstruos para Lords Mobile  
**Usuario:** knayus (knayus@gmail.com)  
**Archivo principal:** index.html (276KB - todo embebido)  
**Fuente de datos:** Excel con 2 hojas (MONSTRUOS y REGALOS)

**Características:**
- 25 monstruos (24 normales + Caballero Fantasma especial)
- 57 héroes (20 F2P + 4 Evento + 33 P2P)
- Equipos por nivel (1-3, 4, 5) para F2P y P2P
- Sistema de equipos personalizables (localStorage)
- Drop rates con porcentajes
- Import/Export configuración
- Diseño responsive
- Funciona offline

---

## 👥 LISTA COMPLETA DE HÉROES (57)

### F2P (20):
1. Hijo de la Luz
2. Caballero Letal
3. Guardián
4. Caballera de la Rosa
5. Forjador de Almas
6. Cuervo Negro
7. Arquera Letal
8. Matademonios
9. Cuervo Nocturno
10. Rayo Escarlata
11. Sombra
12. Estafador
13. Rastreadora
14. Trasgo Dinamita
15. Elementalista
16. Incineradora
17. Prima Donna
18. Sabio del Viento
19. Escudero del Mar
20. Reina de la Nieve

### EVENTO (4):
21. Maestro Bombardero
22. Dragón del Caos
23. Pegaso
24. Observador

### P2P (33):
25. Bárbaro
26. Furiosa
27. Don Guapo
28. Guardián del Bosque
29. El Magmaroide
30. Tramoyista
31. Vapobot
32. El Grandulón
33. Centauro Vengativo
34. Cazadora Maldita
35. Guía Etérea
36. Mujer Fatal
37. Lobo Severo
38. Mente Tejedora
39. Maestro Cocinero
40. Príncipe de Ladrones
41. Doncella Escudo
42. Rompeolas
43. Cronista
44. Seguidor Oscuro
45. Magister Oscuro
46. Bruja Onírica
47. Necroduke
48. Oráculo
49. Diablilla
50. Sabia del Desierto
51. Princesa Caracol
52. Cantante Marina
53. Zorro de la Tormenta
54. Sacerdotisa de Crepúsculo
55. Alquimista Errante
56. Muñeca Mecánica

**Función de conversión nombre → archivo:**
```javascript
function heroToFilename(name) {
    return name.toLowerCase()
        .replace(/ /g, '_')
        .replace(/á/g, 'a').replace(/é/g, 'e')
        .replace(/í/g, 'i').replace(/ó/g, 'o')
        .replace(/ú/g, 'u').replace(/ñ/g, 'n');
}
```

**Ejemplos:**
- "Cuervo Negro" → `cuervo_negro.webp`
- "Muñeca Mecánica" → `muneca_mecanica.webp`
- "Príncipe de Ladrones" → `principe_de_ladrones.webp`

---

## 🐲 LISTA COMPLETA DE MONSTRUOS (25)

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
25. **Caballero Fantasma** (estructura especial - sin niveles)

**Conversión de nombres:** misma función que héroes

---

## 📊 ESTRUCTURA DEL EXCEL

**Archivo:** `Caceria_-_copia.xlsm`

### HOJA 1: MONSTRUOS

**Columnas:**
- **A (1):** MONSTRUO - Nombre del monstruo
- **B (2):** TIPO DE HEROES - "F2P" o "P2P"
- **C (3):** BLOQUE - "BLOQUE A" / "BLOQUE B" / "BLOQUE C"
- **D (4):** Nivel - "1 A 3" / "4" / "5"
- **E (5):** EQUIPOS - "PRINCIPAL" / "ALTERNATIVO" / "Héroes (11K)" / "PERSONALIZADO"
- **F-J (6-10):** HEROE 1, HEROE 2, HEROE 3, HEROE 4, HEROE 5

**Mapeo de bloques:**
- **BLOQUE A** = Nivel 1-3
- **BLOQUE B** = Nivel 4
- **BLOQUE C** = Nivel 5

**Estructura por monstruo:**
```
Monstruo X
├── F2P
│   ├── BLOQUE A (Nivel 1-3)
│   │   ├── PRINCIPAL (5 héroes)
│   │   ├── ALTERNATIVO (5 héroes) [0 o más]
│   │   └── PERSONALIZADO (ignorar)
│   ├── BLOQUE B (Nivel 4)
│   │   ├── PRINCIPAL
│   │   ├── ALTERNATIVO [0 o más]
│   │   └── PERSONALIZADO
│   └── BLOQUE C (Nivel 5)
│       ├── PRINCIPAL
│       ├── ALTERNATIVO [0 o más]
│       ├── Héroes (11K) [0 o más] ← Equipos especiales
│       └── PERSONALIZADO
└── P2P (misma estructura)
```

**Reglas importantes:**
1. **PERSONALIZADO:** Siempre ignorar (slots vacíos para usuario)
2. **Héroes (11K):** Son equipos válidos, NO ignorar
3. **BLOQUE C debe detectarse con `endswith('C')`** no con `'C' in bloque` (porque "BLOQUE C" contiene 'B')

**Correcciones manuales necesarias después de extracción:**

```python
# Chamán Voodoo - P2P Nivel 4
equipos_por_monstruo['Chamán Voodoo']['p2p']['level4'] = [
    ['Matademonios', 'Maestro Cocinero', 'Guía Etérea', 'Maestro Bombardero', 'Cuervo Negro'],
    ['Matademonios', 'Vapobot', 'Cazadora Maldita', 'Guardián del Bosque', 'Cuervo Negro']
]

# Gorila - Agregar alternativo en P2P Nivel 1-3
equipos_por_monstruo['Gorila']['p2p']['level1-3'].insert(1, 
    ['Princesa Caracol', 'Zorro de la Tormenta', 'Elementalista', 'Incineradora', 'Diablilla']
)

# Megalarva - P2P Niveles 4 y 5
equipos_por_monstruo['Megalarva']['p2p']['level4'] = [
    ['Sacerdotisa de Crepúsculo', 'Diablilla', 'Elementalista', 'Incineradora', 'Bruja Onírica']
]
equipos_por_monstruo['Megalarva']['p2p']['level5'] = [
    ['Centauro Vengativo', 'Diablilla', 'Elementalista', 'Incineradora', 'Bruja Onírica'],
    ['Centauro Vengativo', 'Diablilla', 'Magister Oscuro', 'Incineradora', 'Oráculo']
]
```

### HOJA 2: REGALOS

**DOS TABLAS SEPARADAS:**

**TABLA 1 - ARTÍCULOS (Columnas A-C):**
- **A (1):** MONSTRUO
- **B (2):** Artículo (nombre del item)
- **C (3):** Porcentaje
- **Rango:** Filas 2-120 aprox

**TABLA 2 - RAREZAS (Columnas E-G):**
- **E (5):** MONSTRUO
- **F (6):** Rareza (Común, Poco Común, Raro, Épico, Legendario)
- **G (7):** Porcentaje
- **Rango:** Filas 2-130 aprox

**IMPORTANTE:** Los últimos 4 monstruos (Rugido Feroz, Saberfang, Serpiente Gladiador, Titán de Marea) tienen sus datos MÁS ABAJO en el Excel (filas 80-120), NO al principio.

---

## 💻 CÓDIGO PYTHON COMPLETO DE EXTRACCIÓN

```python
import openpyxl
import json

wb = openpyxl.load_workbook('Caceria_-_copia.xlsm', data_only=True)

# === HOJA MONSTRUOS ===
sheet_monstruos = wb['MONSTRUOS']
equipos_por_monstruo = {}

for row in range(2, 500):
    monstruo = sheet_monstruos.cell(row, 1).value
    if not monstruo:
        break
    
    monstruo = str(monstruo).strip()
    tipo = str(sheet_monstruos.cell(row, 2).value or '').strip().upper()
    bloque = str(sheet_monstruos.cell(row, 3).value or '').strip().upper()
    equipo_tipo = str(sheet_monstruos.cell(row, 5).value or '').strip().upper()
    
    # Leer 5 héroes
    heroes = []
    for col in range(6, 11):
        heroe = sheet_monstruos.cell(row, col).value
        if heroe and str(heroe).strip() != 'NO TIENE':
            heroes.append(str(heroe).strip())
    
    # IGNORAR PERSONALIZADO
    if 'PERSONALIZADO' in equipo_tipo:
        continue
    
    # Inicializar estructura
    if monstruo not in equipos_por_monstruo:
        equipos_por_monstruo[monstruo] = {
            'f2p': {'level1-3': [], 'level4': [], 'level5': []},
            'p2p': {'level1-3': [], 'level4': [], 'level5': []}
        }
    
    # Determinar tipo (F2P o P2P)
    tipo_key = 'f2p' if 'F2P' in tipo else 'p2p'
    
    # CRÍTICO: Usar endswith() para detectar BLOQUE
    if bloque.endswith('A'):
        nivel_key = 'level1-3'
    elif bloque.endswith('B'):
        nivel_key = 'level4'
    elif bloque.endswith('C'):
        nivel_key = 'level5'
    else:
        continue
    
    # Agregar equipo si tiene 5 héroes
    if len(heroes) == 5:
        equipos_por_monstruo[monstruo][tipo_key][nivel_key].append(heroes)

# APLICAR CORRECCIONES MANUALES
equipos_por_monstruo['Chamán Voodoo']['p2p']['level4'] = [
    ['Matademonios', 'Maestro Cocinero', 'Guía Etérea', 'Maestro Bombardero', 'Cuervo Negro'],
    ['Matademonios', 'Vapobot', 'Cazadora Maldita', 'Guardián del Bosque', 'Cuervo Negro']
]

equipos_por_monstruo['Gorila']['p2p']['level1-3'].insert(1, 
    ['Princesa Caracol', 'Zorro de la Tormenta', 'Elementalista', 'Incineradora', 'Diablilla']
)

equipos_por_monstruo['Megalarva']['p2p']['level4'] = [
    ['Sacerdotisa de Crepúsculo', 'Diablilla', 'Elementalista', 'Incineradora', 'Bruja Onírica']
]
equipos_por_monstruo['Megalarva']['p2p']['level5'] = [
    ['Centauro Vengativo', 'Diablilla', 'Elementalista', 'Incineradora', 'Bruja Onírica'],
    ['Centauro Vengativo', 'Diablilla', 'Magister Oscuro', 'Incineradora', 'Oráculo']
]

# === HOJA REGALOS ===
sheet_regalos = wb['REGALOS']
drops_por_monstruo = {}

# TABLA 1: Columnas A-C (rango ampliado hasta fila 120)
for row in range(2, 120):
    col_a = sheet_regalos.cell(row, 1).value
    col_b = sheet_regalos.cell(row, 2).value
    col_c = sheet_regalos.cell(row, 3).value
    
    if not col_a:
        continue
    
    col_a_str = str(col_a).strip()
    
    # Ignorar headers
    if 'MONSTRUO' in col_a_str.upper() or 'DROP' in col_a_str.upper():
        continue
    
    if col_b and str(col_b).strip():
        if col_a_str not in drops_por_monstruo:
            drops_por_monstruo[col_a_str] = []
        
        drops_por_monstruo[col_a_str].append({
            'item': str(col_b).strip(),
            'percent': str(col_c).strip() if col_c else '0%',
            'rarity': 'Común'
        })

# TABLA 2: Columnas E-G (rango ampliado hasta fila 130)
for row in range(2, 130):
    col_e = sheet_regalos.cell(row, 5).value
    col_f = sheet_regalos.cell(row, 6).value
    col_g = sheet_regalos.cell(row, 7).value
    
    if not col_e:
        continue
    
    col_e_str = str(col_e).strip()
    
    # Ignorar headers
    if 'MONSTRUO' in col_e_str.upper() or 'DROP' in col_e_str.upper():
        continue
    
    if col_f and str(col_f).strip():
        if col_e_str not in drops_por_monstruo:
            drops_por_monstruo[col_e_str] = []
        
        drops_por_monstruo[col_e_str].append({
            'item': str(col_f).strip(),
            'percent': str(col_g).strip() if col_g else '0%',
            'rarity': 'Común'
        })

# === GENERAR JSON FINAL ===
data_final = []

def convertir_nombre_archivo(nombre):
    return nombre.lower().replace(' ', '_').replace('á', 'a').replace('é', 'e').replace('í', 'i').replace('ó', 'o').replace('ú', 'u').replace('ñ', 'n')

for monstruo in sorted(equipos_por_monstruo.keys()):
    equipos = equipos_por_monstruo[monstruo]
    nombre_archivo = convertir_nombre_archivo(monstruo)
    
    data_final.append({
        'name': monstruo,
        'image': f'img/monstruos/{nombre_archivo}.webp',
        'special_structure': False,
        'teams': equipos,
        'dropRates': drops_por_monstruo.get(monstruo, [])
    })

# Agregar Caballero Fantasma (estructura especial)
data_final.append({
    'name': 'Caballero Fantasma',
    'image': 'img/monstruos/caballero_fantasma.webp',
    'special_structure': True,
    'teams': {
        'f2p': {
            'heroes': ['Cuervo Negro', 'Cuervo Nocturno', 'Arquera Letal', 
                      'Matademonios', 'Rayo Escarlata', 'Sombra', 
                      'Estafador', 'Rastreadora']
        },
        'p2p': {
            'heroes': ['Mujer Fatal', 'Maestro Cocinero']
        }
    },
    'dropRates': []
})

# Guardar JSON
with open('monsters_data.json', 'w', encoding='utf-8') as f:
    json.dump(data_final, f, ensure_ascii=False, indent=2)
```

---

## 📐 ESTRUCTURA JSON FINAL

### Monstruo Normal:
```javascript
{
    "name": "Abeja Reina",
    "image": "img/monstruos/abeja_reina.webp",
    "special_structure": false,
    "teams": {
        "f2p": {
            "level1-3": [
                ["Héroe1", "Héroe2", "Héroe3", "Héroe4", "Héroe5"],  // Principal
                ["HéroeA", "HéroeB", "HéroeC", "HéroeD", "HéroeE"]   // Alternativa
            ],
            "level4": [
                ["Héroe1", "Héroe2", "Héroe3", "Héroe4", "Héroe5"]
            ],
            "level5": [
                ["Héroe1", "Héroe2", "Héroe3", "Héroe4", "Héroe5"],
                ["HéroeX", "HéroeY", "HéroeZ", "HéroeW", "HéroeQ"]   // Héroes (11K)
            ]
        },
        "p2p": {
            "level1-3": [...],
            "level4": [...],
            "level5": [...]
        }
    },
    "dropRates": [
        {"item": "Veneno de Reina", "percent": "3.00%", "rarity": "Común"},
        {"item": "Común", "percent": "29.00%", "rarity": "Común"}
    ]
}
```

### Caballero Fantasma (Especial):
```javascript
{
    "name": "Caballero Fantasma",
    "image": "img/monstruos/caballero_fantasma.webp",
    "special_structure": true,
    "teams": {
        "f2p": {
            "heroes": [
                "Cuervo Negro", "Cuervo Nocturno", "Arquera Letal",
                "Matademonios", "Rayo Escarlata", "Sombra",
                "Estafador", "Rastreadora"
            ]
        },
        "p2p": {
            "heroes": ["Mujer Fatal", "Maestro Cocinero"]
        }
    },
    "dropRates": []
}
```

---

## 🎨 ESTRUCTURA HTML/CSS/JAVASCRIPT

### HTML - Estructura básica:
```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lords Mobile - Guía de Cacería</title>
    <link rel="manifest" href="manifest.json">
    <style>
        /* CSS embebido */
    </style>
</head>
<body>
    <div id="app">
        <div id="home-screen">
            <!-- Pantalla inicial con grid de monstruos -->
        </div>
        <div id="monster-detail" style="display:none;">
            <!-- Detalle del monstruo seleccionado -->
        </div>
    </div>
    <script>
        // JavaScript embebido con MONSTERS_DATA y lógica
    </script>
</body>
</html>
```

### CSS - Paleta de colores:
```css
:root {
    --bg-primary: #1a1a2e;
    --bg-secondary: #16213e;
    --gold: #FFD700;
    --blue-dark: #0f3460;
    --red: #e94560;
    --green: #4ecca3;
    --purple: #6b46c1;
}

.monsters-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    gap: 20px;
    padding: 20px;
}

.monster-card {
    background: linear-gradient(135deg, #2d1b4e 0%, #1a1a3e 100%);
    border-radius: 15px;
    padding: 15px;
    cursor: pointer;
    transition: all 0.3s ease;
    border: 3px solid transparent;
}

.monster-card:hover {
    transform: translateY(-8px);
    border-color: #FFD700;
}

.monster-img {
    width: 100%;
    height: 160px;
    object-fit: contain;
    background: rgba(0, 0, 0, 0.3);
    border-radius: 10px;
}
```

### JavaScript - Estructura de datos:
```javascript
const MONSTERS_DATA = [
    // JSON generado por Python
];

const HEROES_DATA = {
    "Cuervo Negro": { rarity: "f2p", image: "img/heroes/cuervo_negro.webp" },
    "Mujer Fatal": { rarity: "p2p", image: "img/heroes/mujer_fatal.webp" },
    // ... resto de héroes
};
```

### JavaScript - Funciones clave:
```javascript
// Conversión nombre → archivo
function heroToFilename(name) {
    return name.toLowerCase()
        .replace(/ /g, '_')
        .replace(/á/g, 'a').replace(/é/g, 'e')
        .replace(/í/g, 'i').replace(/ó/g, 'o')
        .replace(/ú/g, 'u').replace(/ñ/g, 'n');
}

// Obtener imagen de héroe
function getHeroImage(heroName) {
    return `img/heroes/${heroToFilename(heroName)}.webp`;
}

// localStorage
function saveCustomTeam(monsterName, teamType, level, heroes) {
    const customTeams = JSON.parse(localStorage.getItem('lordsmobile_custom_teams') || '{}');
    const key = `${monsterName}-${teamType}-${level}`;
    customTeams[key] = heroes;
    localStorage.setItem('lordsmobile_custom_teams', JSON.stringify(customTeams));
}

function loadCustomTeam(monsterName, teamType, level) {
    const customTeams = JSON.parse(localStorage.getItem('lordsmobile_custom_teams') || '{}');
    const key = `${monsterName}-${teamType}-${level}`;
    return customTeams[key] || null;
}
```

---

## 💾 SISTEMA DE ALMACENAMIENTO

### localStorage:
**Key:** `lordsmobile_custom_teams`

**Formato:**
```javascript
{
    "Abeja Reina-f2p-level1-3": ["Cuervo Negro", "Matademonios", null, "Sombra", null],
    "Abeja Reina-p2p-level4": [null, "Mujer Fatal", "Cazadora Maldita", null, null]
}
```

**Formato de key:** `{nombreMonstruo}-{tipo}-{nivel}`

---

## 📁 ESTRUCTURA DE ARCHIVOS

```
/
├── index.html (276KB)
├── manifest.json
├── README.md
├── RESUMEN_DESARROLLO.md
├── img/
│   ├── fondo_epico.webp (1920x1080px)
│   ├── monstruos/ (25 archivos .webp)
│   └── heroes/ (57 archivos .webp)
```

**CRÍTICO:** Rutas de imágenes SIN `/` inicial (compatibilidad GitHub Pages):
- ✅ Correcto: `img/monstruos/abeja_reina.webp`
- ❌ Incorrecto: `/img/monstruos/abeja_reina.webp`

---

## 📄 ARCHIVOS ADICIONALES

### manifest.json:
```json
{
    "name": "Lords Mobile - Guía de Cacería",
    "short_name": "LM Cacería",
    "description": "Guía completa de monstruos y equipos",
    "start_url": "./index.html",
    "display": "standalone",
    "background_color": "#1a1a2e",
    "theme_color": "#FFD700",
    "icons": []
}
```

### README.md:
Ver archivo adjunto en el ZIP.

---

## 🔑 INFORMACIÓN CRÍTICA

**NUNCA CAMBIAR:**
- 57 nombres de héroes (lista exacta arriba)
- 25 nombres de monstruos (lista exacta arriba)
- Función `heroToFilename()`
- Estructura JSON de `MONSTERS_DATA`
- localStorage key: `lordsmobile_custom_teams`
- Rutas sin `/` inicial

**CORRECCIONES OBLIGATORIAS POST-EXTRACCIÓN:**
1. Chamán Voodoo - P2P Nivel 4 (código arriba)
2. Gorila - P2P Nivel 1-3 (código arriba)
3. Megalarva - P2P Niveles 4 y 5 (código arriba)

**BUG CRÍTICO A EVITAR:**
NO usar `'C' in bloque` porque "BLOQUE C" contiene 'B' y dará falso positivo.  
✅ USAR: `bloque.endswith('C')`

---

## 📧 CONTACTO

**Usuario:** knayus  
**Email:** knayus@gmail.com  
**Versión:** 1.0  
**Fecha:** Enero 2026

**Tecnologías:**
- HTML5, CSS3
- JavaScript (Vanilla ES6+)
- PWA
- localStorage API
- openpyxl (Python para extracción)

---

## ✅ CHECKLIST PARA CLONAR

1. [ ] Extraer datos del Excel con código Python completo
2. [ ] Aplicar correcciones manuales (Chamán Voodoo, Gorila, Megalarva)
3. [ ] Verificar que todos los monstruos tienen drops completos
4. [ ] Crear HTML con estructura básica
5. [ ] Embeber CSS completo
6. [ ] Embeber JavaScript con MONSTERS_DATA
7. [ ] Embeber HEROES_DATA (57 héroes)
8. [ ] Implementar funciones principales
9. [ ] Implementar sistema localStorage
10. [ ] Agregar sistema import/export
11. [ ] Crear manifest.json
12. [ ] Crear README.md
13. [ ] Verificar rutas de imágenes (sin `/` inicial)
14. [ ] Probar en navegador

---

**FIN DEL RESUMEN v1.0 - COMPLETO PARA CLONAR**
