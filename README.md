# Likes en Casa

Aplicación web familiar para registrar likes (👍) y mejoras (🩹) de los hijos, con subsanación (❤️) y vitrina de logros (🏆).

## Estado actual

**v3.1 publicada en producción** · commit `199e268`

- 📱 Mobile-first, sin servidor, sin tracking
- 🔒 Almacenamiento privado en localStorage + IndexedDB del navegador
- 👨‍👩‍👧 Multi-perfil: mamá, papá, ambos
- 🩹 ❤️ Estados: pendiente y subsanada
- 🏆 Vitrina de logros con podio
- ⚡ Selector rápido de motivos al dar Like

## URL

- **Producción:** https://capinimx.github.io/likes-en-casa/
- **Preview (v3.1+):** https://capinimx.github.io/likes-en-casa-preview/

## Características

### Selector rápido de Likes (⚡ nuevo en v3.1)
Al tocar **👍 Dar like** aparece un modal compacto con 7 motivos generales + Otro motivo:

- 📚 Escuela y aprendizaje
- 🧹 Orden y limpieza
- 🪥 Higiene y autocuidado
- 🏡 Ayuda en casa
- 🤝 Convivencia y respeto
- 🌟 Responsabilidad
- 🎨 Actividades y talentos
- ✏️ Otro motivo

Si el usuario creó **motivos personalizados** (en Ajustes > Gestionar motivos), aparecen automáticamente en una sección compacta **"⭐ Mis motivos"** debajo del grid principal.

### Likes (👍)
- Botón "Dar like" abre el selector rápido
- Al elegir un motivo, se pide confirmar con autor (mamá/papá/ambos) y comentario opcional
- Los motivos personalizados también están disponibles como tarjetas

### Mejoras (🩹)
- Botón "Marcar mejora" registra una conducta a trabajar
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

El discriminador `APP_NAMESPACE` detecta la URL en runtime:
- Producción (`/likes-en-casa/`): claves originales
- Preview (`/likes-en-casa-preview/`): claves con namespace (`preview:***` y `likes_en_casa_db_preview`)

Esto permite que ambas URLs compartan origen sin colisionar datos.

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

## Repos relacionados

- Producción: https://github.com/CapiniMX/likes-en-casa
- Preview: https://github.com/CapiniMX/likes-en-casa-preview
- Respaldo histórico: https://github.com/piztian/likes-en-casa

## Tags de respaldo

- `v2.0-stable` — antes del merge v3.0 (catálogo, 3 estados, Logros)
- `v3.0-pre-selector` — antes del merge v3.1 (selector simplificado)

## Decisiones definitivas (no se modifican)

- **Sincronización entre dispositivos:** **DESCARTADA por decisión del usuario.** Cada quien mantiene sus registros locales. No es una feature futura.
- **Nuevas funcionalidades:** **Esta aplicación está cerrada.** Solo se aceptan correcciones de seguridad y bugs críticos. No se agregan features nuevas.
- **Procedimiento de rollback:** Se prioriza `git revert <commit>` + `git push capinimx main`. No se usa `--force` ni `--force-with-lease` en producción.

## Changelog

### v3.1 (2026-10-11) — commit 199e268
- ⚡ Selector rápido: 7 motivos generales + Otro motivo en grid 2x4
- ⭐ Sección "Mis motivos" que muestra motivos personalizados activos
- Sin barra de categorías ni buscador en el selector rápido
- Modal más compacto, tarjetas más pequeñas
- Compatibilidad total con datos v3.0 existentes

### v3.0 (commit a4bbccc) — v3.0-pre-selector
- 👍 Like con catálogo de 18 motivos
- 🩹 Mejora pendiente con emoji de curita
- ❤️ Subsanada con autor y comentario
- 🏆 Mis Logros con tabs Directos/Superados y podio
- 📸 Editor de fotos simplificado
- 🔒 Subsanar como botón visible
- 🔄 Compatibilidad con datos v2.0

### v2.0 (commit 568485c) — v2.0-stable
- Editor de fotos con 3 acciones
- Compresión automática de imágenes
- Almacenamiento en IndexedDB

### v1.0 (publicada en piztian)
- Versión inicial con likes, dislikes, categorías, PIN
