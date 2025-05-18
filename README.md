# Configuración de Comunicación UDP en Unity

## Requisitos Iniciales
1. **Instalación del Transport**  
   Primero es necesario instalar el paquete `Transport` dentro de Unity para habilitar la funcionalidad de red.

## Estructura de Scripts
2. **Scripts Esenciales**  
   Se deben crear dos scripts fundamentales:
   - `UdpClient.cs`  
   - `UdpServer.cs`  

3. **GameObject Contenedor**  
   - Crear un GameObject llamado `UdpServerManager` en la escena.  
   - Este actuará como contenedor para referenciar ambos scripts (`UdpClient` y `UdpServer`).

## Propósito de los Scripts
- Los scripts gestionan la comunicación UDP bidireccional:  
  - `UdpServer`: Escucha mensajes entrantes.  
  - `UdpClient`: Envía mensajes a un endpoint configurado.  

## Configuración de la Interfaz
4. **Referencias en Inspector**  
   Asignar al GameObject `UdpServerManager`:  
   - **Elementos de UI**:  
     - `InputField` para introducir mensajes.  
   - **Parámetros UDP**:  
     - Dirección IP (`string`).  
     - Puerto (`int`).  

5. **Integración con Botones**  
   - Arrastrar el GameObject `UdpServerManager` al evento `OnClick()` de los botones relevantes.  
   - Vincular a las funciones públicas de los scripts (ej: `SendMessage()` en `UdpClient`).
