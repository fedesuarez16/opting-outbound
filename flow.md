```mermaid
flowchart TD

A[Base de Datos de Leads] --> B[CRM Central]

B --> C[Campañas Email Masivas]

B --> D[Selección Contactos WhatsApp]
D --> E[Generar botón wa.me<br/>Mensaje predefinido]
E --> F[Usuario envía mensaje]

F --> G{¿Cliente responde?}

G -- No --> H[Lead sin opt-in<br/>Queda en cola outbound]
G -- Sí --> I[Opt-in confirmado]

I --> J[Clasificación del Lead<br/>Frío / Tibio / Caliente]

J --> K[Perfil del Lead]

K --> L[Enriquecimiento Automático<br/>IA analiza conversación]
K --> M[Enriquecimiento Manual<br/>Notas / Tags / Score]

K --> N[Proceso de Seguimiento]

N --> O{¿Dentro de ventana 24 hs?}

O -- Sí --> P[Mensajes personalizados]
P --> Q{¿Respuesta del cliente?}

Q -- No --> R[Reglas de Toques]
R --> R1[2 hs → Toque 1]
R --> R2[42 hs → Toque 2]
R --> R3[72 hs → Toque 3]
R3 --> N

Q -- Sí --> S[Actualizar estado del lead]
S --> J

O -- No --> T[Esperar nuevo contacto<br/>o reiniciar outbound]

J --> U[CRM genera tareas diarias]
U --> V[Vendedor ejecuta tareas<br/>Llamadas / Mensajes]

L --> W[IA agenda llamada]
W --> X[Notificación al vendedor]

J --> Y[Conversión progresiva]
Y --> Y1[Frío → Tibio]
Y1 --> Y2[Tibio → Caliente]
Y2 --> Z[Cierre / Venta]
