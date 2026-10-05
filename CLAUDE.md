# CLAUDE.md

## 1. Qué es este repo

Un vault de Obsidian que funciona como resumen de estudio para el **primer parcial de H209 -
Escritura y Oratoria** (UdeSA, 2do semestre 2026, Teórica 3, Mariana McLoughlin). Las páginas
las escribe y mantiene Claude, ancladas estrictamente al material de `raw/`.

No es un proyecto de software: no hay build, lint ni tests. El entregable son páginas Markdown
navegables desde Obsidian y útiles para estudiar. Todo el contenido se escribe en **español
(registro académico rioplatense)**.

El parcial cubre las **Unidades 1 a 4** del programa. El racional de diseño está en
[[DESIGN|DESIGN.md]].

## 2. Estructura

```
raw/                         ← fuentes, solo lectura; cada archivo con su conversión .md al lado
  index.md                   ← mapa fuente → tema → página de la wiki
  Programa/                  ← programa, cronogramas, guía de estudio del primer parcial
  Bibliografía/Obligatoria/  ← lo que entra al parcial
  Bibliografía/Consulta/     ← complementos; nunca la única fuente de una definición de examen
  Diapositivas/              ← PPT de las teóricas
  Ejercitación/              ← cuadernillo, resoluciones, monografía modelo, textos de trabajo
  Normativa/                 ← guías de normativa, código y criterios de corrección
  Cuestionarios/             ← cuestionarios del campus exportados (preguntas, respuestas, devoluciones)
  Transcripciones/           ← teóricas grabadas, "Clase N - AAAA-MM-DD.md"

wiki/                        ← contenido gestionado por Claude, un módulo por carpeta
  1. Teoría/                 ← una página por eje teórico (template A)
  2. Corpus/                 ← la monografía modelo analizada (template B)
  3. Preguntas/              ← preguntas de la guía e integradoras, con respuesta escrita (template C)
  4. Práctica/               ← ejercicios tipo del cuadernillo resueltos (template D)
  5. Examen/                 ← cómo escribir la respuesta, normativa y glosario (template E)
  Cada módulo contiene <Módulo>.md (overview, template F), con el mismo nombre que la
  carpeta sin número.

Escritura.md                 ← home: formato del parcial, recorrido y catálogo
log.md                       ← bitácora append-only
```

Las transcripciones son de las teóricas de los jueves: Clase 1 (presentación), 2 (proceso de
escritura, texto, adecuación y coherencia), 3 (cohesión), 4 (repaso de cohesión), 5 (géneros
discursivos y "Continuidad de los parques"), 6 (géneros y monografía modelo), 7 (enunciación,
personas del discurso, nosotros, despersonalización) y 8 (repaso: despersonalización, ethos,
subjetivemas y preparación del parcial).

## 3. Reglas duras

1. **Anclaje a fuentes.** Cada sección de cada página se puede rastrear hasta una fuente citada
   en `## Fuentes`. Nada se inventa. Si un dato útil no está en `raw/`, se omite. La única
   excepción es la norma de la RAE en `Glosario.md` y `Normativa.md` cuando la cátedra no
   cubre un caso: va dentro de `> [!info] Complemento externo`, con la fuente nombrada.
2. **La clase manda.** La explicación de la profesora en las teóricas es la columna vertebral
   de cada página: su orden, sus definiciones, sus clasificaciones, sus nombres y sus
   ejemplos. La bibliografía aporta la formulación exacta del autor (en el examen se define
   con autor y año) y completa lo que en la transcripción no se entiende. Si clase y texto
   difieren, se sigue la clase.
3. **Transcripciones con pinzas.** Son reconocimiento automático de voz, con frases rotas,
   nombres deformados e inglés espurio. Un concepto se toma de la clase solo si el sentido se
   reconoce con claridad; ante un tramo confuso se omite el detalle o se completa con la
   bibliografía, nunca se reconstruye por inferencia. Nombres propios y términos técnicos se
   escriben como en la bibliografía, no como los deforma la transcripción. Las
   transcripciones nunca se citan textualmente en la prosa.
4. **`raw/` es de solo lectura.** La única excepción es `raw/index.md`.
5. **Wikilinks para navegar**: `[[Página|alias]]`. Nombres de archivo únicos en todo el vault:
   Obsidian resuelve por nombre sin mirar la carpeta.
6. **Prosa narrativa.** Oraciones completas unidas con conectores. Las listas y las tablas
   quedan para enumeraciones genuinas y clasificaciones.
7. **El vault practica lo que enseña.** Ortografía, tildes, puntuación y concordancia
   impecables; registro formal; sin gerundios de posterioridad. Las respuestas de
   `wiki/3. Preguntas/` se escriben exactamente como debe escribirse una respuesta de examen
   (ver template C).
8. **Cada oración sirve para estudiar.** El cuerpo no comenta de dónde sale un dato ("lo dijo
   la profesora", "la ficha no lo menciona"), ni el proceso del vault ("reconstruido",
   "observación propia"), ni divergencias que no cambian una respuesta de examen. Se escribe
   el dato correcto como hecho. Una divergencia se menciona solo cuando un alumno respondería
   distinto según la fuente que estudió, en una oración que dice qué usar. Las advertencias de
   examen ("en el parcial no definir género como conjunto") sí van.
