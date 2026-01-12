# 📋 DOCUMENTACIÓN TÉCNICA COMPLETA - Lords Mobile Guía de Cacería v1.0

## 🎯 INFORMACIÓN GENERAL

**Aplicación:** PWA (Progressive Web App) de guía de cacería de monstruos para Lords Mobile  
**Usuario:** knayus (knayus@gmail.com)  
**Archivo principal:** index.html (238KB - HTML + CSS + JavaScript + datos embebidos)  
**Fuente de datos:** Caceria.xlsm (Excel con 25 hojas de monstruos)  
**Formato de imágenes:** WebP con transparencia

**Características:**
- 25 monstruos (24 normales + 1 especial: Caballero Fantasma)
- 57 héroes (20 F2P + 4 Evento + 33 P2P)
- Equipos predefinidos extraídos del Excel
- Equipos personalizables con localStorage
- Sistema import/export de configuración JSON
- Drop rates para cada monstruo (2-5 items por monstruo)
- Protecciones anti-copia (deshabilitables)
- Diseño responsive (móvil, tablet, desktop)

---

## 📁 ESTRUCTURA DE ARCHIVOS

```
/
├── index.html                    # Aplicación completa (238KB)
├── manifest.json                 # PWA config
├── img/
│   ├── fondo_epico.webp         # Fondo pantalla inicio (1920x1080px)
│   ├── monstruos/               # 25 imágenes .webp
│   │   ├── abeja_reina.webp
│   │   ├── alaescarcha.webp
│   │   ├── alanegra.webp
│   │   ├── ballena_artica.webp
│   │   ├── bestia_de_nieve.webp
│   │   ├── buen_apetito.webp
│   │   ├── buho_carronero.webp
│   │   ├── caballo_de_troya.webp
│   │   ├── caballero_fantasma.webp
│   │   ├── chaman_voodoo.webp
│   │   ├── drider_infernal.webp
│   │   ├── gargantua.webp
│   │   ├── gorila.webp
│   │   ├── grifo.webp
│   │   ├── guiverno_jade.webp
│   │   ├── la_muerte.webp
│   │   ├── megalarva.webp
│   │   ├── moai_milenario.webp
│   │   ├── necrosis.webp
│   │   ├── noceros.webp
│   │   ├── rugido_feroz.webp
│   │   ├── saberfang.webp
│   │   ├── serpiente_gladiador.webp
│   │   ├── titan_de_marea.webp
│   │   └── terrospin.webp
│   └── heroes/                   # 57 imágenes .webp (circulares o cuadradas)
│       ├── hijo_de_la_luz.webp
│       ├── caballero_letal.webp
│       ├── guardian.webp
│       ├── caballera_de_la_rosa.webp
│       ├── forjador_de_almas.webp
│       ├── cuervo_negro.webp
│       ├── arquera_letal.webp
│       ├── matademonios.webp
│       ├── cuervo_nocturno.webp
│       ├── rayo_escarlata.webp
│       ├── sombra.webp
│       ├── estafador.webp
│       ├── rastreadora.webp
│       ├── trasgo_dinamita.webp
│       ├── elementalista.webp
│       ├── incineradora.webp
│       ├── prima_donna.webp
│       ├── sabio_del_viento.webp
│       ├── escudero_del_mar.webp
│       ├── reina_de_la_nieve.webp
│       ├── maestro_bombardero.webp
│       ├── dragon_del_caos.webp
│       ├── pegaso.webp
│       ├── vigilante.webp
│       ├── barbaro.webp
│       ├── furiosa.webp
│       ├── don_guapo.webp
│       ├── guardian_del_bosque.webp
│       ├── el_magmaroide.webp
│       ├── tramoyista.webp
│       ├── vapobot.webp
│       ├── el_grandulon.webp
│       ├── centauro_vengativo.webp
│       ├── cazadora_maldita.webp
│       ├── guia_eterea.webp
│       ├── mujer_fatal.webp
│       ├── lobo_severo.webp
│       ├── mente_tejedora.webp
│       ├── maestro_cocinero.webp
│       ├── principe_de_ladrones.webp
│       ├── doncella_escudo.webp
│       ├── rompeolas.webp
│       ├── cronista.webp
│       ├── seguidor_oscuro.webp
│       ├── magister_oscuro.webp
│       ├── bruja_onirica.webp
│       ├── necroduke.webp
│       ├── oraculo.webp
│       ├── diablilla.webp
│       ├── sabia_del_desierto.webp
│       ├── princesa_caracol.webp
│       ├── cantante_marina.webp
│       ├── zorro_de_la_tormenta.webp
│       ├── sacerdotisa_de_crepusculo.webp
│       ├── alquimista_errante.webp
│       └── muneca_mecanica.webp
├── README.md
└── RESUMEN_DESARROLLO.md
```

