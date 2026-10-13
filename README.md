# Sistema de Gestión de Emergencias SSR

**Dirección de Obras Hidráulicas (DOH)**  
**Subdirección Regional de Servicios Sanitarios Rurales – Región de La Araucanía**

## 1. Descripción general

El Sistema de Gestión de Emergencias SSR es una plataforma informática desarrollada para apoyar el registro, seguimiento, coordinación y análisis de emergencias que afectan a los Sistemas Sanitarios Rurales (SSR) de la Región de La Araucanía.

Su objetivo es centralizar la información operacional, facilitar el seguimiento de las contingencias y disponer de antecedentes actualizados para la toma de decisiones.

La aplicación funciona mediante un navegador web y permite que usuarios autorizados accedan a la información desde distintos dispositivos con conexión a Internet.

## 2. Funcionamiento del sistema

La plataforma organiza la gestión de emergencias en un proceso que comprende el registro inicial, seguimiento, actualización de antecedentes, resolución y generación de informes.

### Registro de emergencias

Permite ingresar nuevas incidencias asociadas a un SSR, incorporando antecedentes como:

- Identificación del sistema sanitario rural y comuna.
- Tipo de emergencia y nivel de prioridad.
- Descripción de la situación.
- Estado del abastecimiento de agua y suministro eléctrico.
- Número de arranques afectados.
- Fecha, ubicación y antecedentes complementarios.
- Fotografías y documentación de respaldo.

### Seguimiento y control

Cada emergencia dispone de un registro individual que permite incorporar actualizaciones, observaciones y antecedentes sobre las medidas adoptadas.

Los eventos pueden clasificarse según su estado de avance: reportado, en revisión, en gestión, en monitoreo, resuelto o cerrado.

El sistema conserva un historial de las actuaciones registradas, permitiendo consultar la evolución de cada emergencia y los usuarios que intervinieron.

### Generación de informes

La plataforma permite elaborar informes individuales y consolidados de situación, utilizando los antecedentes disponibles al momento de su emisión.

Entre sus funcionalidades se incluyen la generación de documentos PDF, exportación de información en formato CSV y conservación de registros históricos de informes.

### Notificaciones

El sistema contempla notificaciones por correo electrónico para informar eventos relevantes, tales como el ingreso y resolución de emergencias.

### Administración de usuarios

El acceso está organizado mediante tres perfiles:

- **Administrador:** gestión de usuarios, configuración, seguimiento y resolución de emergencias.
- **Reportante:** registro de nuevas emergencias y actualización de antecedentes dentro de los permisos establecidos.
- **Visualizador:** consulta de información sin facultades de modificación.

## 3. Lenguajes de programación y tecnologías

La aplicación utiliza tecnologías de desarrollo web que permiten separar la interfaz de usuario, la gestión de datos y los servicios de autenticación.

| Tecnología | Función |
|---|---|
| **TypeScript** | Lenguaje principal para la lógica de la aplicación, validación y manejo de datos. |
| **JavaScript** | Ejecución de funcionalidades e interacciones en el navegador. |
| **HTML5** | Estructura y presentación del contenido web. |
| **CSS3** | Diseño visual, distribución y adaptación de la interfaz a distintos dispositivos. |
| **React** | Biblioteca para construir los componentes interactivos de la plataforma. |
| **Vite** | Herramienta para desarrollo y compilación de la aplicación web. |
| **SQL / PostgreSQL** | Tecnología de base de datos utilizada por Supabase para almacenar y consultar información. |

Se utiliza también la biblioteca jsPDF para la generación de informes descargables en formato PDF.

## 4. Plataformas y servicios integrados

### GitHub

Plataforma utilizada para almacenar y administrar el código fuente, mantener un historial de modificaciones y controlar las versiones del proyecto.

Permite desarrollar mejoras, revisar cambios y conservar los antecedentes de evolución del sistema.

### GitHub Pages

Servicio de alojamiento web encargado de publicar la interfaz de la aplicación.

La publicación se realiza mediante un flujo automatizado de GitHub Actions que compila el proyecto al actualizar la rama principal del repositorio.

GitHub Pages publica la aplicación, pero no constituye la base de datos de las emergencias.

### Supabase

Plataforma utilizada para administrar los servicios de datos y autenticación.

Sus componentes comprenden:

- **PostgreSQL:** almacenamiento de los registros de emergencias, sistemas SSR, usuarios, seguimientos e informes.
- **Supabase Auth:** autenticación y administración de sesiones de usuarios.
- **Supabase Storage:** almacenamiento de fotografías y archivos asociados a los registros.
- **Row Level Security (RLS):** políticas de autorización para controlar el acceso a los datos.
- **Edge Functions:** ejecución de operaciones específicas que requieren procesamiento protegido en el servidor.

### Gmail API

Servicio integrado para el envío de notificaciones por correo electrónico, asociado a los eventos operacionales y administrativos contemplados por la plataforma.

## 5. Arquitectura general

El funcionamiento se organiza en tres componentes principales:

**Interfaz web:** desarrollada con React y TypeScript. Permite registrar, consultar y administrar la información desde un navegador.

**Servicios de datos:** proporcionados por Supabase, responsable de gestionar los registros, la autenticación, el almacenamiento de archivos y los controles de acceso.

**Publicación e integración:** GitHub Pages permite el acceso a la aplicación, mientras que los servicios de notificación se integran mediante funciones de servidor y Gmail API.

En términos generales, el usuario interactúa con la plataforma a través de su navegador. Las operaciones autorizadas se comunican con Supabase, donde se almacenan y recuperan los antecedentes. Los informes se elaboran a partir de la información disponible y las notificaciones se gestionan mediante los servicios integrados.

## 6. Seguridad de la información

La aplicación utiliza autenticación individual y distintos niveles de autorización para controlar el acceso a sus funcionalidades.

Los registros operacionales y archivos asociados se administran mediante los servicios de Supabase y sus mecanismos de seguridad.

Las contraseñas, credenciales privadas y claves administrativas no deben incorporarse al código fuente público. Las operaciones que requieren privilegios elevados deben ejecutarse mediante servicios protegidos y verificaciones de autorización.

## 7. Instalación y desarrollo

El proyecto requiere Node.js versión 22.13.0 o superior y el administrador de paquetes npm.

Para trabajar con una copia local del repositorio se utilizan los siguientes comandos:

| Comando | Descripción |
|---|---|
| `npm ci` | Instala las dependencias del proyecto. |
| `npm run dev:github` | Inicia el entorno local de desarrollo. |
| `npm run typecheck:github` | Verifica los tipos de TypeScript. |
| `npm run build:github` | Compila la aplicación para su publicación. |

Las configuraciones de servicios externos y las credenciales necesarias deben mantenerse en entornos protegidos.

## 8. Alcance del sistema

La plataforma constituye una herramienta de apoyo a la gestión operacional de emergencias en los Sistemas Sanitarios Rurales de La Araucanía.

Su información permite disponer de antecedentes consolidados, mejorar la trazabilidad de las actuaciones y facilitar la elaboración de reportes de situación para los procesos de coordinación y toma de decisiones.

Los registros reflejan los antecedentes ingresados y actualizados por los usuarios autorizados, por lo que su calidad y oportunidad dependen de la información disponible.

---

