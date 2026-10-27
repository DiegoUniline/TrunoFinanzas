# Investigación: finanzas corporativas para PyMEs (con y sin punto de venta) — 2026-10-27
> Todo lo de aquí es 🟡 hasta que el dueño lo confirme para SU producto.

## Resumen (5 líneas)
- Las PyMEs ya registran su dinero en 3–5 lugares: POS/sistema de ventas, banco, SAT (CFDI emitidos y recibidos), hojas de Excel y el contador (CONTPAQi, Aspel, etc.).
- Nadie tiene la vista consolidada: flujo de efectivo real, rentabilidad por unidad de negocio, cuentas por cobrar/pagar y proyección.
- La objeción "ya lo llevo en mi sistema" se resuelve **no pidiendo captura**: el sistema LEE de donde el dato ya existe (CFDI del SAT, banco, POS, exportaciones) y solo pide clasificar/aprobar.
- El mercado mexicano va hacia conexión bancaria automática (CONTPAQi + Banorte, 2024–2026) y agregadores open finance (Belvo, Syncfy).
- Herramientas internacionales de flujo (Float, Fathom, Pulse) dependen de un contable (Xero/QuickBooks) y no integran POS directamente: ese hueco existe.

## Cómo opera (flujo típico)
1. Se vende (POS, facturación o cobro directo) → entra dinero al banco/caja.
2. Se compra/gasta (proveedores, nómina, servicios, caja chica) → CFDI recibido + salida bancaria.
3. Cada mes el contador concilia banco vs CFDI y genera pólizas/declaraciones.
4. El dueño decide con saldo bancario del día y "le alcanza o no", sin proyección.

## Roles
Dueño/director · Administrador/finanzas · Contador (interno o externo) · Responsables de área/sucursal (solicitan o justifican gastos).

## Documentos y formatos
CFDI ingreso/egreso/pago (complemento de pagos) · estado de cuenta bancario (PDF, CSV, OFX, API) · cortes de caja del POS · presupuesto anual · nómina (CFDI nómina).

## Dinero
Ingresos: contado, crédito a clientes (CxC), terminales/pasarelas (comisiones, depósitos netos y diferidos). Egresos: proveedores a crédito (CxP), nómina, impuestos, financiamientos, gastos fijos/variables. Traspasos entre cuentas y entre empresas del mismo dueño.

## Regulación aplicable
| Norma | Qué exige | Impacto en datos | Fuente |
|---|---|---|---|
| CFF art. 28–30 / Anexo 24 RMF | Contabilidad electrónica y conservación 5 años | Guardar UUID/XML y relación con movimientos | 🟡 sin verificar en esta sesión |
| CFDI 4.0 / complemento de pagos | PPD requiere complemento al cobrar/pagar | Saldos de CxC/CxP derivados de CFDI + REP | 🟡 sin verificar |
| Descarga masiva SAT (web service con e.firma) | Acceso a XML emitidos y recibidos | Guardar e.firma de forma segura (secreto) | 🟡 sin verificar |
| LFPDPPP | Protección de datos | Datos de clientes/empleados, aviso de privacidad | 🟡 sin verificar |
| Ley Fintech / open finance (CNBV) | Reglas para agregación bancaria | Usar proveedor autorizado, no scraping propio | 🟡 sin verificar |

## Glosario
| Término | Significado |
|---|---|
| Flujo de efectivo | Entradas y salidas reales de dinero en un periodo |
| Conciliación bancaria | Empatar movimientos del banco con documentos (CFDI, ventas, gastos) |
| CxC / CxP | Cuentas por cobrar / por pagar |
| PUE / PPD | CFDI pagado en una exhibición / en parcialidades o diferido |
| REP | Recibo electrónico de pago (complemento de pagos) |
| Centro de costos / unidad de negocio | Agrupador para medir gasto/rentabilidad por área, sucursal o proyecto |
| Proyección (forecast) | Flujo esperado a futuro con compromisos y supuestos |

## Software líder
| Sistema | Fuerte en | Quejas frecuentes | Precio aprox | Fuente |
|---|---|---|---|---|
| CONTPAQi (+Conecta tu banco) | Contabilidad, conciliación bancaria MX | Pensado para contador, no para dueño | ❓ | [CONTPAQi/Banorte](https://www.cronista.com/mexico/finanzas-economia/banorte-y-contpaqi-se-alian-para-que-las-pymes-integren-banca-y-contabilidad-en-tiempo-real/) |
| Bind ERP | ERP PyME MX | Sincronizaciones intermitentes, subidas de precio | ❓ | [Capterra](https://www.capterra.com/p/190643/bind-erp/reviews/) |
| Alegra | Facturación + POS + contable LatAm | Pocas reseñas | ❓ | [Capterra](https://www.capterra.es/software/196363/alegra-erp) |
| Float / Fathom / Pulse | Flujo y proyección | Dependen de Xero/QuickBooks, sin POS | ❓ | [Float](https://floatapp.com/product) |

## Dolores frecuentes → oportunidad
- Doble captura → importar/leer, no capturar.
- Conciliación manual al mes → conciliación diaria sugerida automáticamente.
- Dinero del POS no cuadra con el banco (comisiones, depósitos diferidos) → conciliación POS↔banco.
- No saber si alcanza para la quincena → proyección a 13 semanas con CxC/CxP.
- Gastos sin dueño ni presupuesto → centros de costo y presupuesto vs real.

## Volúmenes típicos (para escalabilidad)
❓ No investigado con fuente. Supuesto a validar: 200–5,000 movimientos bancarios/mes y 100–3,000 CFDI/mes por empresa PyME.

## Integraciones típicas
SAT (descarga masiva CFDI) · bancos vía agregador ([Belvo](https://www.latamfintech.co/articles/fintech-belvo-supero-los-10-millones-de-cuentas-conectadas-a-traves-del-open-finance-en-latam), [Syncfy](https://www.bloomberglinea.com/2022/12/08/syncfy-cierra-ronda-semilla-por-us10-millones-para-su-negocio-de-open-finance/)) o importación de estado de cuenta · POS (API o exportación CSV) · contables (CONTPAQi/Aspel exportación) · terminales (Clip, Mercado Pago, etc.).

## Preguntas que esto me genera para el dueño
- ¿Es SaaS para rentar o para empresas propias? (C1)
- ¿Por dónde entra el dato: SAT, banco, POS, Excel? ¿Cuál primero?
- ¿El POS es tuyo (propio) o de terceros?
- ¿Usuario principal: dueño, administrador o contador?
- ¿Multiempresa por dueño (grupo de empresas, consolidado)?
- ¿Sustituye al contable o convive con él?

## Fuentes
- https://www.cronista.com/mexico/finanzas-economia/banorte-y-contpaqi-se-alian-para-que-las-pymes-integren-banca-y-contabilidad-en-tiempo-real/
- https://portalerp.com/mx/noticia/contpaqi-y-banorte-buscan-eficientar-la-gestion-fiscal-y-contable-en-las-pymes-de-mexico
- https://www.capterra.com/p/190643/bind-erp/reviews/
- https://www.capterra.es/software/196363/alegra-erp
- https://floatapp.com/product
- https://www.latamfintech.co/articles/fintech-belvo-supero-los-10-millones-de-cuentas-conectadas-a-traves-del-open-finance-en-latam
- https://www.bloomberglinea.com/2022/12/08/syncfy-cierra-ronda-semilla-por-us10-millones-para-su-negocio-de-open-finance/