**CRÍTICO:** Las rutas de imágenes NO llevan `/` inicial (compatibilidad GitHub Pages):
- ✅ Correcto: `img/monstruos/abeja_reina.webp`
- ❌ Incorrecto: `/img/monstruos/abeja_reina.webp`

---

## 👥 HÉROES (57 TOTAL)

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
24. Vigilante

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

### Conversión nombre → archivo:

```javascript
function heroToFilename(name) {
    return name
        .toLowerCase()
        .replace(/ /g, '_')
        .replace(/á/g, 'a')
        .replace(/é/g, 'e')
        .replace(/í/g, 'i')
        .replace(/ó/g, 'o')
        .replace(/ú/g, 'u')
        .replace(/ñ/g, 'n');
}

function getHeroImage(heroName) {
    return `img/heroes/${heroToFilename(heroName)}.webp`;
}
```

**Ejemplos de conversión:**
- "Cuervo Negro" → `cuervo_negro.webp`
- "Muñeca Mecánica" → `muneca_mecanica.webp`
- "Príncipe de Ladrones" → `principe_de_ladrones.webp`
- "Sacerdotisa de Crepúsculo" → `sacerdotisa_de_crepusculo.webp`
- "Sabia del Desierto" → `sabia_del_desierto.webp`

---

## 🐲 MONSTRUOS (25 TOTAL)

### Normales (24):
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

### Especial (1):
25. **Caballero Fantasma** - Estructura diferente (sin niveles, solo lista de héroes)

**Conversión nombre → archivo:** (misma función que héroes)
- "Abeja Reina" → `abeja_reina.webp`
- "Chamán Voodoo" → `chaman_voodoo.webp`
- "Titán de Marea" → `titan_de_marea.webp`

---

## 📐 ESTRUCTURA DE DATOS JSON

### Monstruo Normal:

```javascript
{
    "name": "Abeja Reina",
    "image": "img/monstruos/abeja_reina.webp",
    "special_structure": false,
    "teams": {
        "f2p": {
            "level1-3": [
                ["Héroe1", "Héroe2", "Héroe3", "Héroe4", "Héroe5"],     // Principal
                ["HéroeA", "HéroeB", "HéroeC", "HéroeD", "HéroeE"],     // Alternativa
                ["HéroeX", "HéroeY", "HéroeZ", "HéroeW", "HéroeQ"]      // Alternativa 2 (si existe)
            ],
            "level4": [
                ["Héroe1", "Héroe2", "Héroe3", "Héroe4", "Héroe5"],     // Principal
                ["HéroeA", "HéroeB", "HéroeC", "HéroeD", "HéroeE"],     // Alternativa (si existe)
                ["HéroeX", "HéroeY", "HéroeZ", "HéroeW", "HéroeQ"]      // Alternativa 2 (si existe)
            ],
            "level5": [
                ["Héroe1", "Héroe2", "Héroe3", "Héroe4", "Héroe5"],     // Principal
                ["HéroeA", "HéroeB", "HéroeC", "HéroeD", "HéroeE"],     // Alternativa (si existe)
                ["HéroeX", "HéroeY", "HéroeZ", "HéroeW", "HéroeQ"]      // Alternativa 2 (si existe)
            ]
        },
        "p2p": {
            "level1-3": [
                ["Héroe1", "Héroe2", "Héroe3", "Héroe4", "Héroe5"],
                ["HéroeA", "HéroeB", "HéroeC", "HéroeD", "HéroeE"],
                ["HéroeX", "HéroeY", "HéroeZ", "HéroeW", "HéroeQ"]
            ],
            "level4": [
                ["Héroe1", "Héroe2", "Héroe3", "Héroe4", "Héroe5"],
                ["HéroeA", "HéroeB", "HéroeC", "HéroeD", "HéroeE"],
                ["HéroeX", "HéroeY", "HéroeZ", "HéroeW", "HéroeQ"]
            ],
            "level5": [
                ["Héroe1", "Héroe2", "Héroe3", "Héroe4", "Héroe5"],
                ["HéroeA", "HéroeB", "HéroeC", "HéroeD", "HéroeE"],
                ["HéroeX", "HéroeY", "HéroeZ", "HéroeW", "HéroeQ"]
            ]
        }
    },
    "dropRates": [
        {
            "item": "Queen Venom",
            "percent": "3.00%",
            "rarity": "Común"
        },
        {
            "item": "Royal Stinger",
            "percent": "6.00%",
            "rarity": "Poco Común"
        },
        {
            "item": "Buzzing Husk",
            "percent": "45.50%",
            "rarity": "Raro"
        },
        {
            "item": "Bee Chrysalis",
            "percent": "45.50%",
            "rarity": "Épico"
        }
    ]
}
```

