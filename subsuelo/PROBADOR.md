Para abrir Subsuelo con el servidor local, ejecutá `node subsuelo/servidor.mjs` desde la carpeta del proyecto y entrá a `http://127.0.0.1:8774`.

Los conjuntos preparados funcionan también abriendo `dist/index.html` directamente. Para generar combinaciones nuevas, configurá `POLLINATIONS_API_KEY` como variable de entorno en la terminal del servidor y reinicialo. Usá una clave con presupuesto limitado al saldo que quieras gastar. La clave queda en el servidor. El sitio manda al proveedor las imágenes del maniquí y las prendas de la colección al tocar «Generar vistas con IA».

La primera generación de cada combinación y maniquí solicita tres imágenes. El servidor genera el frente primero y lo usa como referencia para los otros ángulos. Las vistas completas se guardan en `.vistas/` y se reutilizan para la misma selección. Si cambian las fotos de referencia, se genera una nueva versión. Cambiar de ángulo después de generar las vistas usa las imágenes guardadas.

Cada pieza se declara en `dist/piezas.js`. Para habilitarla en el probador, agregale su `outfitSlot` y las tres imágenes individuales en `dist/assets/isolated/`. Por ejemplo, para zapatillas usá `outfitSlot: 'pies'`. El campo opcional `covers` indica qué otras zonas ocupa la pieza, como la cabeza para un buzo con capucha puesta.
