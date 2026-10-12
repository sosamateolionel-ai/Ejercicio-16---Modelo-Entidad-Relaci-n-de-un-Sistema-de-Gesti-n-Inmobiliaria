# Ejercicio 16 - Modelo Entidad-Relación de un Sistema de Gestión Inmobiliaria

## Descripción
Este ejercicio consiste en diseñar un modelo Entidad-Relación (DER) para un sistema de gestión inmobiliaria. El modelo permite administrar propietarios, propiedades, contratos de alquiler, inquilinos, empleados y el registro de pagos.

## Entidades y atributos

### 1. Propietario
Representa a los dueños de los inmuebles registrados en la inmobiliaria.
- **id_propetario**: identificador único del propietario.
- **dni**: documento nacional de identidad.
- **nombre apellido**: nombre y apellido del propietario.
- **telefono**: número de contacto.
- **mail**: correo electrónico.

### 2. Propiedad
Representa los inmuebles disponibles para alquiler.
- **id_propiedad**: identificador único de la propiedad.
- **codigo catastral**: código catastral del inmueble.
- **direccion**: dirección física de la propiedad.
- **ciudad**: ciudad donde se ubica.
- **tipo propiedad**: categoría del inmueble (ej. casa, departamento, local).
- **superficie**: metros cuadrados de la propiedad.
- **precio**: valor base de alquiler.
- **cantidad ambientes**: número de ambientes o habitaciones.

### 3. Inquilino
Representa a los arrendatarios que alquilan las propiedades.
- **id_inquilino**: identificador único del inquilino.
- **dni**: documento nacional de identidad.
- **nombre apellido**: nombre y apellido del inquilino.
- **telefono**: número de contacto.
- **email**: correo electrónico.

### 4. Empleado
Representa al personal de la inmobiliaria encargado de gestionar contratos.
- **id_empleado**: identificador único del empleado.
- **nombre apellido**: nombre y apellido del empleado.

### 5. Contrato
Representa el acuerdo legal de alquiler establecido sobre una propiedad.
- **id_contrato**: identificador único del contrato.
- **codigo catastral**: código de la propiedad asociada.
- **id_inquilino**: identificador del inquilino firmante.
- **id_empleado**: identificador del empleado gestor.
- **fecha inicio**: fecha de comienzo del contrato.
- **fecha fin**: fecha de finalización del contrato.
- **monto mensual**: valor de la cuota de alquiler.
- **deposito garantia**: monto retenido en garantía.

### 6. Pago
Representa los comprobantes o registros de los pagos mensuales de alquiler[cite: 10].
- **id_pago**: identificador único del pago[cite: 10].
- **id_contrato**: identificador del contrato asociado[cite: 10].
- **periodo abonado**: mes o periodo correspondiente al pago[cite: 10].
- **fecha pago**: fecha en que se efectivizó el pago[cite: 10].
- **medio pago**: método utilizado (ej. transferencia, efectivo)[cite: 10].
- **recargo demora**: importe adicional por pago fuera de término[cite: 10].

## Relaciones y cardinalidades
- **Propietario – Propiedad (Tiene / 1:N)**: un propietario puede registrar y poseer múltiples propiedades en administración[cite: 10].
- **Propiedad – Contrato (Genera / 1:1)**: una propiedad da lugar a la formalización de un contrato de alquiler vigente[cite: 10].
- **Contrato – Empleado (Cumple / 1:1)** y **Contrato – Inquilino (Hace / 1:N)**: vinculan el contrato con el empleado que lo administra y los inquilinos responsables[cite: 10].
- **Contrato – Pago (Produce / 1:N)**: un contrato de alquiler genera múltiples registros de pago periódicos a lo largo de su vigencia[cite: 10].

## Objetivo
Diseñar una base de datos para una agencia inmobiliaria que permita administrar la cartera de propietarios y propiedades, registrar la información de inquilinos y empleados, formalizar contratos de alquiler y llevar un control detallado de los pagos y cuotas abonadas.