**IMPORTANTE:** Cada nivel puede tener entre 0 y 3 equipos (Principal + hasta 2 Alternativas). Todos los equipos tienen exactamente 5 héroes.

### Caballero Fantasma (Especial):

```javascript
{
    "name": "Caballero Fantasma",
    "image": "img/monstruos/caballero_fantasma.webp",
    "special_structure": true,
    "teams": {
        "f2p": {
            "heroes": [
                "Cuervo Negro",
                "Cuervo Nocturno",
                "Arquera Letal",
                "Matademonios",
                "Rayo Escarlata",
                "Sombra",
                "Estafador",
                "Rastreadora"
            ]
        },
        "p2p": {
            "heroes": [
                "Mujer Fatal",
                "Maestro Cocinero"
            ]
        }
    },
    "dropRates": []
}
```

---

## 📊 EXTRACCIÓN DE DATOS DEL EXCEL

**Archivo fuente:** `Caceria.xlsm`  
**25 hojas:** Una por cada monstruo (nombre exacto del monstruo)

### Ubicaciones en Excel:

- **F2P:** Columna C (índice 3), filas 15-19, 21-25, 27-31
- **P2P:** Columna J (índice 10), filas 15-19, 21-25, 27-31
- **Drop Rates:** Columnas J-K-L (índices 10-11-12), filas 7-11

**Estructura de filas por nivel:**
- **Nivel 1-3:** Filas 15, 17, 19 (Principal, Alternativa, Alternativa 2)
- **Nivel 4:** Filas 21, 23, 25 (Principal, Alternativa, Alternativa 2)
- **Nivel 5:** Filas 27, 29, 31 (Principal, Alternativa, Alternativa 2)

### Python - Código de extracción:

```python
import openpyxl
import json
import re

wb = openpyxl.load_workbook('Caceria.xlsm', data_only=True)

def limpiar_nombre(nombre):
    """Limpia nombres de héroes eliminando números y guiones iniciales"""
    if not nombre:
        return None
    nombre = str(nombre).strip()
    # Ignorar etiquetas como "Héroes (11K)"
    if '(' in nombre or 'Héroes' == nombre:
        return None
    nombre = re.sub(r'^[\d\-\s]+', '', nombre)
    if len(nombre) < 3:
        return None
    return nombre

def extraer_todos_equipos(sheet, start_col, filas):
    """Extrae TODOS los equipos válidos de un conjunto de filas"""
    equipos = []
    for row in filas:
        equipo = []
        for col_offset in range(5):  # Exactamente 5 héroes
            valor = sheet.cell(row, start_col + col_offset).value
            nombre = limpiar_nombre(valor)
            if nombre:
                equipo.append(nombre)
        if len(equipo) == 5:  # Solo si tiene exactamente 5
            equipos.append(equipo)
    return equipos

def extraer_drops(sheet):
    """Extrae drop rates desde columna J-L (10-12), filas 7-11"""
    drops = []
    for row in range(7, 12):
        item = sheet.cell(row, 10).value      # Columna J
        percent = sheet.cell(row, 11).value   # Columna K
        rarity = sheet.cell(row, 12).value    # Columna L
        
        if item and percent:
            drops.append({
                'item': str(item).strip(),
                'percent': str(percent).strip(),
                'rarity': str(rarity).strip() if rarity else 'Común'
            })
    return drops

# Lista de monstruos normales
monstruos_normales = [
    'Abeja Reina', 'Alaescarcha', 'Alanegra', 'Ballena Ártica', 'Bestia de Nieve',
    'Buen Apetito', 'Buho Carroñero', 'Caballo de Troya', 'Chamán Voodoo',
    'Drider Infernal', 'Gargantua', 'Gorila', 'Grifo', 'Guiverno Jade',
    'La Muerte', 'Megalarva', 'Moai Milenario', 'Necrosis', 'Noceros',
    'Rugido Feroz', 'Saberfang', 'Serpiente Gladiador', 'Titán de Marea',
    'Terrospín'
]

data_completa = []

for monstruo in monstruos_normales:
    sheet = wb[monstruo]
    
    # F2P: Columna C (3), filas 15-19, 21-25, 27-31
    f2p = {
        'level1-3': extraer_todos_equipos(sheet, 3, [15, 17, 19]),
        'level4': extraer_todos_equipos(sheet, 3, [21, 23, 25]),
        'level5': extraer_todos_equipos(sheet, 3, [27, 29, 31])
    }
    
    # P2P: Columna J (10), filas 15-19, 21-25, 27-31
    p2p = {
        'level1-3': extraer_todos_equipos(sheet, 10, [15, 17, 19]),
        'level4': extraer_todos_equipos(sheet, 10, [21, 23, 25]),
        'level5': extraer_todos_equipos(sheet, 10, [27, 29, 31])
    }
    
    drops = extraer_drops(sheet)
    
    nombre_archivo = monstruo.lower().replace(' ', '_').replace('á', 'a').replace('é', 'e').replace('í', 'i').replace('ó', 'o').replace('ú', 'u').replace('ñ', 'n')
    
    data_completa.append({
        'name': monstruo,
        'image': f'img/monstruos/{nombre_archivo}.webp',
        'special_structure': False,
        'teams': {'f2p': f2p, 'p2p': p2p},
        'dropRates': drops
    })

# Caballero Fantasma (estructura especial)
data_completa.append({
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
    json.dump(data_completa, f, ensure_ascii=False, indent=2)
```

