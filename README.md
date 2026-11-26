<p align="center">
  <a href="https://ag.tavardt.com/mx/">
    <img src="https://ag.tavardt.com/img/tavardt-banner.png" alt="TAVARDT" width="1024" />
  </a>
</p>

# Hub de Hardening y Blindaje de Seguridad en Pipelines RAG

[![Live Demo](https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-5b3cf5.svg)](https://tavardt-mexico.github.io/rag-security-hardener-mx/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

***

Motor de evaluación de seguridad y blindaje contextual para arquitecturas RAG (Retrieval-Augmented Generation) desarrollado por **TAVARDT**. Basado en las directrices OWASP LLM01, OWASP LLM04, OWASP LLM07 y el marco MITRE ATLAS, el kit audita el aislamiento vectorial multi-tenant, sanitiza inyecciones indirectas y exporta middleware defensivo.

***

## Capacidades Principales y Arquitectura Defensiva

* **Auditoría Determinista de Canales**: Inspecciona límites contextuales, filtrado de metadados y cuotas de fragmentación frente a estándares formales de seguridad.
* **Generación Automatizada de Middleware**: Exporta clases modulares en Python configuradas para depurar textos recuperados y forzar encapsulamiento estricto en XML.
* **Verificación de Aislamiento Multi-Tenant**: Certifica que las búsquedas vectoriales requieran firmas y metadatos verificados para evitar filtraciones de datos entre clientes.

***

## Vectores de Riesgo e Impacto Operacional

Procesar flujos RAG sin aislamiento de contexto expone la infraestructura a inyecciones indirectas que secuestran la ejecución del modelo y sustraen datos privados. El paquete audita cinco áreas críticas de seguridad:

* **Integridad en la Ingesta de Documentos**: Audita canales de ingesta frente a inyecciones esteganográficas en PDFs, códigos de control unicode y formatos maliciosos (Deducción: hasta -25 puntos).
* **Aislamiento Multi-Tenant en Bases Vectoriales**: Señala colecciones compartidas sin particiones estrictas por espacios de nombres o metadatos de control de acceso (Deducción: hasta -30 puntos).
* **Encapsulamiento de Límites Contextuales**: Bloquea la concatenación directa de texto exigiendo etiquetas delimitadoras XML con órdenes de no ejecución (Deducción: hasta -25 puntos).
* **Filtrado de Inyecciones Indirectas de Prompt**: Aplica filtros heurísticos de expresiones regulares para neutralizar comandos adversarios en fragmentos recuperados (Deducción: hasta -20 puntos).
* **Puertas de Validación de Salida y Enmascaramiento**: Impone verificación de citas y filtros regex para proteger información confidencial antes de emitir respuestas (Deducción: hasta -15 puntos).

Las arquitecturas evaluadas obtienen un puntaje acumulado de 10 a 100 puntos. El sistema clasifica el resultado en **HARDENED** (85 a 100 puntos), **MODERATE** (50 a 84 puntos) o **CRITICAL** (menos de 50 puntos), deteniendo los despliegues de producción vulnerables.

***

## Instalación y Ejecución CLI

Evalúe la seguridad de sus flujos o exporte componentes de middleware mediante comandos estándar de Python:

```bash
# Clonar el repositorio oficial
git clone https://github.com/TAVARDT-Mexico/rag-security-hardener-mx.git

# Acceder al directorio del proyecto
cd rag-security-hardener-mx

# Evaluar canal RAG en todos los niveles defensivos
python rag_security_hardener.py -i 3 -v 3 -c 3 -f 3 -g 3

# Exportar middleware de blindaje en Python
python rag_security_hardener.py -i 3 -v 3 -c 3 -f 3 -g 3 -e defensive_rag_middleware.py

# Exportar reporte estructurado en formato JSON
python rag_security_hardener.py -i 3 -v 3 -c 3 -f 3 -g 3 -j
```

***

## Preguntas Frecuentes Técnicas

### ¿Qué vectores de vulnerabilidad evalúa el kit de seguridad RAG en los canales de recuperación?

La herramienta audita la canalización frente a ingesta de documentos sin autenticación, filtraciones multi-tenant en bases vectoriales, escape de límites contextuales, inyección indirecta y respuestas no validadas. Las arquitecturas analizadas obtienen una calificación de 10 a 100 puntos que las clasifica en HARDENED, MODERATE o CRITICAL.

### ¿Cómo previene el encapsulamiento contextual en etiquetas XML las inyecciones indirectas?

Confinar los fragmentos recuperados dentro de etiquetas XML estrictas delimita formalmente el contenido externo frente a las instrucciones directas del sistema. Esta separación impide que órdenes hostiles insertadas en documentos de terceros se interpreten como directivas ejecutables por el modelo de lenguaje.

### ¿Por qué resulta crítica la filtración por metadados de inquilino en bases vectoriales multi-tenant?

Si no se configuran espacios de nombres independientes o filtros de metadatos validados, las búsquedas por similitud semántica pueden extraer registros de otros clientes. Establecer barreras de control de acceso al consultar la base vectorial elimina fugas laterales de datos privados entre distintas entidades.

### ¿Qué capacidades de protección proporciona el plano de middleware exportado por la herramienta?

Generar el archivo mediante la opción -e crea una clase defensiva en Python diseñada para filtrar patrones maliciosos y sanear etiquetas antes de ensamblar el prompt. Esta capa de contención intercepta intentos de anulación de directivas y solicitudes de extracción de credenciales en tiempo de ejecución.

### ¿Puede implementarse el kit de blindaje en canales automatizados de integración continua CI/CD?

Los utilitarios CLI admiten niveles de parámetros o archivos de configuración emitiendo diagnósticos en formato estructurado con el parámetro -j. Las rutinas automatizadas de despliegue pueden examinar la puntuación JSON resultante para paralizar entregas que incumplan las directrices de seguridad.

***

## Enlaces Útiles

* **Portal Corporativo:** https://ag.tavardt.com/mx/
* **Suite de Diagnósticos:** https://tools.tavardt.com/mx/
* **Contacto Técnico:** https://ag.tavardt.com/mx/contacto/

***

### Licencia
Distribuido bajo la Licencia MIT. Consulte [LICENSE](LICENSE) para más detalles.

***

© 2026 TAVARDT. Todos los derechos reservados.
