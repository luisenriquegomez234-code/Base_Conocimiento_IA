# Skill: Reglas de Arquitectura y Gobierno

## 🎯 Propósito
Definir principios, estándares y reglas obligatorias para el desarrollo, validación y generación de soluciones técnicas dentro del entorno Base_Conocimiento_IA.

---

## 📥 Alcance de Aplicación
Esta skill es de cumplimiento **OBLIGATORIO y TRANSVERSAL** en todos los casos:

- Generación de código
- Validación de datos
- Diseño de arquitectura
- Integraciones
- Automatizaciones

---

## ⚙️ Reglas de ejecución

### 1. Arquitectura (Regla 01)

#### 1.1 Separación de Responsabilidades (SoC)
- Capa de Presentación/API → manejo de entrada/salida (sin lógica de negocio)
- Capa de Negocio (Servicios) → lógica del dominio
- Capa de Datos (Repositorios) → acceso a datos exclusivamente

#### 1.2 Inversión de Dependencias
- Los módulos deben depender de abstracciones, no implementaciones
- Evitar `new` dentro de lógica de negocio
- Priorizar inyección de dependencias

#### 1.3 Modularidad
- Arquitectura basada en módulos autocontenidos
- Cada módulo debe poder evolucionar sin afectar otros
- Evitar acoplamiento fuerte entre módulos

---

### 2. Nomenclatura (Regla 02)

#### 2.1 Principios
- Nombres descriptivos y semánticos
- Prohibidas abreviaciones ambiguas
- Consistencia en todo el sistema

#### 2.2 Código limpio
- Cada función = una única responsabilidad
- Prohibido uso de números mágicos → usar constantes
- Comentarios solo para explicar el "por qué", no el "qué"

---

### 3. Manejo de errores (Regla 03)

#### 3.1 Control de errores
- Prohibido `catch {}` vacío
- Manejo explícito de errores en operaciones críticas

#### 3.2 Tipado de errores
- Usar errores específicos (`ValidationError`, `DatabaseError`, etc.)
- Incluir contexto relevante en el error

#### 3.3 Logging
- Registrar errores técnicos internamente
- Prohibido exponer detalles técnicos al usuario final

---

### 4. Seguridad (Regla 04)

#### 4.1 Principio Zero Trust
Todo input externo es no confiable por defecto

#### 4.2 Validación de entrada
- Validar y sanitizar todos los datos
- Usar esquemas tipados (Zod, Joi, Pydantic)

#### 4.3 Prevención de ataques
- Prohibido SQL dinámico sin protección
- Escapar datos en frontend (XSS)

#### 4.4 Manejo de secretos
- Prohibido hardcodear credenciales
- Uso obligatorio de variables de entorno
- Aplicar mínimo privilegio

---

### 5. Inmutabilidad (Regla 05)

#### 5.1 Variables
- Uso preferente de inmutabilidad (`const`)
- Prohibido `var`

#### 5.2 Estructuras
- Evitar mutaciones directas
- Preferir `.map()`, `.filter()`, spread operator

#### 5.3 Estado
- Minimizar estado global
- Controlar cambios mediante mecanismos centralizados

---

### 6. Rendimiento (Regla 06)

#### 6.1 Acceso a datos
- Prohibido N+1 queries
- Evitar `SELECT *`

#### 6.2 Procesamiento
- Operaciones pesadas → background jobs
- Uso de paralelismo cuando sea posible

#### 6.3 Estructuras de datos
- Elegir estructura adecuada según el caso

---

### 7. Documentación y Ejecución del Agente (Regla 07)

#### 7.1 Flujo obligatorio
1. Análisis
2. Planificación
3. Ejecución
4. Validación

#### 7.2 Uso de herramientas
- Consultar contexto antes de asumir
- Usar skills existentes antes de crear soluciones nuevas

#### 7.3 Manejo de conflictos
- Si una instrucción viola reglas → detener ejecución
- Explicar conflicto citando la regla
- Proponer alternativa segura

---

### 8. Testing (Regla 08)

#### 8.1 Cobertura
- Lógica crítica → pruebas obligatorias

#### 8.2 Diseño testeable
- Código desacoplado
- Uso de mocks

#### 8.3 Estándar
- AAA (Arrange, Act, Assert)
- Nombres descriptivos en pruebas

---

### 9. Configuración (Regla 09)

#### 9.1 Variables de entorno
- Toda configuración externa debe ir en `.env`
- Validación centralizada (fail fast)

#### 9.2 Entornos
- Evitar lógica condicional compleja por entorno
- Usar abstracciones

#### 9.3 Seguridad
- `.env` debe estar en `.gitignore`

---

## 🧠 Lógica de decisión

- Violación de regla → corrección obligatoria
- Prioridad en conflictos:
  1. Seguridad
  2. Integridad de datos
  3. Estabilidad
  4. Rendimiento

---

## 📤 Resultado esperado

- Código modular, mantenible y escalable
- Sistemas seguros
- Procesos auditables

---

## 🚫 Restricciones

- Prohibido ignorar errores
- Prohibido hardcodear valores sensibles
- Prohibido romper modularidad
- Prohibido omitir validaciones

---

## 🔗 Relación con otras skills

- Esta skill es base obligatoria
- Todas las demás skills deben cumplir estas reglas