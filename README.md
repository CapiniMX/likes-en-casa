# Likes en Casa — App Familiar

Aplicación web para registrar likes (reconocimiento) y dislikes (oportunidades de mejora) de los hijos, administrada por mamá y papá.

## Estado actual

Prototipo funcional v1.0 — almacenamiento local (localStorage), sin servidor, sin sincronización.

## Cómo abrirlo en tu Mac

Opción 1 — Abrir directamente:

```bash
open /Users/cristianbarajas/clawd/proyectos/likes-en-casa/index.html
```

Opción 2 — Servidor local (recomendado para celular en la misma red WiFi):

```bash
cd /Users/cristianbarajas/clawd/proyectos/likes-en-casa
python3 -m http.server 8000
```

Luego abre en el navegador del Mac: `http://localhost:8000`
O desde el celular: `http://<ip-de-tu-mac>:8000` (la app es mobile-first).

## Características incluidas

- Perfiles configurables por hijo (nombre, avatar, color)
- Botones grandes para registrar like o dislike
- Categorías editables con valores predeterminados
- Comentario opcional por registro
- Historial con eliminación
- Resumen semanal con gráfica
- Modo papás con PIN (por defecto `1234`)
- Modo niños con vista de progreso y mensajes positivos
- Exportación de datos en JSON
- Sin ranking entre hermanos (cada quien ve su progreso)
- Diseño responsive mobile-first
- Animaciones suaves y confeti al registrar un like

## PIN inicial

`1234` — se puede cambiar en Ajustes.

## Datos de demostración

La app incluye dos perfiles genéricos ("Hijo 1", "Hija 1") que puedes editar o eliminar. No contiene datos reales.

## Limitaciones actuales (a resolver en próximas versiones)

- Sin sincronización entre dispositivos
- Sin respaldo automático en la nube
- Sin recompensas / metas
- Sin reportes PDF
- Sin foto del hijo (solo emoji)

## Archivos

- `index.html` — aplicación completa (HTML + CSS + JS en un solo archivo)
- `README.md` — este archivo

## Próximos pasos sugeridos

1. Sincronización entre dispositivos (backend ligero)
2. Sistema de recompensas y metas
3. Notificaciones diarias
4. Exportar reporte PDF mensual
