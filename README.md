# WebGL-UDP for Unity

## Overview
**WebGL-UDP** permite comunicación UDP bidireccional en Unity, incluyendo compatibilidad con WebGL mediante emulación (WebSockets/WebRTC), ya que los navegadores no permiten sockets UDP directos.

## Propósito
Resolver la limitación de WebGL respecto a los sockets UDP, manteniendo una API consistente usando el paquete **Unity Transport**.

## Componentes Principales
- `UdpClient.cs`: Envía mensajes UDP a un endpoint remoto.
- `UdpServer.cs`: Escucha y procesa mensajes entrantes.
- `UdpServerManager`: Coordina cliente, servidor y la interfaz UI.
- **UI**: Campos de entrada y botones vinculados a eventos (`SendMessage()`).
  
![image](https://github.com/user-attachments/assets/84ca1119-d86f-474c-ba11-ee7588385c3a)

## Arquitectura
- Comunicación entre Unity y endpoints UDP externos.
- Emulación UDP en WebGL vía WebSockets/WebRTC.
- Uso de `NetworkDriver`, `NetworkPipeline` y `NetworkEndpoint`.
  
![image](https://github.com/user-attachments/assets/65c8c8f7-a25f-4b7a-a557-f6f88e6c067e)

## Comandos Disponibles
- `/help`: Muestra los comandos disponibles.
- `/name <nombre>`: Cambia el nombre del usuario.

## Parámetros Configurables
| Parámetro     | Tipo      | Descripción                            |
|---------------|-----------|----------------------------------------|
| `ipAddress`   | `string`  | Dirección IP destino                   |
| `port`        | `int`     | Puerto de envío/recepción              |
| `UI Elements` | Unity UI  | Referencias a InputField y botones     |

## Proceso de Configuración
1. Instalar el paquete `Unity Transport`.
2. Crear los scripts `UdpClient`, `UdpServer`.
3. Crear el GameObject `UdpServerManager`.
4. Asignar parámetros y vincular UI.
5. Configurar eventos de botones (`OnClick`).

## Flujo de comunicación
![image](https://github.com/user-attachments/assets/1f3d0e96-fad4-4b1b-baec-e8d09cc12ffc)

## Subida a WebGL y configuración de base de datos en la nube

- Después de exportar el proyecto Unity como WebGL, se suben los archivos a un hosting web.
- En este caso, se utilizó **awardspace.com** para alojar una base de datos en la nube.
- Desde Awardspace se pueden gestionar archivos PHP que se conectan correctamente a la base de datos.
- Esto permite que el frontend WebGL haga llamadas a los scripts PHP para interactuar con la base de datos remota.

## Características
- Comunicación UDP bidireccional.
- Compatible con WebGL.
- Integración sencilla con UI de Unity.
- API unificada para todas las plataformas.

