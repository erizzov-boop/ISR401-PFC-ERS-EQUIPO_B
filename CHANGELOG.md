# Registro de cambios — ERS del SIMPA

Cambios de la Especificación de Requisitos de Software del **Sistema Inteligente de Mantenimiento de
Palma Africana (SIMPA)**.

El formato sigue las secciones `Añadido` / `Cambiado` / `Eliminado` exigidas por la guía de la PE4.
Cada entrada de la versión v1.1 corresponde a una solicitud formal de cambio (RFC) aprobada por el
Change Control Board, identificada con su código, o a la corrección de un defecto crítico o mayor
detectado en la inspección formal (identificadores `DEF-xx`).

La versión declarada aquí es la misma que consta en la portada del ERS, en su historial de
revisiones y en la etiqueta anotada de Git. Se emplea la numeración de la asignatura: `v1.0` es el
documento de la Entrega 2A y `v1.1` la versión resultante del CCB. Su equivalencia con las
revisiones internas del ERS (3.0 y 3.1) está declarada en la sección 5 del `README.md` y en el
propio ERS.

---

## [v1.1] — *(fecha del acta del CCB)*

Línea base aprobada por el CCB tras la inspección formal tipo Fagan de la PE4. Etiqueta de Git:
`baseline-v1.1`. Alcance inspeccionado: §1 a §7 (63 páginas efectivas). Registro completo de
defectos en `02_Inspeccion/AnexoB_registro_defectos.xlsx`; texto antes/después de cada corrección en
la §5 del informe.

### Añadido

- (DEF-02) Enumeración explícita de los 21 requisitos *Must* y de los 16 *Should* en la §5.3.1, más
  nota de corrección que documenta la contradicción resuelta.
- (DEF-09) Filas de `RF-36` y `RF-37` en la tabla de cobertura del MVP, de los que faltaban por ser
  *Must* no contabilizados.
- (DEF-14) Ciclo de liquidación semanal (`RF-36` a `RF-39`) en la lista de funcionalidades
  principales de la §1.2.3.
- (DEF-17) Enumeración cerrada de los cuatro disparadores de alerta de `RF-12`.
- (DEF-18) Fórmula, componentes, pesos y escala del indicador de desempeño de `RF-16`.
- (DEF-19) Tolerancia del 20 % para la estimación de producción de `RF-18`.
- (DEF-22) Umbrales de calidad mínima de la imagen en la precondición de `RF-07`.
- (DEF-23) Cuantificación de la proximidad al umbral en `RF-22`: la alerta preventiva se dispara al
  80 % del umbral de penalización.
- (DEF-26) `RF-16`, `RF-17` y `RF-20` en la especificación textual de `CU-05`, más flujo alternativo
  C, para que la trazabilidad cierre en sentido inverso.
- (DEF-29) Fila 3.1 en el historial de versiones, que declara que la recolección de `EV-13` concluyó
  el 07/08/2026, con posterioridad al cierre de la v1.0.
- (DEF-30) Plan de construcción del conjunto etiquetado exigido por `RNF-01` y `RNF-02`, dentro del
  alcance de la versión.
- (DEF-31) Limitación `L-12`: el marco de siembra no está declarado, por lo que no puede afirmarse
  que la precisión GPS de `RNF-05` discrimine palmas contiguas.
- (RFC-01) Historias de usuario `HU-20` y `HU-21` con criterios de aceptación `CA-20` y `CA-21`
  para `RF-36` y `RF-37`. Restablece la cobertura *Must* con historia y criterio.
- (RFC-02) Requisito `RNF-19` (Seguridad física / *safety*): toda recomendación de control
  fitosanitario incluye de forma no omisible el equipo de protección personal y el intervalo de
  reingreso al lote. Eleva los RNF de 18 a 19.
- (RFC-03) Requisitos `RF-40` (exportación de datos personales por la titular, Art. 12), `RF-41`
  (rectificación con bitácora, Art. 13) y `RF-42` (supresión con disociación del histórico
  productivo, Art. 14), con sus historias `HU-22` a `HU-24` y las filas `TR-53` a `TR-55` de la
  matriz. Eleva los RF de 39 a 42 y los *Must* de 21 a 24.

### Cambiado

- (RFC-02) `RNF-17` se reclasifica de «Portabilidad» a «Flexibilidad (reemplazabilidad)» y `RNF-18`
  se precisa como «Flexibilidad (adaptabilidad)»: en ISO/IEC 25010:2023 Portabilidad dejó de ser
  característica de primer nivel.
- (RFC-03) `RL-04`, `RL-05` y `RL-06` pasan de enunciar la obligación a declarar el requisito
  funcional que la implementa.
- (RFC-03) Cobertura del MVP: se declara con dos denominadores, 38,1 % sobre los 21 *Must* vigentes
  al construir el prototipo y 33,3 % sobre los 24 posteriores al CCB.
- (DEF-01) §3: de «9 restricciones de diseño» a «10 restricciones de diseño».
- (DEF-03) Apéndice C: de «35 requisitos funcionales» a «39 requisitos funcionales».
- (DEF-04) Matriz de trazabilidad: de «48 filas» a «52 filas» en el Apéndice D y en la §7.1; el
  diccionario pasa de `TR-01`–`TR-48` a `TR-01`–`TR-52`.
