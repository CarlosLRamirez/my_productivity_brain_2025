---
created: 2024-12-18T10:01:03
modified: '"2024-12-18 10:04", "3tc/G12T+6"'
date: 2024-12-18
type:
  - minuta
aliases: 
tags:
  - Escala24x7
IDProyecto: 
---
### Seguimiento

```dataviewjs
let projectID = dv.current().IDProyecto;

// Función para filtrar tareas según las condiciones comunes
function filterTasks(tasks) {
   return tasks
        .where(t => t.tags.includes("#followup"))
        .where(t => !t.tags.includes("#backlog"))
     .where(t => !t.completed)
        
}

// Obtener todas las páginas que tienen tareas relacionadas con el ID del proyecto
let tasksByProperty = filterTasks(dv.pages().where(p => p.IDProyecto === projectID).file.tasks);

// Obtener todas las tareas que tienen el tag del ID del proyecto
let tasksByTag = filterTasks(dv.pages().file.tasks.where(t => t.tags.includes("#id" + projectID)));

// Combinar ambas listas de tareas y eliminar duplicados usando un Set
let combinedTasks = [...new Set([...tasksByProperty, ...tasksByTag])];

// Mostrar la lista de tareas
dv.taskList(combinedTasks, { asOf: dv.date("today") });
 ```
## Fecha de Reunion
2024-12-18

## Asistentes

### Cliente
* 
### Escala24x7
- Carlos Leonel Ramírez
-  Francisco Brito
- Iliana Estupinian
- Maria Fernanda Juarez
- Nelson Mora
- Oscar Romeo Ramírez

## Agenda
* 
## Temas Discutidos
* Roles:
	* Se intentó copiar los roles de MC
	* Lider Técnico
	* 
* Davivienda Costa Rica
	* Va dentro de la organización de CAM
* 

## Puntos de Acción acordados
- 

## Proxima Reunión
*   

---
Template: [[06 Minuta de Reunion Template]]
Author: Carlos Ramírez - 2024