---

## 🎨 DISEÑO Y ESTILOS CSS

### Paleta de colores:

```css
/* Fondos */
--bg-primary: #1a1a2e;
--bg-secondary: #16213e;
--bg-gradient: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);

/* Acentos */
--gold: #FFD700;           /* Dorado - títulos */
--blue-dark: #0f3460;      /* Azul oscuro - botones */
--red: #e94560;            /* Rojo - hover, bordes */
--green: #4ecca3;          /* Verde menta - héroes */
--purple: #6b46c1;         /* Púrpura - modales */
--purple-light: #b794f6;   /* Púrpura claro */

/* Texto */
--text-primary: #ffffff;
--text-secondary: rgba(255, 255, 255, 0.8);
```

### Tipografía:

```css
font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
```

### Grid de monstruos:

```css
.monsters-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    gap: 20px;
    padding: 20px;
    max-width: 1400px;
    margin: 0 auto;
    padding-bottom: 100px;
}

.monster-card {
    background: linear-gradient(135deg, #2d1b4e 0%, #1a1a3e 100%);
    border-radius: 15px;
    padding: 15px;
    cursor: pointer;
    transition: all 0.3s ease;
    border: 3px solid transparent;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.5);
}

.monster-card:hover {
    transform: translateY(-8px);
    border-color: #FFD700;
    box-shadow: 0 8px 25px rgba(255, 215, 0, 0.4);
}

.monster-img {
    width: 100%;
    height: 160px;
    object-fit: contain;
    border-radius: 10px;
    margin-bottom: 12px;
    background: rgba(0, 0, 0, 0.3);
}

.monster-name {
    font-size: 16px;
    font-weight: bold;
    color: #FFD700;
    text-align: center;
    text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.8);
}
```

### Layout responsive:

```css
@media (max-width: 768px) {
    .monsters-grid {
        grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
        gap: 15px;
    }
    
    .monster-img {
        height: 150px;
    }
}
```

---

## 📱 ESTRUCTURA DE PANTALLAS

### 1. HOME (Inicio):
```html
<div class="home-screen">
    <div class="home-content">
        <h1>🏰 Lords Mobile</h1>
        <h2>Guía de Cacería de Monstruos</h2>
        <button onclick="showMonstersList()">🎯 Comenzar Cacería</button>
    </div>
</div>
```
- Fondo: `img/fondo_epico.webp` con overlay oscuro
- Botón centrado con efecto hover

