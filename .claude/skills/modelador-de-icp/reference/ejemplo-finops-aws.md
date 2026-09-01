# Ejemplo trabajado: FinOps sobre AWS, Chile y LATAM

> ⚠️ **Material de enseñanza, no la consulta vigente.** La consulta real es la v1 en
> Notion (ver `NOTION.md`), donde las cinco preguntas abiertas del final ya están
> cerradas. Este archivo se conserva **con las preguntas todavía abiertas** porque su
> valor es mostrar el comportamiento correcto: qué se traduce, qué se marca como
> proxy, y qué se deja sin rellenar en vez de inventarlo.
>
> Si lo "actualizas" con las respuestas, pierdes la lección.

Muestra la traducción de prosa a consulta. **La prosa de origen fue breve; buena
parte del trabajo fue marcar lo que no decía.**

## Prosa de origen

> "Ayudo a empresas a reducir y controlar los gastos en AWS (FinOps), y todo lo
> relacionado a las arquitecturas de este ambiente. Mi cliente ideal tiene que ser
> empresas privadas o públicas que tengan como producción ambientes en AWS, ya sea
> en Chile o LATAM, y que la toma de decisiones sea CTO, CIO, gerente, subgerente,
> jefe de TI o TICA."

## Consulta resultante

### 1. Firmografía
- **Criterio:** privadas o públicas. Ambas, explícitamente.
- **Señal observable:** tipo de organización en su página de LinkedIn.
- **Tipo:** directo.
- ⚠️ **Tamaño e industria: sin restricción — no especificado.** Va a preguntas abiertas.

### 2. Señal técnica
- **Criterio:** ambientes AWS **en producción**. No experimentos, no certificaciones
  personales.
- **Señal observable:** menciones a AWS, EC2, RDS, S3, EKS, Lambda, Savings Plans,
  Reserved Instances o "factura cloud" en titular, experiencia o comentario. Ofertas
  de empleo de la empresa pidiendo AWS.
- **Tipo:** **proxy.** Nadie declara "tenemos producción en AWS". Lo más cercano a
  evidencia directa es una oferta de empleo de la empresa pidiendo operar AWS.
- ⚠️ Un perfil que solo exhibe **certificaciones** AWS indica interés personal, no
  producción de la empresa. Señal débil, y frecuente entre estudiantes.

### 3. Rol decisor
| Cargo | Variantes | Tipo |
|---|---|---|
| CTO | Chief Technology Officer, Director de Tecnología | Decisor |
| CIO | Chief Information Officer, Director de Sistemas | Decisor |
| Gerente TI | Gerente de Tecnología, IT Manager | Decisor |
| Subgerente TI | Subgerente de Tecnología | Decisor |
| Jefe de TI | Jefe de Tecnología, Jefe de Infraestructura, IT Lead | Decisor |
| Jefe TICA | Jefe de TICA | Decisor |

⚠️ **TICA** es sigla del sector público chileno (Tecnologías de Información y
Comunicaciones). Su presencia es señal fuerte de organismo público chileno. No
aparece en perfiles fuera de Chile: úsala como refuerzo de geografía.

**Influyentes no nombrados en la prosa** — arquitecto cloud, DevOps lead, SRE lead.
No firman, pero definen el pliego y detectan el dolor primero. **Pregunta abierta:
¿se incluyen?** No se asumió que sí.

### 4. Geografía
- **Incluye:** Chile (prioritario, se nombra primero) y LATAM.
- **Detección:** 1) ubicación del perfil; 2) sede de la empresa; 3) giros del
  español y sigla TICA, solo como refuerzo.
- ⚠️ **"LATAM" no se delimitó.** ¿Incluye Brasil, donde el idioma cambia? ¿México?
  Va a preguntas abiertas.

### 5. Exclusiones
⚠️ **La prosa no nombró ninguna.** No se inventaron. Se propusieron para aprobación:
otros consultores FinOps, partners AWS que venden lo mismo, estudiantes y
certificados sin empresa, "open to work", reclutadores, empleados de AWS.

Ninguna se aplica hasta que la persona las confirme.

### 6. Señal de dolor
| Nivel | En el comentario |
|---|---|
| Declarado | "nos disparó la factura", "no entendemos el gasto de X", "nos pasamos del presupuesto" |
| Adyacente | pregunta por Savings Plans vs Reserved, cómo asignar costos por equipo, si conviene Graviton, cómo apagar ambientes fuera de horario |
| Temático | comenta el post de FinOps sin señal propia |

## Preguntas abiertas
1. **Tamaño mínimo de empresa.** Bajo cierto gasto en AWS, FinOps no se paga solo.
2. **Alcance de "LATAM".** ¿Brasil? ¿México? Cambia el idioma del outreach.
3. **¿Entran los influyentes técnicos** (arquitecto, DevOps, SRE) o solo decisores?
4. **Exclusiones**, ninguna confirmada.
5. **¿El sector público chileno entra igual?** Compra por licitación, ciclo distinto,
   el outreach directo a un Jefe TICA puede no ser la vía.

Estas cinco no se rellenaron con supuestos. Es correcto que la consulta se guarde en
Notion con ellas abiertas, y se cierren conversando.
