# Estrategia Outbound — Agente de IA de Ventas

```mermaid
flowchart TD
    A["🗂️ FASE 1 — Base de datos"] --> B["Segmentación por ICP\nEquipo ventas 5–50 personas · CRM activo · Volumen de leads"]

    subgraph FUENTES["Fuentes de leads"]
        F1["Apollo.io / Hunter\nEmails verificados"]
        F2["LinkedIn Sales Nav\nSegmentación por cargo"]
        F3["Scraping + Directorios\nClutch, G2, Pág. Amarillas"]
    end

    FUENTES --> A

    B --> C["📬 FASE 2 — Secuencia multicanal 10 días"]

    subgraph SECUENCIA["Secuencia coordinada"]
        direction LR

        subgraph LI["🔵 LinkedIn"]
            LI1["Día 1 · Conexión\nNota breve y personal"]
            LI2["Día 4 · 1er DM\nPregunta de contexto"]
            LI3["Día 7 · DM de valor\nCaso de éxito / recurso"]
            LI4["Día 9 · Cierre\nLink al calendario"]
            LI1 --> LI2 --> LI3 --> LI4
        end

        subgraph EM["📧 Email"]
            EM1["Día 3 · Apertura\nGancho con dolor"]
            EM2["Día 5 · Caso de éxito\n+40% reuniones agendadas"]
            EM3["Día 8 · CTA directo\n¿15 min para el demo?"]
            EM4["Día 10 · Breakup email\n¿Cuándo sería buen momento?"]
            EM1 --> EM2 --> EM3 --> EM4
        end

        subgraph WA["💬 WhatsApp"]
            WA1["Día 2 · Apertura\nPresentación + pregunta"]
            WA2["Día 6 · Video demo\nLoom 60 seg del agente"]
            WA1 --> WA2
        end
    end

    C --> SECUENCIA

    SECUENCIA --> D{"¿Responde el lead?"}

    D -- No --> E["Pasar a lista de\nnurturing pasivo"]
    D -- Sí --> F["🤖 FASE 3 — El agente de IA actúa"]

    subgraph AGENTE["Agente en acción"]
        AG1["Califica el lead\nEmpresa · CRM · Presupuesto · Urgencia"]
        AG2["Agenda la reunión\nSincroniza Calendar + confirmación"]
        AG3["Registra en CRM\nEtiqueta · Puntúa · Notifica al equipo"]
        AG1 --> AG2 --> AG3
    end

    F --> AGENTE

    AGENTE --> G["📊 FASE 4 — Métricas y optimización"]

    subgraph METRICAS["KPIs a trackear"]
        M1["Open rate email\nObjetivo: +40%"]
        M2["Reply rate\nObjetivo: 8–15%"]
        M3["Aceptación LinkedIn\nObjetivo: +30%"]
        M4["Demos agendadas\nvs contactos totales"]
    end

    G --> METRICAS
    METRICAS --> |"Iterar cada 2 semanas"| C
```

## Cronograma de 10 días

```mermaid
gantt
    title Secuencia de contacto por canal
    dateFormat  D
    axisFormat Día %d

    section LinkedIn
    Solicitud de conexión        :li1, 1, 1d
    1er DM — pregunta contexto   :li2, 4, 1d
    DM de valor / caso de éxito  :li3, 7, 1d
    Cierre — link calendario     :li4, 9, 1d

    section Email
    Apertura — gancho con dolor  :em1, 3, 1d
    Caso de éxito                :em2, 5, 1d
    CTA directo — pedir demo     :em3, 8, 1d
    Breakup email                :em4, 10, 1d

    section WhatsApp
    Apertura — presentación      :wa1, 2, 1d
    Video demo Loom 60 seg       :wa2, 6, 1d
```

## Notas de implementación

- **LinkedIn primero**: el warm-up (seguir + comentar posts) se hace *antes* del Día 1 para generar familiaridad
- **Nota de conexión**: corta y personal, sin mencionar el producto todavía
- **WhatsApp**: solo si se tiene el número · máximo 2 mensajes no solicitados
- **Cuando responde**: el agente de IA toma el control de la conversación, califica, agenda y registra en CRM automáticamente
- **Iteración**: revisar métricas cada 2 semanas y ajustar asuntos, ganchos y CTAs