9. **Sin emojis.** Estados en texto plano.
10. **Alcance.** Fuera del parcial: Unidades 5 a 7, oratoria, el corpus de IA de los
    tutoriales. Laca (modalización) se vio muy poco en clase: ocupa un párrafo dentro de
    `Subjetivemas.md`, nunca una página.

## 4. Frontmatter

```yaml
---
tipo: teoria | corpus | preguntas | practica | examen | modulo
estado: en-progreso | completo
fuentes:
  - raw/Transcripciones/Clase 7 - 2026-09-17.md
  - raw/Bibliografía/Obligatoria/Goethals y Delbecque - Personas del discurso y despersonalización.pdf
ultima_actualizacion: AAAA-MM-DD
---
```

`tipo: modulo` para los overviews. Debajo del frontmatter, el back-link:
`> [[<Módulo>|← <Módulo>]] | [[Escritura|← Inicio]]`; los overviews usan solo
`> [[Escritura|← Inicio]]`.

## 5. Templates

### A — Teoría (`wiki/1. Teoría/`)

```markdown
# <Tema>

> Tesis en una oración.

## 1..n <secciones en el orden en que se dio en clase>
(definiciones: primero como la explicó la clase, después la formulación del autor con año;
clasificaciones en tabla; ejemplos de la clase y de la monografía modelo)

## Errores típicos
(advertencias de examen de la profesora y confusiones frecuentes)

## En el parcial
(qué preguntas de la guía y qué ejercicios dependen de esta página, con wikilinks)

## Fuentes
```

### B — Corpus (`wiki/2. Corpus/Monografía modelo.md`)

Estructura, recorte, hipótesis y rasgos genéricos de la monografía modelo, más un inventario de
ejemplos citables por tema (cohesión, despersonalización, adjetivos, voces ajenas, registro),
cada uno transcripto literalmente de la monografía y clasificado, y los lugares donde la
monografía se aparta de las convenciones académicas.

### C — Preguntas (`wiki/3. Preguntas/`)

```markdown
### ==<pregunta, literal de la guía o anticipada en clase>==

<respuesta>

> Ver: [[Página de teoría#Sección]]

---
```

La respuesta es una respuesta de examen modelo: texto autónomo que se entiende sin la consigna
(retoma la pregunta en la primera oración), define cada concepto con autor y año ("Según
Bajtín (1985), …"), ejemplifica con casos propios o de la monografía modelo, relaciona con
otros temas cuando la pregunta lo permite y respeta todo lo que la materia enseña: sin primera
persona del singular ni segunda persona, despersonalización (nosotros de autor, se impersonal,
nominalizaciones), sin adjetivos afectivos ni axiológicos, párrafos de dos o tres oraciones,
conectores explícitos. Extensión orientativa: una carilla manuscrita (250 a 400 palabras).

### D — Práctica (`wiki/4. Práctica/`)

Por ejercicio: número del cuadernillo, consigna, texto de entrada (transcripto), resolución paso
a paso con la clasificación de cada elemento, y el criterio que la sostiene con wikilink a la
teoría. Cuando la cátedra publicó una resolución, se sigue esa resolución.

### E — Examen (`wiki/5. Examen/`)

Formato libre según la página, con reglas en tabla o en lista y ejemplos. En `Normativa.md` y
`Glosario.md` los ejemplos salen de `raw/Cuestionarios/` y de las guías de `raw/Normativa/`,
con la respuesta correcta y la explicación de la cátedra.

### F — Overview de módulo (`wiki/<N. Módulo>/<Módulo>.md`)

```markdown
# <Módulo>

> Resumen de una línea.

## Por qué este módulo
## Recorrido sugerido
## Páginas en este módulo
(una línea por página)
## Lo que remarcó la cátedra
(opcional: énfasis y avisos de examen)
## Conecta con
## Fuentes
```

### Orden en el explorador

El plugin custom-sort ordena el explorador según el grupo de marcadores `sortspec`
(`.obsidian/bookmarks.json`): la home, después `wiki/` con sus módulos en orden numérico y,
dentro de cada uno, el overview primero y las páginas en el orden del recorrido sugerido.
Una página nueva se agrega también a ese grupo.

## 6. `## Fuentes`

Una entrada por fuente, con la ubicación y las secciones de la página que respalda:

```markdown
## Fuentes
- `raw/Transcripciones/Clase 7 - 2026-09-17.md`
  - 00:25:25–00:41:10 → 2. Los tipos de nosotros
- `raw/Bibliografía/Obligatoria/Goethals y Delbecque - Personas del discurso y despersonalización.pdf`
  - pp. 70–74 → 2. Los tipos de nosotros, 3. Estrategias de despersonalización
```

Las transcripciones se citan por timestamp, los PDF por página cuando la conversión la muestra
(si no, por sección o apartado) y los cuestionarios por número de pregunta.

## 7. `log.md`

Append-only, una entrada por operación: `## [AAAA-MM-DD] {ingesta|verificacion|consulta} | <título>`
seguido de viñetas.
