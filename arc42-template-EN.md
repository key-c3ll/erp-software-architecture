# Proyecto ERP – Arquitectura de Software

Este repositorio contiene la documentación de arquitectura del sistema ERP desarrollada como parte del taller de Arquitectura de Software.

La documentación sigue la plantilla **arc42** y describe la arquitectura del sistema ERP, con énfasis en el **Módulo de Compras**.

## Contenido
- Introducción y objetivos del sistema
- Restricciones de arquitectura
- Contexto del sistema
- Vista de bloques de construcción
- Vista de ejecución
- Vista de despliegue
- Glosario del dominio

Toda la documentación se encuentra en formato Markdown dentro de la carpeta `arc42`.

---
date: July 2025
title: Introduction and Goals
---

# Introduction and Goals

## Requirements Overview
El sistema ERP tiene como objetivo principal integrar y optimizar los procesos de negocio de una organización, centralizando la información y reduciendo errores operativos.

En este proyecto se aborda principalmente el **Módulo de Compras**, el cual permite gestionar proveedores, productos y órdenes de compra.

## Quality Goals
Los objetivos de calidad del sistema son:
- Usabilidad: interfaz intuitiva y fácil de usar.
- Mantenibilidad: código modular y bien estructurado.
- Confiabilidad: manejo adecuado de errores y validaciones.
- Rendimiento: tiempos de respuesta aceptables para operaciones comunes.

## Stakeholders

| Rol              | Contacto              | Expectativas |
|------------------|-----------------------|--------------|
| Administrador    | admin@empresa.com     | Gestión completa del sistema |
| Encargado Compras| compras@empresa.com   | Registrar y consultar órdenes |
| Docente          | docente@universidad.edu | Evaluación del diseño |
| Equipo Desarrollo| dev@grupoX.com        | Arquitectura clara y documentada |


# System Scope and Context

## Business Context
El sistema ERP es utilizado por distintos usuarios internos de la empresa para gestionar sus operaciones diarias.

Los usuarios interactúan con el sistema para:
- Registrar proveedores y productos
- Generar órdenes de compra
- Consultar información operativa

![Diagrama de Contexto](./images/c1_context.png)

## Technical Context
Desde el punto de vista técnico, el sistema ERP se comunica con:
- Navegadores web utilizados por los usuarios
- Una base de datos relacional PostgreSQL
- Sistemas externos opcionales, como un sistema contable

Las comunicaciones se realizan mediante protocolos HTTP/HTTPS.

# Building Block View

## Whitebox Overall System
El sistema ERP se compone de varios contenedores que interactúan entre sí para cumplir con los requisitos del negocio.

![Diagrama de Contenedores](./images/c2_containers.png)

### Aplicación Web
Responsable de la interacción con el usuario. Permite registrar y consultar información del sistema ERP mediante formularios y vistas.

### Backend ERP
Contiene la lógica de negocio del sistema. Gestiona los módulos de Compras, Facturación, Stock, Activos Fijos, Empleados y EIS.

### Base de Datos
Almacena de forma persistente toda la información del sistema, como productos, proveedores y órdenes de compra.

# Runtime View

## Escenario: Registrar un Producto
Este escenario describe el flujo de ejecución cuando un usuario registra un nuevo producto en el sistema.

1. El usuario ingresa los datos del producto en la aplicación web.
2. La aplicación envía la solicitud al backend.
3. El backend valida la información.
4. Los datos se almacenan en la base de datos.
5. El sistema confirma el registro exitoso.

![Diagrama de Secuencia](docimages)
# Deployment View

## Infraestructura
El sistema ERP puede desplegarse en un entorno centralizado compuesto por:

- Servidor Web para la aplicación frontend
- Servidor de Aplicaciones Java para el backend
- Servidor de Base de Datos PostgreSQL

Esta configuración es adecuada para un entorno académico y de pruebas.
 Glossary

| Término | Definición |
|--------|------------|
| ERP | Sistema de Planificación de Recursos Empresariales |
| Producto | Artículo que la empresa compra o vende |
| Proveedor | Entidad que suministra productos |
| Orden de Compra | Documento que formaliza una compra |
| Módulo de Compras | Componente del ERP encargado de gestionar compras |

