# TEST CASE CPR 77 - Crear vista de detalle de assessment para assessment by team en estado "In Progress"

**Equipo:** Tracking Operation  
**Analista de calidad:** Santiago Alejandro Sepúlveda Palacio  

---

## ✳️ Feature: Ver y gestionar el detalle del assessment en estado "In Progress"

---

### ✅ Scenario: Acceder a la vista de detalle del assessment
**Given:** el usuario está en la vista "Assessments"  
**When:** hace clic en un assessment en estado "In Progress"  
**Then:** debe ser redirigido a la vista de detalle del assessment por equipo  
**And:** debe ver Team, Year, Semester, Status y Progress  

**Resultado:** Caso de prueba exitoso ✅

---

### ✅ Scenario: Ver cálculo del progreso en la vista
**Given:** el assessment tiene `evaluation_results` registrados  
**Then:** el progreso debe calcularse como:  
> "n° de resultados en estado Completed / n° de empleados activos con perfiles operativos"

**Resultado:** Caso de prueba exitoso ✅

---

### ✅ Scenario: Mostrar lista de `evaluation_results` en la vista
**Given:** el usuario está en la vista de detalle  
**Then:** debe verse la lista de empleados con sus `evaluation_results`

**Resultado:** Caso de prueba exitoso ✅

---

### ✅ Scenario: Ver botón "Close Evaluation" habilitado en estado In Progress
**Given:** el assessment está en estado "In Progress"  
**Then:** el botón "Close Evaluation" debe estar habilitado en la parte superior derecha

---

### ✅ Scenario: Botón "Close Evaluation" deshabilitado si no aplica
**Given:** el assessment no está en estado "In Progress"  
**Then:** el botón "Close Evaluation" debe estar deshabilitado o no visible  

**Resultado:** Caso de prueba exitoso ✅

---

### ✅ Scenario: Mostrar advertencia si hay resultados pendientes
**Given:** hay `evaluation_results` que no están en estado Completed  
**When:** el usuario hace clic en "Close Evaluation"  
**Then:** se debe mostrar el mensaje:  
> "There are still pending evaluations..."

**Resultado:** Caso de prueba exitoso ✅

---

### ✅ Scenario: Mostrar confirmación antes de cerrar evaluación
**Given:** todos los resultados están en estado Completed  
**When:** el usuario hace clic en "Close Evaluation"  
**Then:** se debe mostrar el mensaje:  
> "Are you sure you want to close this assessment? Once closed, you will no longer be able to modify the evaluation results for any employee."

**Resultado:** Caso de prueba exitoso ✅

---

### ✅ Scenario: Cambiar estado a "Completed" tras confirmación
**Given:** todos los resultados están en estado Completed  
**When:** el usuario confirma el cierre del assessment  
**Then:** el estado del `assessment by team` debe cambiar a "Completed"

**Resultado:** Caso de prueba exitoso ✅

---

### ✅ Scenario: Comportamiento posterior al cierre
**Given:** el assessment está en estado "Completed"  
**Then:** 
- los botones "Start Evaluation" y "Close Evaluation" deben estar deshabilitados  
- los `evaluation_results` deben mostrarse en modo solo lectura  
- los botones de edición o eliminación deben estar inactivos

---

🔐 **Nota:** Todos los escenarios fueron verificados y considerados exitosos.
