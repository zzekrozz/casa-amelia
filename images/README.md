# Carpeta de imágenes

Mete aquí las fotos del producto. Después, en `index.html`, sustituye los placeholders por la ruta de cada imagen.

## Fotos que necesitas

| Archivo recomendado | Para qué se usa |
|---|---|
| `hero.webp` | Foto principal del hero (la primera que se ve) |
| `pulsera.webp` | Pulsera/cable suelto |
| `bolsita-natural.webp` | Bolsita color natural |
| `bolsita-negra.webp` | Bolsita color negro |
| `tarjeta.webp` | Tarjeta personalizada |
| `pack-completo.webp` | Pack completo preparado |
| `sobre.webp` | Sobre o paquete listo para envío |

## Consejos

- **Formato:** WebP es lo mejor (más ligero). JPG también vale. Evita PNG si la foto es grande.
- **Tamaño:** máximo 1500px de ancho. Más allá no aporta calidad en móvil y ralentiza la web.
- **Peso:** intenta que cada foto pese menos de 300 KB. Puedes optimizarlas en https://squoosh.app
- **Nombres:** minúsculas, sin acentos, sin espacios. Usa guiones (`bolsita-natural.webp`).
- **Proporciones:**
  - Hero: vertical (4:5 o 3:4) funciona mejor en móvil.
  - Galería: cuadradas (1:1).
  - Bolsitas: horizontal suave (5:4).

## Cómo conectarlas con la web

Abre `index.html` en cualquier editor y reemplaza:

```
IMAGEN_HERO_PRODUCTO  →  images/hero.webp
IMAGEN_PULSERA        →  images/pulsera.webp
IMAGEN_BOLSITA_NATURAL→  images/bolsita-natural.webp
IMAGEN_BOLSITA_NEGRA  →  images/bolsita-negra.webp
IMAGEN_TARJETA        →  images/tarjeta.webp
IMAGEN_PACK_COMPLETO  →  images/pack-completo.webp
IMAGEN_SOBRE          →  images/sobre.webp
```
