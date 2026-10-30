# TERRAEDIFICA

Web estática para GitHub Pages. No necesita Node.js, npm, React, Google AI Studio ni claves de API.

## Publicación

1. Crea el repositorio público `terraedifica.github.io` para conservar la dirección `https://terraedifica.github.io/`.
2. Abre esta carpeta en VS Code. Añade el remoto del repositorio y publica la rama `main`.
3. En **Settings → Pages**, selecciona **GitHub Actions** como fuente.
4. Cada commit que publiques en `main` volverá a desplegar la web.

El workflow publica `site/` directamente. Las ilustraciones son referenciales; el formulario prepara un mensaje y la persona lo envía desde WhatsApp.

## Catálogo de propiedades

El inventario editable está en `site/assets/data/properties.js`. Actualmente contiene tres fichas `Demo` con datos ficticios, solo para probar el catálogo y su ventana de detalle. Antes de anunciar inmuebles reales, reemplázalas por datos verificados y cambia `isDemo` a `false`.

```js
window.TERRAEDIFICA_PROPERTIES = [
	{
		id: 'identificador-unico',
		title: 'Título confirmado',
		type: 'casa', // casa, departamento, proyecto o construccion
		status: 'available', // available, reserved, sold o demo
		isDemo: false,
		location: 'Zona o distrito confirmado',
		priceSoles: 0, // omite si el precio aún no se confirma
		image: './assets/images/nombre-de-imagen.jpg',
		imageAlt: 'Descripción de la fotografía',
		publishedAt: '2026-10-30',
		description: 'Descripción revisada',
		areaBuilt: '90 m²',
		areaLand: '120 m²',
		bedrooms: 3,
		bathrooms: 2,
		floors: 2,
		garage: 'Sí',
		reference: 'Referencia de ubicación confirmada',
		features: ['Acabado confirmado'],
		gallery: ['./assets/images/nombre-de-imagen.jpg']
	}
];
```

Los datos opcionales pueden omitirse; la ficha solo presenta los campos que existan. La búsqueda, filtros de tipo/precio/dormitorios y ordenamiento por fecha o precio se aplican al inventario. No hay un panel administrativo ni una base de datos conectados: actualizar el catálogo requiere editar este archivo y publicar los cambios.
