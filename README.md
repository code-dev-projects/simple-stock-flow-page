# simple-stock-flow-page

La **cara pública** de Simple Stock Flow: qué hace el sistema, cómo se ve, cómo está hecho y los
tres documentos para descargar.

Se publica con **GitHub Pages** desde la rama principal, carpeta raíz.

## Qué hay aquí, y qué no

```
index.html        la página entera, sin framework ni dependencias externas
style.css         los mismos tokens de color y tipografía que el portal
.nojekyll         vacío, para que GitHub Pages sirva los ficheros tal cual
.gitignore        solo la basura del sistema operativo: aquí no se genera nada
LICENSE           MIT, el texto completo que enlaza el final de este README
README.md         este fichero: qué es la página, cómo verla y qué no entra
documentos/       los tres PDF: manual de usuario, manual técnico y arquitectura
diagramas/        los SVG de la arquitectura y del arranque
capturas/         las imágenes del sistema en marcha
```

**Lo que no entra, a propósito:** el material de trabajo del proyecto, que vive aparte y no es
público. Esta página enseña **el producto**, no el expediente: lo que hace, cómo se ve, cómo está
hecho y los tres documentos que acompañan a la entrega.

**Los documentos son copias.** El original de cada PDF se genera en `simple-stock-flow-docs` desde
sus plantillas (`plantillas/construir.py`). Si cambia un manual, se regenera allí y se vuelve a
copiar aquí; no se edita el PDF a mano ni en un sitio ni en el otro.

## Cómo verla antes de publicar

No hace falta nada instalado más allá de Python:

```bash
python -m http.server 8090
```

Y abrir `http://localhost:8090`. Abrir `index.html` con doble clic **no** sirve: las rutas
relativas de las imágenes y los PDF necesitan un servidor.

## Detalles de la página

- **Sin dependencias externas.** Ni CDN, ni fuentes remotas, ni analítica. Lo que se sirve es lo
  que hay en este repositorio.
- **Sigue el tema del sistema** (claro u oscuro) y deja elegir con el botón de arriba a la derecha.
  La elección se recuerda solo en ese navegador.
- **Las imágenes cargan en diferido**, así que la primera pantalla no espera a los diagramas.
- **Comprobada a 375, 768 y 1440 px** de ancho: sin desplazamiento horizontal en ninguno.
- **Identificadores en inglés, texto en español.** Las clases CSS, las variables, el atributo
  `data-theme` y los comentarios están en inglés; lo que se lee en pantalla, en español.
- **Los diagramas siguen el tema de la página, no el del sistema.** Cada SVG es un documento
  aparte y no hereda las variables CSS, así que el script se las escribe dentro al cargar y en
  cada cambio de tema. Si renombras una variable de `style.css` que un diagrama consuma, hay que
  actualizar el puente de `index.html`, no el SVG.

## Licencia

MIT. Copyright (c) 2026 Jesus Ariel Gonzalez Bonilla. El texto completo está en
[`LICENSE`](LICENSE): puede usarse, copiarse, modificarse y distribuirse libremente, con la única
condición de conservar el aviso de copyright.
