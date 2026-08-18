# Contenido de esta carpeta

## Qué versión producen estas fuentes

Los archivos `.tex` de esta carpeta generan **`ERS_v1.1.pdf`**, que es la versión final del ERS del
SIMPA. Compilarlos produce exactamente ese PDF: 106 páginas.

`ERS_v1.0.pdf` **no se genera desde estas fuentes**. Es el documento de la Entrega 2A, el que se
sometió a la inspección formal de la Unidad IV y con el que se comparan las correcciones de la §5 del
informe PE4. Se conserva como artefacto histórico.

## Dónde están las fuentes de la v1.0

En el historial de Git, etiquetadas. No se duplican en una carpeta paralela: mantener dos copias de
los mismos archivos es precisamente el mecanismo que produjo los once defectos de consistencia que la
inspección detectó en este documento.

Para recuperarlas:

```bash
git checkout ers-v1.0 -- 01_ERS/     # trae las fuentes de la v1.0 al directorio de trabajo
git checkout HEAD -- 01_ERS/         # vuelve a las fuentes vigentes
```

O para consultar un archivo concreto sin modificar nada:

```bash
git show ers-v1.0:01_ERS/ERS_SRS_2A_v1.0.tex | less
```

## Archivos

| Archivo | Contenido | Incorporado en |
|---|---|---|
| `ERS_SRS_2A.tex` | **Archivo principal.** Preámbulo, portada, historial de revisiones, §1 a §3 y llamadas al resto | — |
| `seccion4_uml.tex` | §4 Modelado UML e i*. Carga `cu_11_18.tex` | — |
| `seccion5_priorizacion.tex` | §5 Priorización MoSCoW, Kano, WSJF y matriz de trazabilidad | — |
| `seccion6_7_mvp_conclusiones.tex` | §6 Prototipo mínimo viable y §7 conclusiones | — |
| `seccion8_dfd.tex` | §8 Diagramas de flujo de datos, en TikZ | PE5 |
| `seccion9_ia.tex` | §9 Componentes de inteligencia artificial | PE5 |
| `cu_11_18.tex` | Especificación de `CU-11` a `CU-18` | PE5 |
| `apendice_bdd.tex` | Apéndice F, criterios `CB-01` a `CB-37` | PE5 |
| `apendices.tex` | Apéndices A a E. Carga `apendice_bdd.tex` | — |
| `referencias.bib` | Bibliografía en formato BibTeX | — |
| `img/` | 14 figuras en PDF vectorial | — |

Los archivos cargados por `\input` **no compilan por separado**. El único archivo que se compila es
`ERS_SRS_2A.tex`.

## Cómo compilar

```bash
pdflatex ERS_SRS_2A
bibtex   ERS_SRS_2A
pdflatex ERS_SRS_2A
pdflatex ERS_SRS_2A
mv ERS_SRS_2A.pdf ERS_v1.1.pdf
```

Las tres pasadas de `pdflatex` son obligatorias: la primera genera el `.aux`, `bibtex` resuelve las
citas y las dos siguientes fijan el índice y las referencias cruzadas. Con menos pasadas aparecen
marcas `??` en el PDF.

Dependencias que no vienen en una instalación mínima de TeX Live: `texlive-lang-spanish`,
`texlive-publishers`, `texlive-science`, `texlive-pictures` y `texlive-latex-extra`. El documento
carga `babel` y el estilo `IEEEtran` de forma condicional, de modo que compila igual si faltan, con
partición silábica inglesa y estilo bibliográfico `unsrt`.

## Sobre la numeración de versiones

El ERS registra internamente sus revisiones desde la Entrega 1A y llegó a la Entrega 2A como
**revisión interna 3.0**. La asignatura designa a ese mismo documento como **v1.0**.

Se adopta la numeración de la asignatura como versión oficial. Para que la coexistencia no produzca
ambigüedad, el historial de revisiones del propio ERS rotula su columna como *revisión interna* y
declara la equivalencia:

| Numeración de la asignatura | Revisión interna |
|---|---|
| **v1.0** | 3.0 |
| **v1.1** | 3.1 |

Las revisiones internas 1.0, 1.1 y 2.0 que figuran en el historial corresponden a las Entregas 1A y
1B y **no** son las versiones v1.0 y v1.1 de la asignatura.

