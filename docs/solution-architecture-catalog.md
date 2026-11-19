# AI Integration Consultancy

**Solution Architecture Catalog**

Technical fichas, implementation components and commercial framework

---

## Índice

1. [Estructura estándar de cada solución](#1-estructura-estándar-de-cada-solución)
2. [Solution Catalog](#2-solution-catalog)
   - [SOLUTION 01 — Enterprise Knowledge Assistant](#solution-01--enterprise-knowledge-assistant)
   - [SOLUTION 02 — Enterprise Data & Analytics Assistant](#solution-02--enterprise-data--analytics-assistant)
   - [SOLUTION 03 — Intelligent Document Processing](#solution-03--intelligent-document-processing)
   - [SOLUTION 04 — Workflow & Process Automation](#solution-04--workflow--process-automation)
   - [SOLUTION 05 — AI Agent & Multi-System Operations](#solution-05--ai-agent--multi-system-operations)
   - [SOLUTION 06 — AI Communication & Customer Interaction](#solution-06--ai-communication--customer-interaction)
   - [SOLUTION 07 — Event-Driven Intelligence & Monitoring](#solution-07--event-driven-intelligence--monitoring)
   - [SOLUTION 08 — Custom Enterprise AI Application](#solution-08--custom-enterprise-ai-application)
3. [Niveles comerciales de implementación](#3-niveles-comerciales-de-implementación)
4. [Framework de estimación y presupuestación](#4-framework-de-estimación-y-presupuestación)
5. [Plantilla para nuevas soluciones personalizadas](#5-plantilla-para-nuevas-soluciones-personalizadas)
6. [Posicionamiento comercial](#6-posicionamiento-comercial)
7. [Regla final de diseño](#7-regla-final-de-diseño)

---

## 1. Estructura estándar de cada solución

Todas nuestras soluciones siguen la misma estructura documental.

Cada ficha debe responder a estas preguntas:

| Elemento | Qué define |
|----------|------------|
| **Business Objective** | Qué problema empresarial resuelve |
| **Use Cases** | En qué situaciones se utiliza |
| **Core Operations** | Qué operaciones fundamentales ejecuta |
| **Architecture Pattern** | Cómo se estructura la solución |
| **Required Components** | Qué componentes son imprescindibles |
| **Optional Components** | Qué módulos pueden añadirse |
| **Data Sources** | Qué información necesita |
| **Integrations** | Qué sistemas debe conectar |
| **Execution Flow** | Cómo funciona de principio a fin |
| **Security** | Qué controles necesita |
| **Deliverables** | Qué recibe el cliente |
| **Complexity** | Qué determina la dificultad |
| **Acceptance Criteria** | Cómo se verifica el resultado |
| **Extensions** | Cómo puede ampliarse posteriormente |

La arquitectura siempre será **independiente del proveedor**. Los nombres comerciales de las tecnologías se seleccionan durante el diseño técnico.

---

## 2. Solution Catalog

---

### SOLUTION 01 — Enterprise Knowledge Assistant

**Categoría:** Knowledge Management / RAG / Enterprise Search

**Objetivo:** proporcionar a empleados y equipos acceso conversacional al conocimiento empresarial, permitiendo consultar documentos y fuentes internas con respuestas contextualizadas y referencias.

#### 2.1. Casos de uso

- Consulta de políticas empresariales
- Búsqueda de procedimientos internos
- Consulta de contratos
- Recuperación de información técnica
- Asistencia a departamentos de HR, Legal, Finance y Operations
- Consulta de manuales y documentación
- Knowledge management entre departamentos

#### 2.2. Operaciones fundamentales

`Store → Retrieve → Transform → Decide (opcional) → Interact`

#### 2.3. Arquitectura

```
Document Sources
→ Ingestion
→ Extraction & Parsing
→ Chunking
→ Embeddings / Search Index
→ Retrieval
→ Reranking (opcional)
→ LLM
→ Response + Citations
→ User Interface
```

#### 2.4. Componentes

**Core components:**
- Source Connectors
- Document Ingestion Pipeline
- Document Parsing / Text Extraction
- Chunking & Metadata Processing
- Search Index
- Retrieval Engine
- LLM Integration
- Response Generation
- User Interface
- Logging & Basic Evaluation

**Optional modules:**
- OCR
- Vector Database
- Hybrid Search
- Reranking
- Knowledge Graph
- Multilingual Retrieval
- Permission-Aware Retrieval
- Advanced Evaluation
- Document Change Detection
- Multiple LLM Providers
- Department-Specific Knowledge Bases

#### 2.5. Requisitos de entrada

- Acceso a las fuentes documentales
- Identificación de repositorios
- Estructura de usuarios y departamentos
- Documentos de calidad razonable
- Definición de permisos
- Preguntas representativas para evaluación

#### 2.6. Entregables

- Knowledge Assistant
- Document ingestion pipeline
- Configuración de fuentes
- Search / retrieval architecture
- User interface
- Source citation functionality
- Evaluation test set
- Technical documentation
- Deployment documentation

#### 2.7. Criterios de aceptación

- Recuperación de documentos relevantes
- Respuestas fundamentadas en las fuentes disponibles
- Referencias verificables
- Respeto de los permisos documentales
- Comportamiento adecuado ante preguntas sin respuesta
- Rendimiento aceptable según el volumen y los requisitos acordados

#### 2.8. Factores de complejidad

| Factor | Complejidad |
|--------|-------------|
| Número de repositorios | Baja / Media / Alta |
| Volumen documental | Bajo / Medio / Alto |
| Calidad documental | Alta / Variable / Baja |
| Número de usuarios | Reducido / Medio / Alto |
| Permisos granulares | No / Sí |
| Multilingüismo | No / Sí |
| Actualización documental | Manual / Programada / Continua |

---

### SOLUTION 02 — Enterprise Data & Analytics Assistant

**Categoría:** Business Intelligence / Data Analytics / Conversational BI

**Objetivo:** permitir a los usuarios consultar información empresarial, analizar indicadores y obtener explicaciones mediante lenguaje natural.

#### 2.1. Casos de uso

- Consulta de ventas
- Análisis financiero
- Reporting ejecutivo
- Análisis de rendimiento
- Comparación entre periodos
- Análisis de desviaciones
- Forecasting
- Consulta conversacional de dashboards

#### 2.2. Operaciones fundamentales

`Retrieve → Analyze → Transform → Interact`  
Decide puede incorporarse para recomendaciones y acciones posteriores.

#### 2.3. Arquitectura

```
User Question
→ Intent Interpretation
→ Metric Identification
→ Semantic Layer / SQL
→ Data Retrieval
→ Calculation & Validation
→ AI Interpretation
→ Visualization / Explanation
```

#### 2.4. Componentes

**Core components:**
- Data Connectors
- Database / Data Warehouse Access
- Business Metrics Definitions
- Semantic Layer or Governed Query Layer
- Query Engine
- LLM Interpretation
- Output Validation
- User Interface

**Optional modules:**
- Natural Language to SQL
- Power BI Integration
- Dashboard Generation
- Automated Reporting
- Forecasting Models
- Anomaly Detection
- Financial Analysis
- Scheduled Executive Reports
- Multi-Database Analytics
- Data Lineage
- Advanced Data Governance

#### 2.5. Requisitos de entrada

- Acceso a bases de datos o plataformas BI
- Diccionario de datos
- Definición de KPIs
- Fórmulas empresariales
- Identificación de usuarios autorizados
- Consultas representativas
- Validación de los responsables de negocio

#### 2.6. Entregables

- Conversational Analytics Interface
- Data integration layer
- Semantic / metric definitions
- Query execution layer
- AI interpretation layer
- Validated business queries
- Reporting functionality
- Documentation

#### 2.7. Criterios de aceptación

- Exactitud de métricas frente a las fuentes oficiales
- Consistencia de definiciones de negocio
- Consultas autorizadas
- Explicaciones respaldadas por resultados
- Gestión de consultas no soportadas
- Rendimiento dentro de los límites acordados

#### 2.8. Factores de complejidad

- Número de bases de datos
- Calidad y consistencia de los datos
- Complejidad de las métricas
- Número de dashboards
- Complejidad de permisos
- Necesidad de forecasting
- Frecuencia de actualización

---

### SOLUTION 03 — Intelligent Document Processing

**Categoría:** Document AI / Information Extraction / Business Process Automation

**Objetivo:** automatizar la recepción, extracción, clasificación y procesamiento de información contenida en documentos.

#### 3.1. Casos de uso

- Procesamiento de facturas
- Extracción de contratos
- Órdenes de compra
- Formularios
- Documentación de clientes
- Documentos fiscales
- Solicitudes administrativas
- Clasificación documental

#### 3.2. Operaciones fundamentales

`Retrieve → Transform → Analyze → Decide → Execute`

#### 3.3. Arquitectura

```
Document Arrival
→ Ingestion
→ OCR / Parsing
→ Document Classification
→ Information Extraction
→ Structured Output
→ Validation
→ Human Approval (when required)
→ Destination System
```

#### 3.4. Componentes

**Core components:**
- Document Source Connector
- Ingestion Pipeline
- OCR / Parsing
- Document Classification
- Field Extraction
- Structured Output
- Validation Engine
- Exception Handling
- Destination Connector
- Audit Logging

**Optional modules:**
- Advanced Table Extraction
- Handwriting Recognition
- Signature Detection
- Contract Analysis
- Multilingual Processing
- Duplicate Detection
- Fraud Indicators
- Human Review Interface
- Approval Workflows
- Document Archiving

#### 3.5. Requisitos de entrada

- Muestras de documentos
- Definición de campos
- Reglas de validación
- Formatos aceptados
- Sistema de destino
- Ejemplos de documentos excepcionales
- Definición de aprobación

#### 3.6. Entregables

- Document Processing Pipeline
- Extraction Configuration
- Classification Logic
- Validation Engine
- Integration with destination system
- Exception Management
- Audit Logs
- Accuracy Evaluation Report

#### 3.7. Criterios de aceptación

- Precisión por campo extraído
- Tasa de documentos procesados correctamente
- Tasa de excepciones
- Detección de campos obligatorios ausentes
- Correcta gestión de duplicados
- Integridad de los datos enviados al sistema de destino

#### 3.8. Factores de complejidad

- Número de tipos documentales
- Variabilidad de formatos
- Calidad de imágenes
- Volumen mensual
- Número de campos
- Complejidad de validación
- Número de sistemas de destino

---

### SOLUTION 04 — Workflow & Process Automation

**Categoría:** Business Process Automation / System Integration

**Objetivo:** conectar aplicaciones y automatizar procesos empresariales mediante workflows estructurados.

#### 4.1. Casos de uso

- Automatización de emails
- Sincronización de CRM
- Procesos de aprobación
- Onboarding de clientes
- Gestión de solicitudes
- Automatización administrativa
- Actualización de registros
- Notificaciones y seguimiento

#### 4.2. Operaciones fundamentales

`Communicate → Retrieve → Transform → Decide → Execute → Orchestrate → Monitor`

#### 4.3. Arquitectura

```
Trigger / Event
→ Workflow Engine
→ Data Retrieval
→ Conditions & Business Rules
→ API Actions
→ Approval (optional)
→ Confirmation
→ Logging
```

#### 4.4. Componentes

**Core components:**
- Trigger Configuration
- Workflow Engine
- Application Connectors
- Data Mapping
- Conditional Logic
- API Execution
- Error Handling
- Execution Logs

**Optional modules:**
- AI Classification
- AI Extraction
- Human Approval
- Scheduled Workflows
- Multi-Application Synchronization
- Queue Management
- Advanced Retry Logic
- RPA
- Notifications
- Process Analytics

#### 4.5. Requisitos de entrada

- Proceso actual documentado
- Sistemas involucrados
- Credenciales y permisos
- Reglas de negocio
- Excepciones conocidas
- Resultado esperado
- Responsable del proceso

#### 4.6. Entregables

- Workflow Architecture
- Configured Automation
- Application Integrations
- Business Rules
- Error Handling
- Monitoring
- Process Documentation
- Handover

#### 4.7. Criterios de aceptación

- Ejecución correcta del flujo
- Integridad de los datos transferidos
- Gestión de excepciones
- Ausencia de ejecuciones duplicadas no deseadas
- Recuperación ante errores
- Registro de las operaciones
- Cumplimiento de tiempos acordados

#### 4.8. Factores de complejidad

- Número de aplicaciones
- Número de pasos
- Cantidad de excepciones
- Complejidad de reglas
- Necesidad de aprobaciones
- Disponibilidad de APIs
- Frecuencia de ejecución

---

### SOLUTION 05 — AI Agent & Multi-System Operations

**Categoría:** Agentic AI / Enterprise Operations

**Objetivo:** desarrollar agentes capaces de investigar situaciones, consultar herramientas empresariales y realizar tareas mediante flujos de trabajo dinámicos y controlados.

#### 5.1. Casos de uso

- Customer Operations Agent
- Sales Research Agent
- Procurement Assistant
- Internal IT Agent
- Finance Operations Assistant
- Customer Account Investigation
- Multi-System Business Assistant

#### 5.2. Operaciones fundamentales

`Retrieve → Analyze → Decide → Execute → Orchestrate`

#### 5.3. Arquitectura

```
User Request
→ Agent Runtime
→ Context & State
→ Planning / Task Decomposition
→ Tool Selection
→ API / Search / Database Operations
→ Result Evaluation
→ Next Action
→ Approval Gate
→ Final Response
```

#### 5.4. Componentes

**Core components:**
- LLM / Agent Runtime
- System Prompt / Agent Instructions
- Tool Registry
- API Connectors
- State Management
- Execution Control
- Permissions
- Logging
- Evaluation
- User Interface

**Optional modules:**
- RAG
- Multiple Agents
- Long-Term Memory
- Human Approval
- Advanced Planning
- Workflow Integration
- Persistent Checkpoints
- Browser Automation
- Multimodal Processing
- Agent Evaluation Framework
- Cost and Token Monitoring

#### 5.5. Requisitos de entrada

- Definición de la tarea
- Herramientas autorizadas
- Sistemas accesibles
- Reglas de negocio
- Límites de autonomía
- Acciones permitidas y prohibidas
- Escenarios de aprobación
- Casos de prueba

#### 5.6. Entregables

- Agent Architecture
- Tool Integrations
- Agent Instructions
- State Management
- Execution Policies
- Approval Mechanisms
- Evaluation Dataset
- Monitoring
- Technical Documentation

#### 5.7. Criterios de aceptación

- Finalización de tareas representativas
- Uso correcto de herramientas
- Exactitud de información recuperada
- Cumplimiento de permisos
- Ausencia de acciones no autorizadas
- Gestión de errores
- Trazabilidad de las decisiones y acciones
- Evaluación de costes y rendimiento

#### 5.8. Factores de complejidad

- Número de herramientas
- Número de sistemas
- Libertad de planificación
- Número de pasos
- Riesgo de las acciones
- Necesidad de memoria
- Necesidad de intervención humana
- Complejidad de evaluación

---

### SOLUTION 06 — AI Communication & Customer Interaction

**Categoría:** Conversational AI / Customer Experience

**Objetivo:** automatizar y mejorar la comunicación con clientes y empleados mediante sistemas conversacionales inteligentes.

#### 6.1. Casos de uso

- Atención al cliente
- Asistente de email
- Chatbot empresarial
- Asistente de ventas
- Clasificación de solicitudes
- Voice assistants
- Respuestas automatizadas
- Gestión de conversaciones

#### 6.2. Operaciones fundamentales

`Communicate → Retrieve → Transform → Decide → Execute`

#### 6.3. Arquitectura

```
Communication Channel
→ Message Ingestion
→ Intent Recognition
→ Context Retrieval
→ AI Response Generation
→ Business Validation
→ Human Handoff / Action
→ Conversation Logging
```

#### 6.4. Componentes

**Core components:**
- Communication Channel
- Message Ingestion
- Conversation Management
- Intent Recognition
- LLM
- Response Generation
- Logging
- Escalation Mechanism

**Optional modules:**
- RAG
- CRM Integration
- Customer History Retrieval
- Email Sending
- Voice Recognition
- Text-to-Speech
- Sentiment Classification
- Human Agent Handoff
- Multilingual Support
- Customer Analytics

#### 6.5. Requisitos de entrada

- Canales de comunicación
- Tipos de consultas
- Políticas de atención
- Historial disponible
- Reglas de escalado
- Tono y límites de comunicación
- Acciones autorizadas

#### 6.6. Entregables

- Conversational Assistant
- Channel Integration
- Conversation Logic
- Knowledge Integration (if required)
- Escalation System
- CRM Integration (if required)
- Conversation Evaluation
- Documentation

#### 6.7. Criterios de aceptación

- Calidad de respuesta
- Resolución de consultas
- Correcta derivación a humanos
- Respeto de políticas
- Ausencia de respuestas no fundamentadas en escenarios críticos
- Fiabilidad del canal de comunicación

#### 6.8. Factores de complejidad

- Número de canales
- Volumen de conversaciones
- Número de idiomas
- Integración con CRM
- Necesidad de voz
- Complejidad de consultas
- Nivel de autonomía

---

### SOLUTION 07 — Event-Driven Intelligence & Monitoring

**Categoría:** Event Processing / Intelligent Monitoring

**Objetivo:** detectar acontecimientos en los sistemas empresariales, identificar situaciones relevantes y activar respuestas automáticas.

#### 7.1. Casos de uso

- Detección de anomalías financieras
- Seguimiento de pedidos
- Supervisión de incidencias
- Monitorización de operaciones
- Alertas comerciales
- Detección de problemas
- Compliance monitoring

#### 7.2. Operaciones fundamentales

`Monitor → Retrieve → Analyze → Decide → Communicate → Execute`

#### 7.3. Arquitectura

```
Event Sources
→ Event Ingestion
→ Event Bus / Queue
→ Event Processing
→ Rules / AI Analysis
→ Decision
→ Alert / Workflow Trigger
→ Audit
```

#### 7.4. Componentes

**Core components:**
- Event Sources
- Event Ingestion
- Event Processing
- Rules Engine
- Notification System
- Event Logging
- Monitoring Dashboard

**Optional modules:**
- Kafka / Event Streaming
- Anomaly Detection
- LLM Incident Summarization
- Predictive Monitoring
- Agent Investigation
- Automated Remediation
- Service Management Integration
- Advanced Alert Prioritization

#### 7.5. Requisitos de entrada

- Sistemas que generan eventos
- Definición de eventos importantes
- Umbrales
- Reglas de alerta
- Responsables de notificaciones
- Acciones permitidas
- Requisitos de latencia

#### 7.6. Entregables

- Event Architecture
- Event Connectors
- Detection Rules
- Alerting System
- Dashboard
- Workflow Integrations
- Monitoring and Documentation

#### 7.7. Criterios de aceptación

- Eventos correctamente detectados
- Tiempo de detección
- Tasa de falsos positivos
- Gestión de eventos duplicados
- Fiabilidad de notificaciones
- Trazabilidad de alertas y acciones

#### 7.8. Factores de complejidad

- Número de fuentes
- Volumen de eventos
- Frecuencia
- Necesidad de tiempo real
- Complejidad de reglas
- Necesidad de ML
- Acciones automáticas asociadas

---

### SOLUTION 08 — Custom Enterprise AI Application

**Categoría:** Custom AI Development / Enterprise Application

**Objetivo:** desarrollar una aplicación empresarial personalizada que integre datos, IA, automatización y sistemas existentes en una única experiencia.

#### 8.1. Casos de uso

- Portal de inteligencia empresarial
- Aplicación de gestión interna
- Plataforma de operaciones
- Asistente ejecutivo
- Aplicación financiera
- Plataforma de conocimiento
- Sistema de soporte interno
- Aplicaciones multiagente

#### 8.2. Operaciones fundamentales

Potencialmente todas las operaciones: Store, Retrieve, Transform, Analyze, Decide, Execute, Orchestrate, Communicate, Monitor y Secure.

#### 8.3. Arquitectura

```
Frontend
→ Backend / Application Logic
→ Authentication & Authorization
→ Integration Layer
→ AI Layer
→ Business Logic
→ Data Layer
→ Monitoring & Governance
```

#### 8.4. Componentes

**Core components:**
- Frontend
- Backend
- Authentication
- Database
- Business Logic
- API Integrations
- AI Model Integration
- Logging
- Deployment Infrastructure

**Optional modules:**
- RAG
- Agent Runtime
- Multi-Agent Architecture
- Analytics
- Advanced Workflow
- Document Intelligence
- Role-Based Interfaces
- Advanced Search
- Notifications
- Multi-Tenant Architecture
- Custom Reporting

#### 8.5. Requisitos de entrada

- Business Requirements
- Functional Specifications
- User Roles
- Existing Systems
- Data Model
- UI Requirements
- Security Requirements
- Deployment Constraints

#### 8.6. Entregables

- Architecture Design
- Application Development
- Backend
- Frontend
- Database
- AI Components
- System Integrations
- Testing
- Deployment
- Documentation
- Maintenance Plan

#### 8.7. Criterios de aceptación

- Funcionalidad completa según alcance
- Integraciones operativas
- Seguridad validada
- Rendimiento
- Experiencia de usuario
- Pruebas funcionales
- Documentación
- Despliegue y transferencia

#### 8.8. Factores de complejidad

- Número de funcionalidades
- Número de usuarios
- Integraciones
- Volumen de datos
- Complejidad de UI
- Infraestructura
- Seguridad
- Escalabilidad
- Requisitos de disponibilidad

---

## 3. Niveles comerciales de implementación

Los niveles comerciales **no deben implicar arquitecturas completamente diferentes**. Deben reflejar el alcance, la profundidad y la complejidad de la implementación.

| Nivel | Características |
|-------|-----------------|
| **Starter** | Una necesidad concreta, pocas fuentes, funcionalidad esencial |
| **Professional** | Varias fuentes, lógica más avanzada, mayor integración y evaluación |
| **Enterprise** | Seguridad avanzada, múltiples departamentos, escalabilidad, governance y alta complejidad |

Cada solución puede tener estos niveles, pero su definición debe adaptarse al patrón.

### Ejemplo: Enterprise Knowledge Assistant

**Starter**
- Un repositorio
- Búsqueda documental
- Respuestas con referencias
- Interfaz sencilla

**Professional**
- Múltiples repositorios
- Hybrid Retrieval
- Reranking
- Metadatos
- Evaluación sistemática

**Enterprise**
- Permisos granulares
- Múltiples departamentos
- Escalabilidad
- Governance
- Monitoring avanzado
- Evaluación continua

---

## 4. Framework de estimación y presupuestación

El presupuesto se calcula por **componentes y complejidad**, no simplemente por el nombre de la solución.

### 4.1. Dimensiones de estimación

| Dimensión | Pregunta |
|-----------|----------|
| Discovery | ¿Cuánto análisis requiere? |
| Integrations | ¿Cuántos sistemas deben conectarse? |
| Data | ¿Qué complejidad tienen los datos? |
| AI | ¿Qué nivel de inteligencia se necesita? |
| Workflow | ¿Cuántos pasos y excepciones existen? |
| Security | ¿Qué permisos y controles requiere? |
| Interface | ¿Necesita interfaz personalizada? |
| Deployment | ¿Dónde y cómo se despliega? |
| Testing | ¿Cuántos escenarios deben validarse? |
| Maintenance | ¿Qué soporte y evolución requiere? |

### 4.2. Modelo de estimación

Cada proyecto debe descomponerse en:

1. Discovery & Requirements
2. Architecture & Design
3. Data Integration
4. Application Integration
5. AI Implementation
6. Workflow Development
7. Interface Development
8. Security & Governance
9. Testing & Evaluation
10. Deployment
11. Documentation & Handover

La estimación se realiza por horas o jornadas de cada especialidad, dependencias, incertidumbre y riesgos.

### 4.3. Costes que deben separarse

**Implementation Costs**
- Consultoría
- Desarrollo
- Integraciones
- Testing
- Deployment

**Recurring Costs**
- Model inference
- Cloud infrastructure
- Databases
- Vector search
- Third-party subscriptions
- Monitoring
- Maintenance

**External Dependencies**
- Licencias del cliente
- API usage
- Vendor limitations
- Infrastructure requirements

Las licencias y consumos recurrentes deben aparecer **separados** del coste de implementación.

---

## 5. Plantilla para nuevas soluciones personalizadas

Si aparece una necesidad que no encaja exactamente en ninguno de los ocho patrones, creamos una solución nueva o combinamos patrones existentes.

La nueva ficha deberá contener:

- Nombre de la solución
- Business Objective
- Target Users
- Use Cases
- Core Operations
- Required Integrations
- Architecture Diagram
- Required Components
- Optional Modules
- Data Requirements
- Security Requirements
- Execution Flow
- Deliverables
- Acceptance Criteria
- Complexity Factors
- Estimated Effort
- Future Extensions

> No es necesario inventar un nuevo patrón por cada proyecto. Primero evaluamos si puede resolverse mediante una **combinación de patrones existentes**.

---

## 6. Posicionamiento comercial

Nuestra oferta se presenta en tres niveles:

| Nivel | Descripción |
|-------|-------------|
| **CONSULTING** | Diagnóstico, análisis, diseño y arquitectura de soluciones de IA e integración |
| **INTEGRATION SOLUTIONS** | Implementación de patrones reutilizables de integración, automatización y sistemas inteligentes |
| **CUSTOM DEVELOPMENT** | Desarrollo de aplicaciones y arquitecturas empresariales completamente personalizadas |

El catálogo es una herramienta para estructurar nuestra oferta, **no una limitación** a nuestra capacidad de diseñar soluciones específicas.

---

## 7. Regla final de diseño

Para cada proyecto:

1. Identificar el problema
2. Identificar las operaciones
3. Seleccionar uno o varios patrones
4. Definir componentes obligatorios y opcionales
5. Seleccionar proveedores compatibles con el ecosistema
6. Diseñar la arquitectura
7. Definir autonomía y seguridad
8. Establecer entregables y criterios de aceptación
9. Estimar implementación y operación
10. Implementar, evaluar y evolucionar

> La solución se diseña a partir de las **necesidades del negocio**.  
> Los patrones proporcionan estructura, los componentes proporcionan flexibilidad y el custom development proporciona libertad arquitectónica.
