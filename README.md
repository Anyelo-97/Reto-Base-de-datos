# Reto-Base-de-datos Gestión de Proyectos

## Descripción

Este reto implementa una base de datos para gestionar proyectos y empleados, manteniendo una estructura en Tercera Forma Normal (3FN).

## Relaciones

* Empleados 1:N Proyecto_Empleado
* Proyectos 1:N Proyecto_Empleado
* Relación N:N entre Empleados y Proyectos

## Script SQL

```sql
CREATE TABLE Proyectos(
  ID_proyecto INT PRIMARY KEY,
  Nombre_Proyecto VARCHAR(255) NOT NULL,
  Fecha_Inicio DATE NOT NULL,
  Fecha_Finalizacion DATE NOT NULL,
  CHECK (Fecha_Finalizacion >= Fecha_Inicio)
);

CREATE TABLE Empleados (
  ID_empleado INT PRIMARY KEY,
  Nombre VARCHAR(255) NOT NULL
);

CREATE TABLE Proyecto_Empleado (
  ID_proyecto INT,
  ID_empleado INT,
  PRIMARY KEY (ID_proyecto, ID_empleado),
  FOREIGN KEY (ID_proyecto) REFERENCES Proyectos(ID_proyecto),
  FOREIGN KEY (ID_empleado) REFERENCES Empleados(ID_empleado)
);
```

## Diagrama
https://drive.google.com/file/d/1c_fPb07D73dyWZCB7Ao6lCKBmngmMZNx/view?usp=sharing
