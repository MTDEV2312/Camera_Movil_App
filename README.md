# Mostrar fotos y nombre de archivo en la galería

## Descripción

Se realizaron cambios en la aplicación para que, además de mostrar las fotos capturadas, se muestre el nombre del archivo debajo de cada imagen en la galería.

## Cambios realizados

1. **Mostrar el nombre del archivo en la tarjeta de cada foto:**
   - En el archivo `tab2.page.html`, se agregó la etiqueta `<ion-card-subtitle>` dentro de `<ion-card-header>` para mostrar el nombre del archivo (`filepath`) debajo de cada imagen.
   - Esto permite que el nombre del archivo se visualice en un tamaño de texto más pequeño y discreto, justo debajo de la foto.

   ```html
   <ion-card>
     <img [src]="photo.webviewPath" />
     <ion-card-header>
       <ion-card-subtitle>{{photo.filepath}}</ion-card-subtitle>
     </ion-card-header>
   </ion-card>
   ```

2. **Estructura del servicio:**
   - El servicio `PhotoService` guarda el nombre del archivo en la propiedad `filepath` de cada foto, lo que permite acceder fácilmente a este dato desde la plantilla.

## Resultado

Ahora, en la galería de fotos, cada imagen muestra su nombre de archivo justo debajo, facilitando la identificación de cada foto almacenada.