### 2. LISTA DE MONSTRUOS:
```html
<div class="monsters-screen">
    <div class="header-actions">
        <button onclick="exportConfig()">💾 Exportar</button>
        <button onclick="importConfig()">📥 Importar</button>
        <button onclick="resetConfig()">🔄 Reset</button>
        <button onclick="contactEmail()">✉️ Contacto</button>
    </div>
    <div class="monsters-grid">
        <!-- 25 cards de monstruos -->
    </div>
    <div class="footer">
        <button onclick="showHome()">🏠 Inicio</button>
    </div>
</div>
```
- Grid responsivo de 25 cards
- Cada card: imagen + nombre + click handler

### 3. DETALLE DE MONSTRUO:
```html
<div class="monster-detail">
    <div class="detail-header">
        <button onclick="goBack()">← Volver</button>
        <h2>{Nombre Monstruo}</h2>
    </div>
    
    <img src="{monster.image}" class="monster-detail-img">
    
    <!-- Sección F2P -->
    <div class="team-section">
        <div class="section-title">🆓 Héroes F2P</div>
        
        <!-- Nivel 1-3 -->
        <div class="level-block">
            <div class="level-label">Nivel 1-3</div>
            <div class="team-row">
                <span class="team-label">Principal:</span>
                <!-- 5 botones de héroes -->
            </div>
            <div class="team-row">
                <span class="team-label">Alternativa:</span>
                <!-- 5 botones de héroes -->
            </div>
            <!-- Más alternativas si existen -->
            <div class="team-row">
                <span class="team-label">✨ Mis Héroes Personalizados:</span>
                <!-- 5 slots editables -->
            </div>
        </div>
        
        <!-- Nivel 4 (igual) -->
        <!-- Nivel 5 (igual) -->
    </div>
    
    <!-- Sección P2P (idéntica estructura) -->
    
    <!-- Drop Rates -->
    <div class="drops-section">
        <h3>💎 Recompensas (Drop Rates)</h3>
        <table class="drops-table">
            <thead>
                <tr>
                    <th>Item</th>
                    <th>Drops</th>
                    <th>Progreso</th>
                    <th>Rarity</th>
                </tr>
            </thead>
            <tbody>
                <!-- Filas de drops -->
            </tbody>
        </table>
    </div>
</div>
```

