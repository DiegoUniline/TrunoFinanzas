# Historias
(De "cuéntame cómo trabajas") · Fuente: dueño, 2026-10-27

## Proceso: ingresos (cobros)
- H-01 · Como administrador quiero que entre un ingreso al banco (ej. Bancomer) y después asociarlo a una o varias ventas para saber qué se cobró. ✅
- H-02 · Como administrador quiero registrar una venta y después registrarle su ingreso (cobro) para saber qué falta por cobrar. ✅

## Proceso: egresos (pagos)
- H-03 · Como administrador quiero registrar un gasto y después ponerle su egreso del banco para saber qué está pagado. ✅
- H-04 · Como administrador quiero que salga un egreso del banco y después asociarlo a un gasto para que nada quede sin justificar. ✅ (simétrico de H-01, dicho como "como Bancomer")

- H-07 · Como administrador quiero crear un gasto deducible cuya factura llega después y ligarle el CFDI cuando lo descargue, para no duplicarlo ni perder la deducción. ✅

## Proceso: pagos programados y costos fijos
- H-05 · Como administrador quiero programar pagos (fecha y monto) para saber qué viene y no olvidar ninguno. ✅
- H-06 · Como administrador quiero dar de alta costos fijos (renta, nómina, servicios) que se repitan solos cada periodo. ✅

## Detectado sin detallar (🟡 se pregunta después)
- Un ingreso puede cubrir varias ventas y una venta puede cobrarse en varios ingresos (parcialidades) → relación de aplicaciones.
- Movimientos del banco que no son venta ni gasto: traspasos entre cuentas o entre empresas del grupo, comisiones, préstamos, impuestos.
- Origen de la venta: desde CFDI emitido o punto de venta; manual solo si no hay (D-007).
- Origen del gasto: desde CFDI recibido o manual con foto (D-008).
- Cómo entran los movimientos del banco: (P-009)
