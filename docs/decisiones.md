# Decisiones

### D-001 · general · 2026-10-27
**Decisión:** La app es un SaaS que se renta a muchas empresas.
**Origen:** P-001
**Consecuencias:** empresa_id + RLS en todas las tablas de negocio (CR-16), catálogos configurables por empresa (CR-03/CR-05), permisos configurables (CR-08), unicidad por empresa (CR-14), folios por empresa (CR-11).

### D-002 · general · 2026-10-27
**Decisión:** Usuarios por empresa variable (1 a 15+); roles y permisos configurables por empresa.
**Origen:** P-002
**Consecuencias:** CR-08: tablas roles, permisos (vista + acción) con valores iniciales; usuarios_empresa.

### D-003 · general · 2026-10-27
**Decisión:** Estructura grupo → empresas (razones sociales) → sucursales, con vista consolidada del grupo.
**Origen:** P-003
**Consecuencias:** tabla de grupos (organización/cliente del SaaS) sobre empresas; sucursal_id; usuarios con acceso a varias empresas y sucursales; traspasos y préstamos entre empresas del grupo; reportes consolidados que eliminan movimientos internos.

### D-004 · general · 2026-10-27
**Decisión:** La app lee CFDI (emitidos y recibidos) y además emite/timbra CFDI usando la API de Facturama.
**Origen:** P-004
**Consecuencias:** aplica skill cfdi-mexico: datos fiscales por empresa (RFC, régimen, CP, CSD), clientes con datos de receptor, series y folios por empresa (CR-11), impuestos explícitos (CR-12), cancelación con motivo SAT, notas de crédito, complemento de pago (REP); credenciales de Facturama y CSD como secretos solo en backend. Rebanada en la que entra la emisión: ❓ por definir en 1.3.

### D-005 · general · 2026-10-27
**Decisión:** Uso en computadora (administración, conciliación) y celular (dueño: tablero, autorizaciones, fotos de comprobantes). Sin modo sin conexión.
**Origen:** P-005
**Consecuencias:** diseño responsive con prioridad escritorio para conciliación y móvil para tablero y aprobaciones (mobile-ux-architect); carga de comprobantes con cámara; notificaciones.

### D-006 · general · 2026-10-27
**Decisión:** Tecnología: Supabase (Postgres, Auth, RLS, Storage, Edge Functions) + web React responsive.
**Origen:** P-006
**Consecuencias:** convenciones Postgres de la constitución; RLS por empresa en todas las tablas; integraciones SAT, banco, POS y Facturama en Edge Functions con secretos en el backend; operaciones de varios pasos en RPC transaccional.