### Diseño de botón de héroe:
```html
<div class="hero-btn" style="display: flex; flex-direction: column; align-items: center; gap: 5px; padding: 10px; min-width: 80px;">
    <img src="img/heroes/cuervo_negro.webp" alt="Cuervo Negro" 
         style="width: 70px; height: 70px; border-radius: 10px; object-fit: cover; border: 2px solid #4ecca3;" 
         onerror="this.style.display='none'">
    <span style="font-size: 11px; text-align: center; line-height: 1.2;">Cuervo Negro</span>
</div>
```
- Imagen: 70x70px arriba
- Nombre: debajo, centrado, 11px
- Border verde (#4ecca3)
- Si falla imagen: se oculta

### 4. MODAL DE SELECCIÓN DE HÉROE:
```html
<div class="hero-modal" id="heroModal">
    <div class="hero-modal-content">
        <div class="hero-modal-header">
            <h3>⚔️ Selecciona un Héroe</h3>
            <button onclick="closeHeroModal()">✖</button>
        </div>
        <div class="heroes-selector" id="heroesSelector">
            <!-- 57 botones de héroes en grid -->
        </div>
    </div>
</div>
```
- Modal overlay con blur
- Grid de héroes scrolleable
- Click en héroe: asigna y cierra

---

## 💾 SISTEMA DE ALMACENAMIENTO

### localStorage:

**Key:** `lordsmobile_custom_teams`

**Estructura:**
```javascript
{
    "Abeja Reina-f2p-level1-3": ["Cuervo Negro", "Matademonios", null, "Sombra", null],
    "Abeja Reina-p2p-level4": [null, "Mujer Fatal", "Cazadora Maldita", null, null],
    "Gorila-f2p-level5": ["Vigilante", "Pegaso", null, null, "Dragón del Caos"]
}
```

**Formato de key:** `{nombreMonstruo}-{tipo}-{nivel}`
- `tipo`: "f2p" o "p2p"
- `nivel`: "level1-3", "level4", "level5"

**Value:** Array de 5 elementos (nombres de héroes o null)

### Funciones principales:

```javascript
// Variables globales
let customTeams = {};
let currentMonster = null;
let currentSlot = null;

// Inicialización
window.addEventListener('DOMContentLoaded', () => {
    loadCustomTeams();
    showHome();
});

// Cargar
function loadCustomTeams() {
    const saved = localStorage.getItem('lordsmobile_custom_teams');
    if (saved) {
        try {
            customTeams = JSON.parse(saved);
        } catch (e) {
            customTeams = {};
        }
    }
}

// Guardar
function saveCustomTeams() {
    localStorage.setItem('lordsmobile_custom_teams', JSON.stringify(customTeams));
}

// Exportar
function exportConfig() {
    const data = JSON.stringify(customTeams, null, 2);
    const blob = new Blob([data], { type: 'application/json' });
    const url = URL.createObjectURL(blob);
    const a = document.createElement('a');
    a.href = url;
    a.download = 'lordsmobile_config.json';
    a.click();
    URL.revokeObjectURL(url);
    alert('✅ Configuración exportada');
}

// Importar
function importConfig() {
    const input = document.createElement('input');
    input.type = 'file';
    input.accept = '.json';
    input.onchange = e => {
        const file = e.target.files[0];
        if (!file) return;
        const reader = new FileReader();
        reader.onload = event => {
            try {
                customTeams = JSON.parse(event.target.result);
                saveCustomTeams();
                alert('✅ Configuración importada correctamente');
                if (currentMonster) renderMonsterDetail();
            } catch (err) {
                alert('❌ Error: archivo JSON inválido');
            }
        };
        reader.readAsText(file);
    };
    input.click();
}

// Reset
function resetConfig() {
    if (confirm('⚠️ ¿Eliminar TODOS los equipos personalizados?')) {
        customTeams = {};
        saveCustomTeams();
        alert('✅ Configuración reiniciada');
        if (currentMonster) renderMonsterDetail();
    }
}

// Contacto
function contactEmail() {
    window.location.href = 'mailto:knayus@gmail.com?subject=Lords Mobile - Guía de Cacería';
}
```

---

## 🔧 FUNCIONES JAVASCRIPT CRÍTICAS

### Navegación:

```javascript
function showHome() {
    document.querySelector('.home-screen').style.display = 'flex';
    document.querySelector('.monsters-screen').style.display = 'none';
    document.querySelector('.monster-detail').style.display = 'none';
}

function showMonstersList() {
    document.querySelector('.home-screen').style.display = 'none';
    document.querySelector('.monsters-screen').style.display = 'block';
    document.querySelector('.monster-detail').style.display = 'none';
    renderMonstersList();
}

function showMonsterDetail(monsterName) {
    currentMonster = MONSTERS_DATA.find(m => m.name === monsterName);
    document.querySelector('.home-screen').style.display = 'none';
    document.querySelector('.monsters-screen').style.display = 'none';
    document.querySelector('.monster-detail').style.display = 'block';
    renderMonsterDetail();
}

function goBack() {
    showMonstersList();
}
```

### Renderizado:

```javascript
function renderMonstersList() {
    const grid = document.querySelector('.monsters-grid');
    grid.innerHTML = MONSTERS_DATA.map(monster => `
        <div class="monster-card" onclick="showMonsterDetail('${monster.name}')">
            <img src="${monster.image}" alt="${monster.name}" class="monster-img">
            <div class="monster-name">${monster.name}</div>
        </div>
    `).join('');
}

function renderMonsterDetail() {
    if (!currentMonster) return;
    
    const container = document.querySelector('.monster-detail');
    
    if (currentMonster.special_structure) {
        // Caballero Fantasma
        container.innerHTML = `
            <div class="detail-header">
                <button onclick="goBack()">← Volver</button>
                <h2>${currentMonster.name}</h2>
            </div>
            <img src="${currentMonster.image}" class="monster-detail-img">
            ${renderSpecialTeams()}
        `;
    } else {
        // Monstruos normales
        container.innerHTML = `
            <div class="detail-header">
                <button onclick="goBack()">← Volver</button>
                <h2>${currentMonster.name}</h2>
            </div>
            <img src="${currentMonster.image}" class="monster-detail-img">
            ${renderTeamType('F2P', 'f2p')}
            ${renderTeamType('P2P', 'p2p')}
            ${renderDropRates()}
        `;
    }
}

function renderTeamType(title, type) {
    const teams = currentMonster.teams[type];
    let html = `<div class="team-section"><div class="section-title">${title === 'F2P' ? '🆓' : '💰'} Héroes ${title}</div>`;
    
    ['level1-3', 'level4', 'level5'].forEach(level => {
        const levelName = level === 'level1-3' ? 'Nivel 1-3' : level === 'level4' ? 'Nivel 4' : 'Nivel 5';
        html += `
            <div class="level-block">
                <div class="level-label">${levelName}</div>
                ${teams[level].map((team, idx) => `
                    <div class="team-row">
                        <span class="team-label">${idx === 0 ? 'Principal:' : `Alternativa${idx > 1 ? ' ' + idx : ''}:`}</span>
                        ${team.map(h => renderHeroButton(h)).join('')}
                    </div>
                `).join('')}
                <div class="team-row">
                    <span class="team-label">✨ Mis Héroes Personalizados:</span>
                    ${renderCustomHeroSlots(type, level, 5)}
                </div>
            </div>
        `;
    });
    
    html += '</div>';
    return html;
}

function renderHeroButton(heroName) {
    return `
        <div class="hero-btn" style="display: flex; flex-direction: column; align-items: center; gap: 5px; padding: 10px; min-width: 80px;">
            <img src="${getHeroImage(heroName)}" alt="${heroName}" 
                 style="width: 70px; height: 70px; border-radius: 10px; object-fit: cover; border: 2px solid #4ecca3;" 
                 onerror="this.style.display='none'">
            <span style="font-size: 11px; text-align: center; line-height: 1.2;">${heroName}</span>
        </div>
    `;
}

function renderCustomHeroSlots(type, level, count) {
    const key = `${currentMonster.name}-${type}-${level}`;
    const saved = customTeams[key] || [];
    
    let html = '';
    for (let i = 0; i < count; i++) {
        const hero = saved[i];
        if (hero) {
            html += `
                <div class="hero-slot filled" onclick="openHeroModal('${type}', '${level}', ${i})">
                    <img src="${getHeroImage(hero)}" alt="${hero}" 
                         style="width: 100%; height: 100%; object-fit: cover; border-radius: 8px;" 
                         onerror="this.outerHTML='<div style=\\'font-size: 12px; text-align: center;\\'>${hero.substring(0, 3)}</div>'">
                </div>
            `;
        } else {
            html += `
                <div class="hero-slot" onclick="openHeroModal('${type}', '${level}', ${i})">
                    +
                </div>
            `;
        }
    }
    return html;
}

function renderDropRates() {
    if (!currentMonster.dropRates || currentMonster.dropRates.length === 0) return '';
    
    return `
        <div class="drops-section">
            <h3>💎 Recompensas (Drop Rates)</h3>
            <table class="drops-table">
                <thead>
                    <tr>
                        <th>Item</th>
                        <th>Drops</th>
                        <th>Progreso</th>
                        <th>Rarity</th>
                    </tr>
                </thead>
                <tbody>
                    ${currentMonster.dropRates.map(drop => `
                        <tr>
                            <td>${drop.item}</td>
                            <td>${drop.percent}</td>
                            <td><div class="drop-bar" style="width: ${drop.percent}"></div></td>
                            <td>${drop.rarity}</td>
                        </tr>
                    `).join('')}
                </tbody>
            </table>
        </div>
    `;
}

function renderSpecialTeams() {
    // Para Caballero Fantasma
    return `
        <div class="special-teams">
            <div class="team-section">
                <div class="section-title">🆓 Héroes F2P</div>
                ${currentMonster.teams.f2p.heroes.map(h => renderHeroButton(h)).join('')}
            </div>
            <div class="team-section">
                <div class="section-title">💰 Héroes P2P</div>
                ${currentMonster.teams.p2p.heroes.map(h => renderHeroButton(h)).join('')}
            </div>
        </div>
    `;
}
```

### Modal de Héroes:

```javascript
function openHeroModal(type, level, slot) {
    currentSlot = { type, level, slot };
    const modal = document.getElementById('heroModal');
    const selector = document.getElementById('heroesSelector');
    
    const allHeroes = [...HEROES_DATA.f2p, ...HEROES_DATA.event, ...HEROES_DATA.p2p];
    
    selector.innerHTML = allHeroes.map(heroName => `
        <div class="hero-selector-btn" onclick="selectHero('${heroName.replace(/'/g, "\\'")}')">
            <img src="${getHeroImage(heroName)}" alt="${heroName}" 
                 style="width: 60px; height: 60px; border-radius: 50%; object-fit: cover;" 
                 onerror="this.outerHTML='<div style=\\'width: 60px; height: 60px; background: rgba(255,255,255,0.1); border-radius: 50%; display: flex; align-items: center; justify-content: center;\\'>${heroName.substring(0, 2)}</div>'">
            <div>${heroName}</div>
        </div>
    `).join('');
    
    modal.classList.add('active');
}

function closeHeroModal() {
    document.getElementById('heroModal').classList.remove('active');
}

function selectHero(heroName) {
    const key = `${currentMonster.name}-${currentSlot.type}-${currentSlot.level}`;
    
    if (!customTeams[key]) {
        customTeams[key] = [null, null, null, null, null];
    }
    
    customTeams[key][currentSlot.slot] = heroName;
    saveCustomTeams();
    closeHeroModal();
    renderMonsterDetail();
}
```

