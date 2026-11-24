# Hub de Hardening y Blindaje de Seguridad en Pipelines RAG

[![Live Demo](https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-5b3cf5.svg)](https://tavardt-mexico.github.io/rag-security-hardener-mx/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![OWASP LLM](https://img.shields.io/badge/OWASP-LLM%20Top%2010-red.svg)](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
[![MITRE ATLAS](https://img.shields.io/badge/MITRE-ATLAS%20Matrix-orange.svg)](https://atlas.mitre.org/)

**Hub de Arquitectura Defensiva y Blueprints de Hardening para Pipelines RAG (Retrieval-Augmented Generation)**

Desarrollado y mantenido por la división de ingeniería de seguridad en inteligencia artificial de **TAVARDT Mexico**.

***

## Portales Oficiales

* **Portal Institucional**: [Portal Institucional](https://ag.tavardt.com/mx/)
* **Central de Herramientas**: [Central de Ferramentas](https://tools.tavardt.com/mx/)
* **Canal de Atención y Soporte Técnico**: [https://ag.tavardt.com/mx/contacto/](https://ag.tavardt.com/mx/contacto/)

***

## Demostración Online y Hub de Arquitectura Defensiva

Puede consultar la especificación técnica corporativa, las pruebas de diagnóstico arquitectónico y los blueprints de mitigación directamente desde el navegador:

* **[Aplicación Web Oficial en GitHub Pages](https://tavardt-mexico.github.io/rag-security-hardener-mx/)**
* **Central de Herramientas TAVARDT**

> [!NOTE]
> **Alcance de Ejecución Técnica:** Este hub web proporciona especificaciones de arquitectura defensiva y blueprints de configuración. Las auditorías activas de bases vectoriales e integridad de contexto requieren credenciales de entorno y ejecución en la infraestructura de la aplicación mediante la herramienta CLI oficial (`rag_security_auditor.py`). Las páginas web en entornos sandbox de navegador no pueden conectarse directamente a clústeres vectoriales privados.

***

## Blueprints Técnicos de Hardening

1. **rag-security-policy.yml:** Políticas corporativas de seguridad que definen límites de chunks, etiquetas XML de aislamiento de contexto y reglas de validación semántica.
2. **rag_chunk_sanitizer.py:** Pipeline de sanitización para eliminar caracteres invisibles Unicode, secuencias de escape y marcadores de inyección de prompt antes de generar embeddings.
3. **vector_acl_filter.json:** Esquema de consulta vectorial que impone filtros obligatorios de control de acceso (RBAC/ACL) por usuario y organización para evitar la exfiltración de datos.
4. **rag_context_template.xml:** Plantilla de encapsulación de contexto delimitada por etiquetas XML con directivas estrictas de no ejecución para modelos LLM.
5. **rag_security_auditor.py:** Utilidad CLI local determinista ejecutada en el entorno de la aplicación para auditar directamente configuraciones de pipelines RAG y verificar cumplimiento con OWASP LLM.

***

## Uso de la Herramienta CLI Determinista

Para ejecutar la inspección determinista directamente en el entorno de la aplicación RAG:

```bash
# 1. Descargar script de auditoría desde el repositorio oficial
curl -sO https://raw.githubusercontent.com/TAVARDT-Mexico/rag-security-hardener-mx/main/rag_security_auditor.py

# 2. Inspeccionar pipeline y especificaciones defensivas
python3 rag_security_auditor.py

# 3. Exportar diagnóstico en formato estructurado JSON
python3 rag_security_auditor.py -json
```

***

© 2026 TAVARDT. Todos los derechos reservados.
