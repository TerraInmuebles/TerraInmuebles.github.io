# Terra Inmuebles

Web estática para GitHub Pages. No necesita Node.js, npm, React, Google AI Studio ni claves de API.

## Publicación

1. Renombra el repositorio a `terrainmuebles` desde **Settings → General → Repository name**.
2. En **Settings → Pages**, selecciona **GitHub Actions** y configura `terrainmuebles.github.io`.
3. Después del cambio de nombre, actualiza el remoto local si es necesario y publica la rama `main`.
4. Cada cambio publicado en `main` volverá a desplegar el sitio.

El workflow publica `site/` directamente. La web presenta inmuebles en venta en Andahuaylas y Apurímac. Las tres fichas actuales contienen datos ficticios de muestra y no representan ofertas reales; reemplázalas por información verificada antes de anunciar propiedades. El formulario prepara una consulta y la persona la envía desde WhatsApp.

## Catálogo de propiedades

El inventario editable está en `site/assets/data/properties.js`. Actualmente contiene tres fichas de ejemplo con datos ficticios, solo para probar el catálogo y su ventana de detalle. No son ofertas reales. Antes de anunciar inmuebles, reemplázalas por datos verificados y cambia `isDemo` a `false`.

```js
window.TERRA_INMUEBLES_PROPERTIES = [
	{
		id: 'identificador-unico',
		title: 'Título confirmado',
		type: 'casa', // casa, terreno, departamento o local
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

Los datos opcionales pueden omitirse; la ficha solo presenta los campos que existan. La búsqueda, los filtros por tipo y precio, y el ordenamiento por fecha o precio se aplican al inventario. No hay un panel administrativo ni una base de datos conectados: actualizar el catálogo requiere editar este archivo y publicar los cambios.
