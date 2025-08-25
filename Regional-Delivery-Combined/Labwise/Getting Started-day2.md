# Laboratorios Prácticos – Día 02
## Implementar la Protección Contra Amenazas con las Soluciones Microsoft Defender XDR

## Descripción General

En este laboratorio, mejorará sus capacidades de protección contra amenazas mediante la integración de Microsoft Defender for Cloud Apps, Microsoft Defender for Identity, Microsoft Sentinel y Power Automate. Comenzará conectando e integrando aplicaciones SaaS a Defender for Cloud Apps y configurando directivas de sesión para detectar y bloquear comportamientos de usuario de riesgo. A continuación, implementará la Gobernanza de Aplicaciones para identificar aplicaciones OAuth de alto riesgo y creará directivas de detección personalizadas para actividades sospechosas. Implementará sensores de Defender for Identity en controladores de dominio, simulará y detectará ataques basados ​​en la identidad, como Pass-the-Hash y DC Sync, y analizará líneas de tiempo de amenazas. Finalmente, implementará Investigación y Respuesta Automatizadas (AIR) para amenazas de identidad y creará flujos de trabajo de respuesta a incidentes con Microsoft Sentinel y Power Automate.

## Objetivos

- Integrar aplicaciones SaaS y configurar directivas de sesión con Microsoft Defender for Cloud Apps.
- Implementar Gobernanza de Aplicaciones para detectar aplicaciones OAuth de alto riesgo y crear directivas de detección personalizadas.
- Implementar sensores de Microsoft Defender for Identity e investigar amenazas basadas en la identidad y ataques de movimiento lateral.
- Integrar Defender for Identity con Microsoft Defender XDR y analizar las líneas de tiempo de los usuarios.
- Implementar Investigación y Respuesta Automatizadas (AIR) para amenazas a la identidad.
- Crear flujos de trabajo de respuesta a incidentes con Microsoft Sentinel y Power Automate.

## Requisitos previos

Los participantes deberían contar con:

- Familiaridad con las funcionalidades de seguridad y cumplimiento de Microsoft 365.
- Conocimiento de Microsoft Defender para Punto de Conexión (Endpoint) y Defender for Cloud Apps.
- Acceso a los permisos administrativos y de inquilino de Microsoft 365 proporcionados por el laboratorio.
- Conocimientos básicos de Acceso Condicional, incorporación de SaaS y configuración de directivas de seguridad.
- Conocimiento de los riesgos de TI en la Sombra (Shadow IT), seguridad de aplicaciones OAuth y gobernanza de archivos.
- Conocimientos básicos de KQL, gestión de incidentes y configuración de directivas de seguridad.
- Conocimiento de técnicas de ataque, búsqueda de amenazas y respuesta a incidentes.

## Explicación de Componentes

* **Microsoft Defender for Cloud Apps**: Un agente de seguridad de acceso a la nube (CASB) que proporciona visibilidad, control y protección para aplicaciones SaaS.
* **Cloud Discovery**: Una función que recopila y analiza datos de uso de las aplicaciones para detectar aplicaciones no autorizadas o de alto riesgo en la organización.
* **Informes de Instantáneas**: Archivos de registro cargados manualmente desde firewalls o servidores proxy que generan un análisis único de las aplicaciones detectadas.
* **Control de Aplicaciones con Acceso Condicional**: Integración con el Acceso Condicional de Microsoft Entra (Microsoft Entra Conditional Access) para controlar y supervisar las sesiones de las aplicaciones conectadas en la nube.
* **Supervisión de Archivos**: Capacidad para rastrear la actividad de los archivos, clasificar contenido confidencial y aplicar directivas de protección de datos en las aplicaciones conectadas.
* **Directivas de Sesión**: Controles en tiempo real aplicados a las sesiones de usuario, como el bloqueo de descargas o la restricción del acceso en función del cumplimiento de los dispositivos.
* **Gobernanza de Aplicaciones**: Supervisión avanzada de aplicaciones OAuth para detectar permisos de riesgo, publicadores no verificados y actividad inusual. 
* **Directivas de Detección**: Reglas personalizadas para identificar y responder automáticamente a comportamientos o configuraciones de alto riesgo en aplicaciones en la nube.
* **Microsoft Defender XDR**: Una suite de seguridad integrada para detectar, investigar y responder a amenazas en puntos de conexión, identidades, correo electrónico y aplicaciones en la nube.
* **Microsoft Sentinel**: Una solución SIEM y SOAR de nube nativa para la detección proactiva de amenazas, búsqueda y respuesta automatizada.
* **Simulación de Ataques**: Pasos prácticos para simular ataques de persistencia (modificación del registro) y de comando y control (consultas DNS).
* **Reglas de Análisis**: Reglas personalizadas en Sentinel para detectar actividad sospechosa y generar incidentes.
* **Búsqueda de Amenazas**: Creación y ejecución de consultas KQL para buscar amenazas de forma proactiva y marcar los hallazgos más relevantes.
* **Investigación de Incidentes**: Revisión de incidentes, mapeo de entidades y análisis de evidencia en Defender y Sentinel.
* **Mitigación**: Gestión de incidentes y alertas, aplicación de recomendaciones de seguridad y restauración de datos para un análisis más profundo.

Ahora, haga clic en **Siguiente** en la esquina inferior derecha para pasar a la siguiente página.
 
  ![Comience su Experiencia con Azure](../media/rd_gs_1_9.png)

### ¡Feliz aprendizaje!