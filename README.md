# Migración de la galería de fotos de Tab2 a Tab3

## Descripción

El código responsable de mostrar la galería de fotos fue **movido de la Tab2 a la Tab3**. Ahora, la galería y la funcionalidad para agregar nuevas fotos se encuentran en la Tab3. La Tab2 fue restaurada a su estado por defecto, mostrando únicamente el contenido básico generado por Ionic.

---

## Cambios realizados

### 1. Código de la galería movido de Tab2 a Tab3

Antes, el archivo `tab2.page.html` contenía la galería de fotos y el botón para agregar nuevas imágenes. Ahora, este código se encuentra en [`tab3.page.html`](src/app/tab3/tab3.page.html):

```html
<!-- src/app/tab3/tab3.page.html -->
<ion-header [translucent]="true">
  <ion-toolbar>
    <ion-title>
      Photo Gallery
    </ion-title>
  </ion-toolbar>
</ion-header>

<ion-content [fullscreen]="true">
  <ion-grid>
    <ion-row>
      <ion-col size="6" *ngFor="let photo of photoService.photos; index as position">
        <ion-card>
          <img [src]="photo.webviewPath" />
          <ion-card-header>
            <ion-card-subtitle>{{photo.filepath}}</ion-card-subtitle>
          </ion-card-header> 
        </ion-card>
      </ion-col>
    </ion-row>
  </ion-grid>

  <ion-fab vertical="bottom" horizontal="center" slot="fixed">
    <ion-fab-button (click)="addPhotoToGallery()">
      <ion-icon name="camera"></ion-icon>
    </ion-fab-button>
  </ion-fab>
</ion-content>
```

Y en el archivo [`tab3.page.ts`](src/app/tab3/tab3.page.ts):

```typescript
// src/app/tab3/tab3.page.ts
import { Component } from '@angular/core';
import { PhotoService } from '../services/photo.service';

@Component({
  selector: 'app-tab3',
  templateUrl: 'tab3.page.html',
  styleUrls: ['tab3.page.scss'],
  standalone: false,
})
export class Tab3Page {

  constructor(public photoService: PhotoService) {}

  addPhotoToGallery() {
    this.photoService.addNewToGallery();
  }
  async ngOnInit() {
    await this.photoService.loadSaved();
  }
}
```

### 2. Tab2 restaurada a su estado por defecto

El archivo [`tab2.page.html`](src/app/tab2/tab2.page.html) fue restaurado a su contenido básico, eliminando la galería y dejando solo el contenido generado por defecto:

```html
<!-- src/app/tab2/tab2.page.html -->
<ion-header [translucent]="true">
  <ion-toolbar>
    <ion-title>
      Photo Gallery
    </ion-title>
  </ion-toolbar>
</ion-header>

<ion-content [fullscreen]="true">
  <ion-header collapse="condense">
    <ion-toolbar>
      <ion-title size="large">Tab 2</ion-title>
    </ion-toolbar>
  </ion-header>

  <app-explore-container name="Tab 2 page"></app-explore-container>
</ion-content>
```

Y el archivo [`tab2.page.ts`](src/app/tab2/tab2.page.ts) permanece con la estructura básica del componente:

```typescript
// src/app/tab2/tab2.page.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-tab2',
  templateUrl: 'tab2.page.html',
  styleUrls: ['tab2.page.scss'],
  standalone: false,
})
export class Tab2Page {
  constructor() {}
}
```

---

## Resultado

- **Tab3**: Ahora muestra la galería de fotos y permite agregar nuevas imágenes, mostrando el nombre del archivo debajo de cada foto.
- **Tab2**: Vuelve a mostrar solo el contenido por defecto, sin la galería de fotos.

Esto mejora la organización de la aplicación y deja la galería exclusivamente en la pestaña de fotos (Tab3).