# Decisiones

### D-001 · general · 2026-10-27
**Decisión:** La app es un SaaS que se renta a muchas empresas.
**Origen:** P-001
**Consecuencias:** empresa_id + RLS en todas las tablas de negocio (CR-16), catálogos configurables por empresa (CR-03/CR-05), permisos configurables (CR-08), unicidad por empresa (CR-14), folios por empresa (CR-11).

### D-002 · general · 2026-10-27
**Decisión:** Usuarios por empresa variable (1 a 15+); roles y permisos configurables por empresa.
**Origen:** P-002
**Consecuencias:** CR-08: tablas roles, permisos (vista + acción) con valores iniciales; usuarios_empresa.
