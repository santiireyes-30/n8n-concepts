# N8N y automatización en Ciberseguridad

N8N es una plataforma de **automatización de workflows** que permite conectar diferentes sistemas, procesar información y ejecutar tareas automáticamente.

Un **workflow** es una secuencia de pasos que se ejecutan cuando ocurre un evento. Cada paso está representado por un **nodo**, que puede recibir, procesar o enviar información a otros sistemas. 

Brevemente Workflow = Cadena de Nodos Conenectados

Tipos de Nodos:

- Entrada: Recepción de datos

- Procesamiento: Transformación/Análisis

- Salida: Envío a servicios externos

Vamos a poner un ejemplo de ciberseguridad para saber como actúa o como es el proceso

Ejemplo:

📧 Correo sospechoso  
↓  
🔎 Extraer enlaces y archivos  
↓  
🛡️ Consultar Threat Intelligence  
↓  
⚠️ Analizar riesgo  
↓  
🚨 Generar alerta

## Utilidad en Ciberseguridad

La automatización permite reducir tareas repetitivas que normalmente realizaría un analista, como:

- Analizar correos sospechosos.
- Extraer y enriquecer **IOCs**.
- Consultar APIs de Threat Intelligence.
- Correlacionar eventos de seguridad.
- Generar alertas automáticamente.

## ¿Cómo funciona N8N?

Los workflows se construyen conectando **nodos**.

Cada nodo realiza una acción y pasa el resultado al siguiente. De esta manera, los datos van avanzando y transformándose a lo largo del workflow.

Esto permite crear procesos de seguridad complejos sin tener que desarrollar una aplicación completa desde cero.

## Objetivo

El objetivo no es convertirse en experto en N8N, sino aprender lo necesario para construir **automatizaciones aplicadas a Ciberseguridad**.

Mas adelante se trabajará con workflows para analizar eventos, procesar IOCs, consultar fuentes externas y automatizar tareas de detección y respuesta.
