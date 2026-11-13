# GARGANTUA

## Cómo abrirlo
Doble clic en `index.html`. No necesita instalar nada.

## Cómo cargar tus datos
1. Prepara un archivo `.json` con el formato de abajo.
2. Pulsa **⇪ Cargar JSON** (arriba a la derecha). Se valida y reemplaza los datos de ejemplo.
3. Para que cargue solo al publicar la web, guárdalo como `data/real/dataset.json`.

Mapas: pulsa **Cargar imagen de mapa**, o añade `maps` en el JSON con la ruta de la imagen (por ejemplo `data/real/maps/mapa1.png`).

## Formato del JSON
```json
{
  "meta": {
    "title": "Mi conjunto",
    "is_sample": false,
    "metrics": [
      { "key": "slope_mean_deg", "label": "Pendiente media", "unit": "°", "min": 0, "max": 30 }
    ]
  },
  "regions": [
    { "id": "A1", "body": "mars", "name": "Nombre real", "coords": { "lat": 0, "lon": 0 },
      "metrics": { "slope_mean_deg": 0 }, "uncertainty": { "slope_mean_deg": 0 } }
  ],
  "maps": [ { "title": "…", "image": "data/real/maps/x.png", "source": "…", "projection": "…" } ],
  "sources": [ { "name": "…", "type": "…", "status": "cargada", "use": "…", "url": "https://…" } ],
  "methodology": [ { "title": "…", "text": "…" } ],
  "limitations": [ { "level": "alta", "title": "…", "text": "…" } ]
}
```
- `body` es `"mars"` o `"earth"`.
- Un valor que no tengas va como `null` (se muestra «SIN DATO»).
- `min`/`max` de cada métrica fijan la escala de las barras y la similitud.
- Si pones `"is_sample": true`, la interfaz muestra el aviso de datos de ejemplo.

## Estructura
- `data/` → solo datos (`sample/` ejemplo, `real/` tuyos).
- `js/` y `css/` → solo interfaz. No contienen datos científicos.
