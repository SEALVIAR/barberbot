## Workflow de N8n

El archivo `n8n/barberbot_workflow_public.json` contiene la versión pública del flujo de automatización de BarberBot desarrollado en N8n.

Este flujo implementa la primera parte del proyecto, correspondiente a la automatización visual. Permite recibir mensajes desde Telegram, interpretar la intención del cliente con un modelo de lenguaje, consultar disponibilidad en Google Calendar, crear, cancelar o reprogramar citas, registrar información en Google Sheets y aplicar una estrategia de riesgo mediante lógica difusa.

Por seguridad, el archivo publicado no contiene credenciales reales, correos personales, IDs privados de Google Calendar, IDs de Google Sheets ni webhooks reales. En su lugar, se usan valores genéricos para que cualquier persona pueda reconstruir el flujo con sus propias cuentas.

### Valores que deben reemplazarse

Antes de importar y ejecutar el workflow, cada usuario debe reemplazar los siguientes valores:

| Placeholder                       | Descripción                                               |
| --------------------------------- | --------------------------------------------------------- |
| `TELEGRAM_CREDENTIAL_HERE`        | Credencial de Telegram configurada en N8n                 |
| `OPENAI_CREDENTIAL_HERE`          | Credencial de OpenAI configurada en N8n                   |
| `GOOGLE_CALENDAR_CREDENTIAL_HERE` | Credencial de Google Calendar configurada en N8n          |
| `GOOGLE_SHEETS_CREDENTIAL_HERE`   | Credencial de Google Sheets configurada en N8n            |
| `CALENDAR_ID_HERE`                | ID o correo del calendario donde se gestionarán las citas |
| `GOOGLE_SHEET_ID_HERE`            | ID del archivo de Google Sheets usado como historial      |
| `GOOGLE_SHEET_URL_HERE`           | URL del Google Sheet usado para registrar las pruebas     |
| `WEBHOOK_ID_HERE`                 | Webhook generado por la instancia de N8n                  |
| `WORKFLOW_ID_HERE`                | ID interno del workflow en la instancia de N8n            |
| `WORKFLOW_VERSION_ID_HERE`        | ID de versión del workflow                                |
| `N8N_INSTANCE_ID_HERE`            | ID de la instancia local o cloud de N8n                   |

### Cómo reconstruir el flujo

1. Crear una cuenta o instancia de N8n.
2. Importar el archivo `n8n/barberbot_workflow_public.json`.
3. Configurar las credenciales de Telegram, OpenAI, Google Calendar y Google Sheets.
4. Crear o seleccionar un calendario para las citas de BarberBot.
5. Crear un Google Sheet con las columnas necesarias para registrar solicitudes, resultados, disponibilidad, riesgo y métricas.
6. Reemplazar los placeholders del archivo por los valores reales de la nueva instancia.
7. Activar el workflow y probar cada rama: reservar, precios, horarios, cancelar, cambiar hora y solicitud desconocida.

### Nota de seguridad

El archivo original exportado desde N8n no debe subirse directamente al repositorio, porque puede contener información privada como credenciales, webhooks, correos, IDs de documentos y URLs internas.

Por esta razón, en este repositorio solo se publica la versión sanitizada:

`n8n/barberbot_workflow_public.json`
