# CameraApp

## Descripción

CameraApp es una aplicación móvil desarrollada con Ionic y Angular que permite a los usuarios tomar fotografías desde su dispositivo. Una de sus características principales es la opción de seleccionar la calidad de la foto antes de capturarla, permitiendo elegir entre calidad al 100% o al 50%. Esto es útil para ahorrar espacio de almacenamiento o para compartir imágenes más ligeras.

## Características

- Interfaz basada en Ionic Framework.
- Toma de fotografías usando la cámara del dispositivo.
- Opción para seleccionar la calidad de la imagen (100% o 50%).
- Estructura modular y fácil de mantener.
- Componentes reutilizables para explorar y mostrar información.

## Estructura del Proyecto

- `src/app/`: Contiene los módulos, páginas y componentes principales de la aplicación.
  - `tabs/`: Navegación principal por pestañas.
  - `tab2/`, `tab3/`: Páginas individuales de cada pestaña.
  - `explore-container/`: Componente reutilizable para mostrar información.
- `src/environments/`: Configuración de entornos (producción y desarrollo).
- `src/index.html`: Archivo principal HTML de la aplicación.
- `src/polyfills.ts`: Polyfills necesarios para Angular.
- `src/test.ts`: Configuración para pruebas unitarias.

## Instalación

1. Clona el repositorio:

```
git clone https://github.com/MTDEV2312/Camera_Movil_App.git
```
2. Carpeta
```
cd Camera_Movil_App
```
3. Dependencias
```
npm install
```
4. Iniciar el Proyecto
```
ionic serve
```