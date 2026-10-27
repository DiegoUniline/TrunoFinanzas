# Mapa del sistema
Última actualización: 2026-10-27 · Paso 0.4 base fija (propuesta, pendiente de confirmar)

## Base fija 💡 PROPUESTO (criterio-uniline con C1–C6)
| Tabla | Para qué | Por qué entra | Certeza |
|---|---|---|---|
| grupos | Cliente del SaaS (dueño con varias razones sociales); plan y consolidado | D-001 + D-003 | 💡 |
| empresas | Cada razón social: RFC, régimen, CP, logo, colores, configuración fiscal | D-001, D-004 | 💡 |
| sucursales | Sedes; filtro de datos, series y folios | D-003 | 💡 |
| usuarios | Perfil ligado a Supabase Auth: nombre, foto, teléfono, activo | siempre | 💡 |
| roles | Dueño, administrador, contador, responsable de área/sucursal (seed editable) | D-002, CR-08 | 💡 |
| usuarios_empresa | Qué usuario, en qué grupo/empresa/sucursal, con qué rol | D-002, D-003 | 💡 |
| permisos | Por vista y por acción (ver, crear, editar, cancelar, autorizar) por rol | D-002, CR-08 | 💡 |
| configuracion | Parámetros por empresa (periodos, límites de autorización, textos) | siempre | 💡 |
| folios | Consecutivo por empresa/sucursal/serie (CFDI emitidos) | D-004, CR-11 | 💡 |
| bitacora | Quién hizo qué y cuándo en acciones importantes | siempre | 💡 |
| archivos | XML, PDF y fotos de comprobantes en Storage | D-004, D-005 | 💡 |
| notificaciones | Avisos en la app (autorizaciones, vencimientos, errores de sincronización) | D-005 | 💡 |
