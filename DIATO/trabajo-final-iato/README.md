# Trabajo Final IA-TO — Sección 6 (Caso Plantium)

> Versiones iterativas de la **Sección 6 — Análisis de proveedores y costos** del Trabajo Final de la Diplomatura en IA aplicada a Transformaciones Organizacionales (DIATO, UNRaf 2026).
>
> **Responsable**: Javier Zader.

## Evolución del documento

La sección pasó por tres iteraciones con multi-voice review (Sonnet + Codex CLI + Opus + Codex gpt-5.5) entre cada versión.

### v1 — Original (25 KB, 270 líneas)

[seccion-6-v1-original.md](seccion-6-v1-original.md)

Primera redacción coherente con Sec 5 (Nadia, arquitectura) y Sec 8 (Magdalena, KPIs+ROI). Contiene los 7 componentes del stack, CAPEX/OPEX inicial y ROI alineado con Magdalena.

**Limitaciones detectadas en review** (29 findings F1-F29):

- Sin matriz de scoring para los criterios
- ROI sin descontar OPEX
- Brecha 70% automatización vs 55% ahorro sin explicar
- Mix LLM 80/20 inconsistente con OPEX
- Contingencia mal calculada (12,5% vs 15% declarado)
- Sin análisis fiscal AR ni sensibilidad de volumen
- Faltan tablas para copiloto, embeddings, cumplimiento legal

### v2 — Refactor (49 KB, 463 líneas)

[seccion-6-v2-refactor.md](seccion-6-v2-refactor.md)

Aplica los 29 findings F1-F29. Agrega 8 subsecciones nuevas:

- 6.1.1 Definiciones operativas
- 6.1.2 Glosario técnico
- 6.4.8 Copiloto interno
- 6.4.9 Cumplimiento Ley 25.326
- 6.4.10 TCO comparativo
- 6.6.6 Carga fiscal AR
- 6.6.7 Análisis de sensibilidad

**Limitaciones detectadas en segundo review** (Opus + Codex gpt-5.5):

- Fiscalidad AR: tabla extranjero/local INVERTIDA
- Sensibilidad: cálculos no derivan de la regla declarada
- FTE confunde capacidad bruta con costo-equivalente
- WhatsApp pricing 2026 desactualizado (Meta migró a per-mensaje desde julio 2025)
- Matrices scoring incompletas (5 componentes sin matriz)

### v3 — FIX 2.0 + Reestructura (64 KB, 672 líneas) ✅ FINAL

[seccion-6-v3-fix2-final.md](seccion-6-v3-fix2-final.md)

Aplica los 5 fixes críticos detectados en v2 + reestructura el documento en cuerpo principal + anexos.

**Estructura**:

- **Cuerpo principal (6.1-6.9)** — ~365 líneas, contundente y legible
- **Anexo A** — Análisis comparativo detallado por componente (A.1-A.9) con matrices scoring de todos los componentes
- **Anexo B** — Carga fiscal AR corregida (B.1) + Sensibilidad recalculada (B.2)
- **Anexo C** — Cumplimiento Ley 25.326 con DPA reformulado

**Cifras finales corregidas**:

| Métrica | Valor |
|---------|------:|
| CAPEX detallado | USD 45.425 |
| CAPEX referencia Sección 8 | USD 50.000 |
| OPEX nominal mensual | USD 2.308 |
| OPEX nominal anual | USD 27.696 |
| OPEX efectivo AR (con carga fiscal) | USD 32.304 |
| ROI sobre CAPEX | 137,6% |
| ROI sobre inversión total año 1 | 52,9% |
| ROI con carga AR | 44,3% |
| Payback bruto | 5,05 meses |
| Payback neto nominal | 6,59 meses |
| Payback con carga AR | 6,94 meses |
| TCO 3 años nominal | USD 124.928 |
| TCO 3 años con carga AR | USD 138.752 |

**Hallazgos clave de v3**:

1. WhatsApp Meta migró a per-mensaje desde julio 2025. Para Plantium (customer-initiated post-venta), la mayoría de mensajes caen en service window gratuita → modelo más favorable que el per-conversation anterior.
2. Pico estacional de cosecha MEJORA el ROI (no lo empeora) — el ahorro escala más rápido que el OPEX.
3. Carga fiscal AR impacta solo +11% sobre el TCO 3 años (no +25% como sugerían números previos) — 2/3 del OPEX es local.

## Próximos pasos

- Coordinar con **Magdalena (Sec 8)** la reconciliación del ROI (137,6% sobre CAPEX vs 44,3% con carga AR)
- Coordinar con **Nadia (Sec 5)** que la arquitectura del stack coincida con lo cerrado en el Anexo A
- Validar con **Lourdes (Sec 1)**: ¿Plantium tiene Microsoft 365? ¿CRM cloud-native o legacy?
- Coordinar con **Santiago (Sec 7)**: el cronograma debe absorber CAPEX en 3-6 meses, no día 1

## Material de referencia

- TPI completo: `../TPI_5tacohorte-1.pdf`
- Trabajo Final V2.docx: `../Trabajo final Diplomatura IA-TO V2.docx`
- Borrador previo (.docx 1): `../Trabajo final Diplomatura IA(1).docx` — fuente de material reutilizable
- Estudio DIATO completo: `../estudio/` — referencias cruzadas a caps 07 (procesos), 08 (arquitectura), 09 (automatización), 11 (legal), 16 (frameworks)

---

*Documento en curso. NO compartir hasta entrega final (16/06/2026).*
