# UNIDAD-4-BASE-DE-DATOS-EJERCICIO-5
Tablas Principales y Atributos

alumno: Almacena la información de los estudiantes con los campos id_alumno (PK), nombre, apellido, dni y correo.

profesor: Registra los datos del plantel docente mediante matricula (PK), nombre, apellido, especialidad y telefono.

ciclo_lectivo: Define los períodos lectivos institucionales con id_ciclo (PK), anio y cuatrimestre.

carrera: Contiene las ofertas académicas con codigo_carrera (PK), nombre y plan_vigente (clave foránea hacia los planes de estudio).

plan_estudio: Administra los planes asociados a las carreras mediante id_plan (PK), nombre, anio_vigencia y codigo_carrera (FK).

asignatura: Catálogo de materias con codigo_asignatura (PK), nombre, carga_horaria, anio_curricula y id_plan (FK).

correlatividad: Tabla intermedia que maneja los requisitos previos entre materias con una clave primaria compuesta por (codigo_asignatura, codigo_correlativa).

comision: Agrupa las comisiones de cursado con id_comision (PK), cupo_maximo, comision_letra, además de las claves foráneas hacia asignatura, ciclo_lectivo y profesor (matricula).

inscripcion: Registra el vínculo de matriculación de los estudiantes en las comisiones con id_inscripcion (PK), condicion, nota_parcial_1, nota_parcial_2, id_alumno (FK) e id_comision (FK).

evaluacion: Almacena el historial de exámenes y calificaciones con id_evaluacion (PK), fecha, nota, tipo e id_inscripcion (FK).

Restricciones y Claves Foráneas (Foreign Keys)

fk_asignatura_plan: Relaciona asignatura(id_plan) con plan_estudio(id_plan).

fk_carrera_plan_vigente: Relaciona carrera(plan_vigente) con plan_estudio(id_plan).

fk_comision_asignatura: Relaciona comision(codigo_asignatura) con asignatura(codigo_asignatura).

fk_comision_ciclo: Relaciona comision(id_ciclo) con ciclo_lectivo(id_ciclo).

fk_comision_profesor: Relaciona comision(matricula) con profesor(matricula).

fk_correlativa_asignatura y fk_correlatividad_asignatura: Conectan los campos de correlatividad con la tabla asignatura(codigo_asignatura).

fk_evaluacion_inscripcion: Relaciona evaluacion(id_inscripcion) con inscripcion(id_inscripcion).

fk_inscripcion_alumno: Relaciona inscripcion(id_alumno) con alumno(id_alumno).

fk_inscripcion_comision: Relaciona inscripcion(id_comision) con comision(id_comision).

fk_plan_carrera: Relaciona plan_estudio(codigo_carrera) con carrera(codigo_carrera).

IMAGEN DE EJEMPLO DE CONSULTA:
<img width="1008" height="365" alt="image" src="https://github.com/user-attachments/assets/2c401bbb-5db9-425a-b211-6f44e65b95b0" />


