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

### P-004 · general · ALTA · RESPONDIDA
**Contexto:** C4. Leer CFDI del SAT es la base para no pedir captura; emitir CFDI es otro producto (PAC, timbrado, cancelaciones).
**Pregunta:** Con las facturas, ¿la app solo las LEE (descarga del SAT) o también las EMITE (timbra)?
**Opciones:** A) Solo leer emitidas y recibidas del SAT  B) Leer y también emitir  C) Leer ahora y emitir en una rebanada posterior
**Recomendación:** A — no compite con el sistema de facturación o punto de venta que ya usan; esa competencia es justo la objeción a evitar.
**Impacto en datos:** cfdi (XML, UUID, emisor, receptor, totales, impuestos, PUE/PPD, REP), resguardo de e.firma; si emite: PAC, folios, series, cancelación (cfdi-mexico).
**Respuesta:** B) Leer y también emitir; timbrado con API de Facturama (2026-10-27, texto del dueño: "si facturar desde ahi al sat usando api facurama")

### P-005 · general · ALTA · RESPONDIDA
**Contexto:** C5. Define prioridades de pantallas (escritorio vs móvil) y si se necesita trabajar sin internet.
**Pregunta:** ¿Desde dónde se usará principalmente?
**Opciones:** A) Computadora para administración + celular para dueño (tablero, aprobaciones, fotos de comprobantes)  B) Solo computadora  C) Principalmente celular
**Recomendación:** A — el administrador concilia y clasifica en escritorio; el dueño consulta y autoriza desde el celular. Sin modo sin conexión: todo depende de SAT/banco en línea.
**Impacto en datos:** diseño responsive, carga de comprobantes con cámara, notificaciones, aprobaciones móviles.
**Respuesta:** A) Computadora + celular, sin modo sin conexión (2026-10-27)

### P-006 · general · ALTA · RESPONDIDA
**Contexto:** C6. SaaS multiempresa (D-001), grupos con consolidado (D-003), miles de movimientos por empresa al mes, conexión a SAT, bancos, POS y Facturama (D-004).
**Pregunta:** ¿Con qué tecnología se construye?
**Opciones:** A) Supabase (Postgres + RLS + Edge Functions) + web React responsive  B) AppSheet + Google Sheets + Apps Script  C) Híbrido: Supabase como base de datos + AppSheet como interfaz
**Recomendación:** A — aislamiento real entre empresas con RLS, volumen de movimientos y conciliación que Sheets no aguanta, secretos (e.firma, CSD, Facturama) protegidos en el backend.
**Impacto en datos:** todo lo técnico.
**Respuesta:** A) Supabase + web React (2026-10-27)

### P-007 · ventas · ALTA · RESPONDIDA
**Contexto:** H-01/H-02. Clave para no pedir doble captura: de dónde sale la venta.
**Pregunta:** ¿De dónde viene la venta en la app?
**Opciones:** A) Se crea sola desde el CFDI emitido (Facturama o descargado del SAT) o se importa del punto de venta; captura manual solo si no hay ninguno  B) Siempre se captura en la app  C) Solo del punto de venta
**Recomendación:** A — si ya existe en otro lado, se lee; así no hay objeción.
**Impacto en datos:** ventas con origen (manual, cfdi, pos), referencia externa única por empresa para no duplicar.
**Respuesta:** A) Desde CFDI emitido o punto de venta; manual solo si no hay ninguno (2026-10-27)

### P-008 · gastos · ALTA · RESPONDIDA
**Contexto:** H-03/H-04. Mismo principio que D-007 para el lado de los gastos.
**Pregunta:** ¿De dónde viene el gasto en la app?
**Opciones:** A) Se crea solo desde el CFDI recibido descargado del SAT; si no hay factura, se captura con foto del comprobante (ticket, recibo)  B) Siempre se captura en la app  C) Solo de CFDI recibidos
**Recomendación:** A — la mayoría de gastos ya tienen CFDI; los que no (efectivo, sin factura) quedan con foto para justificar el egreso y marcados como no deducibles.
**Impacto en datos:** gastos con origen (cfdi, manual), deducible sí/no, archivo de comprobante, UUID único por empresa.
**Respuesta:** A, y además: se puede crear un gasto manual que sí será deducible y cuya factura llega después (2026-10-27, texto del dueño: "TAMBIEN PUEDO CREAR UN GASTO Y SI SER DEDUCIBLE LA FACTURA LA RECIBIRE DESPUES")

### P-009 · bancos · ALTA · ABIERTA
**Contexto:** H-01/H-04. Los movimientos del banco son la otra mitad que no debe capturarse.
**Pregunta:** ¿Cómo entran los movimientos del banco (Bancomer, etc.)?
**Opciones:** A) Conexión automática con el banco mediante un agregador (Belvo/Syncfy), costo por cuenta conectada  B) Importar el estado de cuenta (Excel/CSV/OFX) que se descarga de la banca en línea  C) Importar en la primera versión y conexión automática después; captura manual siempre disponible (efectivo/caja)
**Recomendación:** C — la importación funciona con cualquier banco sin costo por cuenta; la conexión automática se agrega cuando haya clientes que la paguen.
**Impacto en datos:** movimientos con origen (manual, importacion, conexion), id/hash externo único por cuenta para no duplicar al reimportar; lotes de importación; credenciales del agregador en backend.
**Respuesta:**