---

## 🔒 PROTECCIONES ANTI-COPIA

### JavaScript:

```javascript
// Bloquear clic derecho
document.addEventListener('contextmenu', e => e.preventDefault());

// Bloquear atajos de teclado
document.addEventListener('keydown', e => {
    if (e.key === 'F12') {
        e.preventDefault();
        return false;
    }
    if (e.ctrlKey && e.shiftKey && e.key === 'I') {
        e.preventDefault();
        return false;
    }
    if (e.ctrlKey && e.key === 'u') {
        e.preventDefault();
        return false;
    }
    if (e.ctrlKey && e.key === 's') {
        e.preventDefault();
        return false;
    }
});
```

### CSS:

```css
body {
    user-select: none;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
}

body::before {
    content: "© Lords Mobile Hunting Guide - by knayus";
    position: fixed;
    bottom: 10px;
    right: 10px;
    font-size: 12px;
    color: rgba(255, 255, 255, 0.3);
    pointer-events: none;
    z-index: 9999;
}
```

---

## 🚀 PWA CONFIGURATION

### manifest.json:

```json
{
    "name": "Lords Mobile - Guía de Cacería",
    "short_name": "LM Cacería",
    "description": "Guía completa de cacería de monstruos para Lords Mobile",
    "start_url": "./",
    "display": "standalone",
    "background_color": "#1a1a2e",
    "theme_color": "#1a1a2e",
    "orientation": "portrait",
    "icons": [
        {
            "src": "icon-192.png",
            "sizes": "192x192",
            "type": "image/png",
            "purpose": "any maskable"
        },
        {
            "src": "icon-512.png",
            "sizes": "512x512",
            "type": "image/png",
            "purpose": "any maskable"
        }
    ]
}
```

