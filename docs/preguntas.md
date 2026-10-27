# Preguntas

### P-001 · general · ALTA · RESPONDIDA
**Contexto:** define multiempresa, catálogos configurables, permisos y seed (C1).
**Pregunta:** ¿La app se renta a muchas empresas (SaaS) o es para empresas propias/de un cliente?
**Opciones:** A) SaaS para rentar  B) Empresas propias (grupo)  C) Ambas: propias primero, luego rentar
**Recomendación:** A — el requisito "sin objeción" es de producto comercial.
**Impacto en datos:** empresa_id en todas las tablas, RLS, permisos configurables (CR-08), catálogos por empresa (CR-03).
**Respuesta:** A) SaaS para rentar (2026-10-27)

### P-002 · general · ALTA · RESPONDIDA
**Contexto:** C2. Define si los permisos y roles se configuran por empresa.
**Pregunta:** ¿Cuántas personas por empresa la usarán y con qué roles?
**Opciones:** A) 1–3 (dueño + administrador + contador)  B) 4–15 con responsables de área o sucursal  C) Variable, desde 1 hasta más de 15
**Recomendación:** C — en un SaaS cada empresa trae un tamaño distinto; los permisos se configuran (CR-08).
**Impacto en datos:** roles y permisos por vista y acción, flujo de aprobación de gastos.
**Respuesta:** C) Variable, de 1 a 15+ (2026-10-27)

### P-003 · general · ALTA · RESPONDIDA
**Contexto:** C3. Define sucursal_id, consolidados y si un usuario ve varias empresas.
**Pregunta:** ¿Un mismo dueño puede tener varias empresas (razones sociales) y/o sucursales que quiera ver juntas?
**Opciones:** A) Sí: grupo con varias empresas y sucursales, con vista consolidada  B) Solo sucursales dentro de una empresa  C) Una empresa sin sucursales
**Recomendación:** A — es común que un dueño tenga varias razones sociales; el consolidado es un valor que ningún sistema de punto de venta da.
**Impacto en datos:** tabla de grupos/organización sobre empresas, sucursal_id, traspasos entre empresas, usuarios con acceso a varias empresas.
**Respuesta:** A) Grupo con varias empresas y sucursales, vista consolidada (2026-10-27)

### P-004 · general · ALTA · ABIERTA
**Contexto:** C4. Leer CFDI del SAT es la base para no pedir captura; emitir CFDI es otro producto (PAC, timbrado, cancelaciones).
**Pregunta:** Con las facturas, ¿la app solo las LEE (descarga del SAT) o también las EMITE (timbra)?
**Opciones:** A) Solo leer emitidas y recibidas del SAT  B) Leer y también emitir  C) Leer ahora y emitir en una rebanada posterior
**Recomendación:** A — no compite con el sistema de facturación o punto de venta que ya usan; esa competencia es justo la objeción a evitar.
**Impacto en datos:** cfdi (XML, UUID, emisor, receptor, totales, impuestos, PUE/PPD, REP), resguardo de e.firma; si emite: PAC, folios, series, cancelación (cfdi-mexico).
**Respuesta:**
