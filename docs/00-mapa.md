# Mapa del sistema
Última actualización: 2026-10-27 · Paso 1.1 · base fija confirmada (el dueño no quitó ninguna, 2026-10-27)

## Base fija ✅ CRITERIO (criterio-uniline con C1–C6; confirmada sin quitar)
| Tabla | Para qué | Por qué entra | Certeza |
|---|---|---|---|
| grupos | Cliente del SaaS (dueño con varias razones sociales); plan y consolidado | D-001 + D-003 | ✅ CRITERIO |
| empresas | Cada razón social: RFC, régimen, CP, logo, colores, configuración fiscal | D-001, D-004 | ✅ CRITERIO |
| sucursales | Sedes; filtro de datos, series y folios | D-003 | ✅ CRITERIO |
| usuarios | Perfil ligado a Supabase Auth: nombre, foto, teléfono, activo | siempre | ✅ CRITERIO |
| roles | Dueño, administrador, contador, responsable de área/sucursal (seed editable) | D-002, CR-08 | ✅ CRITERIO |
| usuarios_empresa | Qué usuario, en qué grupo/empresa/sucursal, con qué rol | D-002, D-003 | ✅ CRITERIO |
| permisos | Por vista y por acción (ver, crear, editar, cancelar, autorizar) por rol | D-002, CR-08 | ✅ CRITERIO |
| configuracion | Parámetros por empresa (periodos, límites de autorización, textos) | siempre | ✅ CRITERIO |
| folios | Consecutivo por empresa/sucursal/serie (CFDI emitidos) | D-004, CR-11 | ✅ CRITERIO |
| bitacora | Quién hizo qué y cuándo en acciones importantes | siempre | ✅ CRITERIO |
| archivos | XML, PDF y fotos de comprobantes en Storage | D-004, D-005 | ✅ CRITERIO |
| notificaciones | Avisos en la app (autorizaciones, vencimientos, errores de sincronización) | D-005 | ✅ CRITERIO |

## Entidades de negocio 🟡 (de H-01…H-06; se definen en 2.1, no son diseño aprobado)
| Entidad | Para qué | Historia |
|---|---|---|
| cuentas (bancarias/caja) | Bancomer, otras cuentas y efectivo | H-01, H-04 |
| movimientos (ingreso/egreso) | Lo que entra y sale del banco o caja | H-01…H-04 |
| ventas | Lo que se vendió / se debe cobrar | H-01, H-02 |
| gastos | Lo que se compró / se debe pagar | H-03, H-04 |
| aplicaciones | Asocia movimientos con ventas o gastos (uno a varios, parcialidades) | H-01…H-04 |
| pagos programados | Compromisos con fecha y monto | H-05 |
| costos fijos (recurrentes) | Plantillas que generan pagos programados cada periodo | H-06 |