### HTML head:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#1a1a2e">
<link rel="manifest" href="manifest.json">
<link rel="icon" type="image/png" href="icon-192.png">
```

---

## 📊 ESTADÍSTICAS

- **HTML total:** 238 KB
- **Líneas de código:** ~2,400
- **Monstruos:** 25
- **Héroes:** 57
- **Equipos predefinidos:** ~150-200
- **Drop rates:** ~90 items
- **Slots personalizables:** 375 (25 × 3 niveles × 5 slots)
- **Imágenes totales:** 83 (.webp)

---

## 📧 CONTACTO Y CRÉDITOS

**Desarrollado para:** knayus  
**Email:** knayus@gmail.com  
**Fecha:** Enero 2026  
**Versión:** 1.0

**Tecnologías:**
- HTML5
- CSS3 (Flexbox, Grid, Animations)
- JavaScript (Vanilla ES6+)
- PWA (Progressive Web App)
- localStorage API
- FileReader API (import)
- Blob API (export)

**Fuente de datos:** Excel (Caceria.xlsm) → Python → JSON embebido en HTML

---

## 🎯 INFORMACIÓN CRÍTICA PARA CLAUDE

Este documento contiene TODO lo necesario para duplicar la aplicación exactamente igual:

**NUNCA cambiar:**
- 57 nombres exactos de héroes (ver lista completa)
- 25 nombres de monstruos
- Función `heroToFilename()` - CRÍTICA para conversión
- Estructura JSON de `MONSTERS_DATA`
- localStorage key: `lordsmobile_custom_teams`
- Rutas de imágenes sin `/` inicial
- Columnas Excel: F2P=3, P2P=10, Drops=10-12
- Filas Excel: 15-19, 21-25, 27-31

**Archivos generados:**
- ✅ index.html (238KB - app completa)
- ✅ manifest.json
- ✅ 25 imágenes de monstruos (.webp)
- ✅ 57 imágenes de héroes (.webp)
- ✅ README.md
- ✅ RESUMEN_DESARROLLO.md

---

**FIN DE LA DOCUMENTACIÓN TÉCNICA v1.0**
