# Content Studio

Herramienta (un solo archivo, `index.html`) para producir el
contenido de Instagram de un lugar: cargás el perfil, las fotos y el logo, y
la app te devuelve las fotos con marca de agua más el texto listo para
publicar (caption, stories, bio, etc.).

Corre 100% en el navegador. Los lugares, fotos y ajustes se guardan en el
propio equipo (IndexedDB + `localStorage`), no hay backend.

## Flujo de trabajo

Cada **lugar** es un cliente/proyecto con su propio recorrido de 6 pasos:

| Paso | Qué hace |
|---|---|
| Perfil | Nombre del lugar, @ de Instagram y datos de referencia |
| Fotos | Carga de fotos, mejora/upscale y conversión a JPEG |
| Marca de agua | Superpone el logo (posición, margen y opacidad configurables) |
| Referencias IG | Analiza capturas de Instagram del lugar y deduce su estilo visual |
| Generar contenido | Redacta el texto a partir de todo lo anterior |
| Exportar | Fotos procesadas, plantilla de post y texto final |

## Cómo usarlo

Abrí `index.html` con doble clic (funciona desde `file://`) o servilo local:

```bash
python3 -m http.server
# http://localhost:8000
```

1. Creá un lugar en la barra lateral.
2. Completá el perfil, cargá fotos y el logo.
3. Aplicá la marca de agua y sumá capturas de referencia de IG.
4. Elegí el tipo de contenido e idioma, generá y copiá/exportá el resultado.

## Tipos de contenido

Caption de IG · Ideas de stories · Bio de perfil · Sobre nosotros · Misión y
valores · Llamado a voluntarios. En portugués, español o inglés.

## IA (opcional)

En Ajustes podés conectar:

- **Google Gemini** (API key propia) para visión + redacción.
- **LM Studio** u otro backend local compatible con `/chat/completions`.

Las claves quedan solo en el navegador (`localStorage`). El paso de
referencias usa la visión del modelo sobre las capturas de Instagram; el
resto lo usa para redactar el contenido.

## Exportación

- Fotos con marca de agua listas para descargar.
- Plantilla de post (1080×1080, story 1080×1920 o feed 1080×1350) con
  tipografía, titular y color elegibles.
- Todo el texto generado, con botón **Copiar todo**.

## Archivos

| Archivo | Qué hace |
|---|---|
| `index.html` | Toda la app: estructura, estilos y lógica |
