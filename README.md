# Likes en Casa

Aplicación web familiar para registrar likes (👍) y mejoras (🩹) de los hijos, con subsanación (❤️) y vitrina de logros (🏆).

## Estado actual

**v3.0 publicada en producción** · commit `c5e3087`

- 📱 Mobile-first, sin servidor, sin tracking
- 🔒 Almacenamiento privado en localStorage + IndexedDB del navegador
- 👨‍👩‍👧 Multi-perfil: mamá, papá, ambos
- 🩹 ❤️ Estados: pendiente y subsanada
- 🏆 Vitrina de logros con podio

## URL

- **Producción:** https://capinimx.github.io/likes-en-casa/
- **Preview (v3.0+):** https://capinimx.github.io/likes-en-casa-preview/

## Características

### Likes (👍)
- Botón "Dar like" abre un catálogo con 18 motivos predefinidos
- Buscador en tiempo real
- 6 categorías: Escuela, Orden y limpieza, Higiene, Ayuda, Convivencia, Actividades
- Motivos recientes arriba
- Botón "Otro motivo" para crear personalizados
- Autor (mamá/papá/ambos) y comentario opcional

### Mejoras (🩹)
- Botón "Marcar mejora" registra algo que el niño necesita trabajar
- Aparece en el historial con emoji 🩹

### Subsanación (❤️)
- Botón "❤️ Subsanar" en la pantalla principal (solo si hay mejoras pendientes)
- Abre un picker con las mejoras pendientes del niño seleccionado
- Al elegir una, pide autor + comentario opcional
- La mejora cambia a ❤️ con la fecha y autor de subsanación
- Botón ↩️ para deshacer

### 🏆 Mis Logros
- Cuarto botón en la navegación inferior
- Selector de niño con pills
- **Podio 🥇🥈🥉** con los 3 logros más recientes del niño (no es ranking entre hermanos)
- Tabs: 👍 Directos | ❤️ Superados (con contadores)
- Filtros: Todo | Mes | Semana
- Mensajes motivadores cuando no hay logros

### Fotografías
- 3 acciones: 📸 Tomar foto · 🖼️ Subir foto · 🗑️ Quitar foto
- Compresión automática (800px, JPEG 85%)
- object-fit: cover en el círculo
- Almacenadas en IndexedDB privado

### PIN
- PIN inicial `1234`, configurable en Ajustes
- Modo papás protegido, modo niños libre

## Almacenamiento

- `localStorage["***"]` — datos de la app (kids, entries, motivos, config)
- `IndexedDB["likes_en_casa_db"]` — fotografías de los perfiles

La vista previa usa nombres con namespace (`preview:***` y `likes_en_casa_db_preview`)
para aislarse de producción, ya que ambas URLs comparten origen
(`capinimx.github.io`).

## Compatibilidad

- Respaldos JSON exportables (Ajustes → 🛡️ Exportar / restaurar datos)
- Formato v3 incluye fotos, PIN, motivoId/motivoText/motivoEmoji, subsanada
- Respaldos v1 (de piztian) y v2.0 (locales) son importables
- Migración automática al actualizar: campos nuevos se inicializan vacíos
  sin afectar datos existentes

## Privacidad

- Todo el almacenamiento es local (navegador del usuario)
- Sin backend, sin tracking, sin cookies de terceros
- Sin sincronización entre dispositivos (aún)
- Las fotos no salen del celular

## Privacidad para el repo

- `.gitignore` excluye capturas de UI, respaldos JSON y archivos personales
- El repo solo contiene `index.html`, `README.md` y `.gitignore`
- Los nombres de los 3 niños demo (Luke, Dalia, Iris) son los defaults;
  no son datos reales de ninguna familia

## Repos relacionados

- Producción: https://github.com/CapiniMX/likes-en-casa
- Preview: https://github.com/CapiniMX/likes-en-casa-preview
- Respaldo histórico: https://github.com/piztian/likes-en-casa

## Changelog

### v3.0 (2026-10-11) — commit c5e3087
- 👍 Like con catálogo de 18 motivos (de EnseñandoLuk, sin montos de dinero)
- 🩹 Mejora con emoji de curita
- ❤️ Subsanada con autor (mamá/papá/ambos) y comentario
- 🏆 Sección Mis Logros con tabs Directos/Superados y podio
- 📸 Editor de fotos simplificado a 3 acciones
- 🔒 Subsanar como botón visible en pantalla principal
- 🔄 Compatibilidad con datos v2.0 (claves originales preservadas)

### v2.0 (commit 568485c)
- Editor de fotos con 3 acciones (Tomar/Subir/Quitar)
- Compresión automática de imágenes
- Almacenamiento en IndexedDB

### v1.0 (publicada en piztian)
- Versión inicial con likes, dislikes, categorías, PIN
