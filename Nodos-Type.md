# Tipos de Nodos más utilizados

| Nodo                   | Para qué lo usarías                                                              |
| ---------------------- | -------------------------------------------------------------------------------- |
| **Webhook**            | Recibir alertas/eventos desde SIEM, EDR, APIs, etc.                              |
| **HTTP Request** ⭐     | Conectarte a APIs como VirusTotal, AbuseIPDB, Splunk, AWS, etc.                  |
| **IF** ⭐               | Tomar decisiones: `si riesgo > X → generar alerta`.                              |
| **Switch**             | Clasificar eventos según diferentes condiciones.                                 |
| **Code**               | Procesar, transformar o analizar datos con JavaScript/Python.                    |
| **Set / Edit Fields**  | Crear o modificar campos de los eventos.                                         |
| **Merge**              | Combinar información proveniente de diferentes fuentes.                          |
| **Filter**             | Filtrar eventos que cumplan determinadas condiciones.                            |
| **Schedule Trigger** ⭐ | Ejecutar tareas periódicamente, por ejemplo, revisar vulnerabilidades cada 24 h. |
| **Execute Command**    | Ejecutar comandos en el sistema. ⚠️ Requiere especial cuidado por seguridad.     |

## Para SOC / SIEM

Te interesan especialmente:

Webhook → HTTP Request → IF/Switch → Code → alerta

Por ejemplo:

```text
    🚨 Alerta del SIEM
           ↓
       Webhook
           ↓
    Extraer IP sospechosa
           ↓
     HTTP Request
           ↓
      AbuseIPDB
           ↓
          IF
       ↙       ↘
    Maliciosa  Normal
       ↓          ↓
    🚨 Alerta   📝 Registrar
```

## Para AWS / Cloud Security

Acá empezaría a aprender:

AWS IAM → gestionar/consultar identidades y permisos.
AWS S3 → automatizar comprobaciones sobre buckets.
AWS Lambda → ejecutar funciones como parte del workflow.
AWS SNS → enviar notificaciones.
AWS SQS → trabajar con colas de eventos.
AWS CloudWatch → monitoreo y eventos.
HTTP Request → conectar servicios de AWS que no tengas directamente como nodo.

n8n dispone de credenciales y nodos para varios servicios AWS, incluyendo IAM, S3, Lambda, SNS, SQS y otros.

En mi caso estoy desarrollando un proyecto de Secure Baselines me correspondería verificar líneas de base seguras en múltiples equipos, para ello mi esquema de nodos será:

```text
Schedule Trigger
       ↓

HTTP Request
       ↓

Obtener estado del equipo
       ↓

Code / Edit Fields
       ↓

      IF
   ↙       ↘

Cumple    No cumple
   ↓          ↓

Registrar   Remediar
              ↓

        Verificar nuevamente
```

Luego conectarlo con AWS, o un SIEM, EDR, sistemas de tickets, etc.
