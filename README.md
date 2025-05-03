# CameraApp - Botón para tomar fotos al 50% de calidad

## Descripción del cambio

Se implementó una mejora en la funcionalidad de la cámara, permitiendo al usuario elegir la calidad de la foto antes de tomarla. Ahora, al presionar el botón de la cámara, aparece un popover con dos opciones:

- **Tomar foto (100%)**: Toma la foto con calidad máxima.
- **Tomar foto (50%)**: Toma la foto con calidad media (50%).

Ambos botones llaman al método `addPhotoToGallery(quality)` con el valor de calidad correspondiente, y el servicio de fotos (`PhotoService`) ya soporta la recepción de este parámetro.

## Archivos modificados

- `src/app/tab3/tab3.page.html`: Se agregó el `<ion-popover>` con los dos botones para seleccionar la calidad de la foto.

## Ejemplo visual

Al presionar el botón de la cámara, el usuario puede elegir entre tomar una foto al 100% o al 50% de calidad.
