# 📋 INSTRUCCIONES — ICONIQ Hats Studio NFC
## Cómo configurar la base de datos (JSONBin.io)

---

### PASO 1 — Crear cuenta gratuita en JSONBin
1. Ve a 👉 https://jsonbin.io
2. Haz clic en **Sign Up** y crea una cuenta gratis

---

### PASO 2 — Obtener tu API Key
1. Entra a tu cuenta en jsonbin.io
2. Haz clic en tu avatar (arriba a la derecha) → **API Keys**
3. Copia el valor de **X-Master-Key**
   - Se ve así: $2a$10$xxxxxxxxxxxxxxxxxxxxxxxx

---

### PASO 3 — Crear el Bin (base de datos)
1. En jsonbin.io haz clic en **+ NEW BIN**
2. Pega este contenido exacto en el editor:
   ```json
   { "escaneos": [] }
   ```
3. Ponle un nombre: **iconiq-scans**
4. Haz clic en **CREATE BIN**
5. Copia el **BIN ID** que aparece en la URL
   - Se ve así: 64a3f8b9e12ab18a9d1a2b3c

---

### PASO 4 — Pegar los datos en los archivos
Abre **index.html** y **log.html** y busca estas líneas al final:

```javascript
const JSONBIN_BIN_ID  = "TU_BIN_ID_AQUI";   // ← pega tu BIN ID aquí
const JSONBIN_API_KEY = "TU_API_KEY_AQUI";   // ← pega tu X-Master-Key aquí
```

Reemplaza los valores. Ejemplo:
```javascript
const JSONBIN_BIN_ID  = "64a3f8b9e12ab18a9d1a2b3c";
const JSONBIN_API_KEY = "$2a$10$xxxxxxxxxxxxxxxxxxxxxxxx";
```

---

### PASO 5 — Subir los archivos a GitHub
Sube los 3 archivos a tu repositorio:
- index.html
- log.html
- README.md (este archivo)

---

### PASO 6 — Programar el tag NFC
En la app **NFC Tools** (gratis), escribe esta URL en el tag de la gorra:

```
https://westmex.github.io/ALL-IN-CRYSTAL/index.html?id=gorra-allin-001
```

---

### ✅ Listo — así funciona todo
| Acción | Resultado |
|--------|-----------|
| Escaneas la gorra con tu celular | Se abre index.html, muestra ORIGINAL ✅ y guarda en la BD |
| Tu amigo abre log.html | Ve todos los escaneos en tiempo real (se actualiza cada 8 seg) |
| Alguien con tag falso | Sale "No válido ⚠️" y también se registra |

---

### ➕ Agregar más gorras
En **index.html** busca la sección TAGS y agrega líneas:

```javascript
const TAGS = {
  "gorra-allin-001": { modelo: "All-In Crystal (TEST)", activo: true },
  "gorra-allin-002": { modelo: "Otro Modelo",           activo: true },
  "gorra-allin-003": { modelo: "Edición Especial",      activo: true },
};
```

Cada gorra tiene su propia URL con su ID:
- Gorra 1: `...index.html?id=gorra-allin-001`
- Gorra 2: `...index.html?id=gorra-allin-002`
