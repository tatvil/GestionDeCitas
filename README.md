# GestionDeCitas
Gestion de citas para pequeños comercios como peluquerias, entrenadores personales, profesores particulares, medicos, psicologos, nutricionistas

# Aplicación de Gestión de Agenda para Pequeños Negocios

## Descripción

Esta aplicación está diseñada para ayudar a pequeños negocios a gestionar sus citas y contactos de manera eficiente. Puede ser utilizada por entrenadores personales, profesores de yoga, psicólogos, peluquerías y otros profesionales que necesiten organizar su agenda y enviar recordatorios de citas a sus clientes.

## Características Principales

- **Gestión de Citas**: Los pequeños empresarios pueden programar, modificar y cancelar citas.
- **Envío de Recordatorios por WhatsApp**: Envío automático de recordatorios o confirmaciones de citas por WhatsApp, incluyendo un archivo en formato `.ics` para añadir la cita al calendario del cliente.
- **Base de Datos de Clientes**: Una tabla de personas que almacena la información básica del cliente, como nombre y número de teléfono.
- **Integración de API**: Se utiliza la API de WhatsApp para el envío de mensajes.
- **Formato de archivo .ics**: El sistema genera un archivo `.ics` para que los clientes puedan añadir la cita a sus calendarios personales.
  
## Base de Datos

La base de datos contiene una tabla clave para la gestión de contactos:

### Tabla `personas`
| Campo       | Tipo       | Descripción                           |
|-------------|------------|---------------------------------------|
| `id`        | INT (PK)   | Identificador único de la persona     |
| `nombre`    | VARCHAR    | Nombre completo del cliente           |
| `telefono`  | VARCHAR    | Número de teléfono (para WhatsApp)    |
| `propietario`  | INT   | id del propietario del negocio, así podemos utilizar la misma base de datos para distintos negocios |

### Tabla propietarios de negocios 
| Campo           | Tipo       | Descripción                              |
|-----------------|------------|------------------------------------------|
| `id`            | INT (PK)   | Identificador único de la cita           |
| `persona_id`    | INT (FK)   | Identificador del cliente                |
| `fecha_hora`    | DATETIME   | Fecha y hora de la cita                  |
| `servicio`      | VARCHAR    | Tipo de servicio (entrenamiento, sesión, etc.) |
| `notificado`    | BOOLEAN    | Indica si se ha enviado el recordatorio   |

### Tabla `citas`
| Campo           | Tipo       | Descripción                              |
|-----------------|------------|------------------------------------------|
| `id`            | INT (PK)   | Identificador único de la cita           |
| `nombre`        | VARCHAR    | nombre                                   |
| `email`         | VARCHAR    | Su email                                 |
| `empresa`       | VARCHAR    | Para el "El día x tiene una cita en {nombre de empresa} |

## Instalación

1. Clona el repositorio:
    ```bash
    git clone https://github.com/tatvil/GestionDeCitas.git
    ```

2. Configura la base de datos MySQL:
    - Ejecuta el archivo SQL para crear las tablas necesarias.

3. Configura la API de WhatsApp:
    - Regístrate en WhatsApp API y obtén tus credenciales.
    - Configura el envío de mensajes y el formato `.ics`.

## Funcionalidades Futuras

- Applicacion para Windows
- Aplicacion para moviles Android
- Gestión de facturación y pagos.
- Recordatorios por SMS o email.
- Sistema de notificaciones internas para los dueños del negocio.

## Contribuciones

Las contribuciones son bienvenidas. Si deseas colaborar, abre un issue o envía un pull request.