- (DEF-05) §2.2: de «seis bloques» a «siete bloques», en coherencia con la §3.2.
- (DEF-06) Justificación de `RD-01`: se sustituye la suposición invalidada de que todo el personal
  dispone de teléfono inteligente por el dato real de `EV-12` (88,7 %), con remisión a `RD-10` y
  `RF-35` para el 11,3 % restante.
- (DEF-07) Justificación de `RD-02`: se corrige la afirmación de que nadie declaró señal permanente
  por el dato de la Tabla 7 (25,8 % sí la declara).
- (DEF-08) Catálogo de evidencias: `EV-13` deja de atribuirse el origen de `RF-29`, que su ficha
  declara en `EV-06` y `EV-07`.
- (DEF-09, DEF-33) Cobertura del MVP: denominador de 19 a 21 *Must*; se retiran `RF-15` y `RF-20`
  del numerador por ser *Should*. La cobertura declarada baja de 47,4 % a 38,1 % (42,9 %
  ponderada). Se actualizan en consecuencia la limitación `L-10` y el diagnóstico de cobertura de la
  §5.4.1.
- (DEF-10, DEF-11) §5.3.3: la Tabla 68 deja de presentarse como el ranking de los diez WSJF más
  altos y declara los tres requisitos omitidos con valor superior (`RF-10`, `RF-05`, `RF-30`).
- (DEF-15) Limitación `L-06`: se declara el número efectivo de sesiones de *walkthrough*.
- (DEF-20) `RNF-10`: de «≤ 7 h 18 min» a «≤ 7 h 12 min», que es el equivalente correcto de una
  disponibilidad del 99 % mensual.
- (DEF-21) `RNF-03`: de 50 a 20 sesiones concurrentes, derivadas de la población de 62 personas y
  del 25,8 % con señal permanente.
- (DEF-24) `RF-25`: el valor de la ventana corte-entrega se declara atributo de la variedad,
  gestionado por `RF-10`, en lugar de un «valor recomendado» sin tabular.
- (DEF-27) Tabla 9: el prototipo `MU-02` pasa a declarar también `RF-29` y `RF-36` a `RF-39`, en
  coherencia con la matriz.
- (DEF-28) §1.4: de «31 fuentes primarias» a «27», tras retirar las entradas nunca citadas.
- (DEF-31) `RF-14`: el conteo se acota a la agregación por línea de siembra y se excluye del alcance
  la asignación individual planta por planta.
- (DEF-32) Limitación `L-07`: se marca como resuelta en la v1.0 y se declara que no computa como
  limitación vigente.
- Portada: versión v1.0 → v1.1 (revisión interna 3.0 → 3.1). El historial del ERS rotula su columna como «Revisión interna» y declara la equivalencia con la numeración de la asignatura.

### Eliminado

- (DEF-33) Filas de `RF-15` y `RF-20` de la tabla de cobertura del MVP sobre requisitos *Must*: sus
  fichas de la §3.2 los clasifican como *Should*.

### No corregido

- (DEF-25, menor) `RF-09` sigue sin enumerar las etapas del ciclo del insecto. Requiere información
  entomológica ausente en las trece evidencias; consulta programada a la asesoría técnica antes de
  la Entrega 4. Justificación completa en la §5 del informe.

---

## [v1.0] — 2026-08-03

Entrega 2A (revisión interna 3.0). Versión sometida a inspección formal en esta práctica. Estado del documento antes de
cualquier cambio de la PE4.

### Añadido

- Segunda ronda de trabajo de campo con cinco participantes nuevos y una organización fuente
  adicional (evidencias `EV-04` a `EV-08`).
- Ampliación del catálogo a 39 requisitos funcionales y 18 no funcionales, estos últimos mapeados
  sobre las características del modelo de calidad de ISO/IEC 25010:2023.
- Requisito de explicabilidad de las decisiones automáticas (`RNF-16`) y caso de uso `CU-18`, que
  materializa la exigencia: los tres casos de uso con decisión automática lo incluyen de forma
  obligatoria.
- Mapeo de los 8 requisitos legales derivados de la LOPDP (`RL-01` a `RL-08`).
- 19 historias de usuario en formato Connextra con escenarios de aceptación en Gherkin
  (`HU-01`/`CA-01` a `HU-19`/`CA-19`).
- Modelado organizacional i* (diagramas SD y SR) y ciclo de liquidación semanal derivado de la
  evidencia `EV-13` (`RF-36` a `RF-39`).

### Cambiado

- Incorporación de las correcciones del informe docente de la Entrega 1B (detalladas en la §1.6 del
  propio ERS).
- Renumeración completa del catálogo de evidencias (detallada en la §1.7).
- Migración del documento desde procesador de texto a LaTeX, con fuentes versionadas en `01_ERS/`.

### Eliminado

- Nada. Esta versión acumula y reemplaza a las Entregas 1A y 1B sin retirar contenido.

---

## Revisiones internas previas

Las entradas siguientes son revisiones internas del ERS anteriores a la Entrega 2A. **No** son las
versiones v1.0 y v1.1 de la asignatura, pese a la coincidencia de los números.

- **Rev. interna 2.0 — 2026-06-26.** Entrega 1B: requisitos específicos, modelado UML, priorización
  MoSCoW y matriz de trazabilidad parcial.
- **Rev. interna 1.1 — 2026-06-23.** Correcciones docentes de la Entrega 1A: diagrama de contexto,
  actas formales y trazabilidad de requisitos brutos.
- **Rev. interna 1.0 — 2026-06-01.** Elaboración inicial de la Entrega 1A: planificación y
  elicitación.
