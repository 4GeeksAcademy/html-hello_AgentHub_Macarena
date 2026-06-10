# SPECS - Panel de Administracion AgentHub

## 1) Descripcion del producto
AgentHub es una plataforma SaaS donde empresas alquilan agentes de IA para tareas de negocio.
El usuario administrador necesita un panel interno para monitorear estado del negocio y gestionar usuarios, agentes, skills, contratos y errores operativos.

## 2) Stack tecnico y restricciones
- HTML semantico en un unico archivo principal: index.html.
- Tailwind CSS via CDN.
- JavaScript vainilla para toda la interactividad.
- Sin frameworks (React, Vue, etc.), sin jQuery, sin backend, sin llamadas a API.
- Datos hardcodeados en el frontend.
- Sin estilos inline y sin archivos CSS externos.

## 3) Especificaciones por seccion

### 3.1 Dashboard
1. Componente: Tarjeta de metrica.
   Contenido: 4 tarjetas en grilla 2x2 responsive con icono, etiqueta y valor hardcodeado para: ingresos totales del mes, perdida por descuentos y cupones, agentes activos y agentes fallando.
   Comportamiento: las tarjetas deben mantener su orden y visualizacion en desktop/tablet/mobile.

2. Componente: Colores de acento por metrica.
   Contenido: cada tarjeta usa un color de acento distinto y consistente con su tipo (ingresos, descuentos, activos, fallando).
   Comportamiento: en modo oscuro los colores conservan contraste legible.

3. Componente: Placeholder de grafico semanal.
   Contenido: debajo de las tarjetas, un bloque de ancho completo con borde discontinuo y etiqueta centrada indicando actividad semanal.
   Comportamiento: no requiere grafico real ni libreria de charts.

### 3.2 Gestion de usuarios
1. Componente: Tabla de usuarios.
   Contenido: minimo 5 filas hardcodeadas con nombre, email, plan y badge de estado.
   Comportamiento: scroll horizontal en pantallas pequenas.

2. Componente: Dropdown de acciones por fila.
   Contenido: boton de acciones con opciones Ver detalle y Eliminar.
   Comportamiento: abre/cierra al hacer click y se cierra al clickear fuera.

3. Componente: Modal de detalle de usuario.
   Contenido: al elegir Ver detalle, mostrar registro completo del usuario (nombre, email, plan, estado, empresa, fecha de alta).
   Comportamiento: cierre con boton y con click en backdrop.

### 3.3 Gestion de agentes
1. Componente: Lista de agentes.
   Contenido: minimo 4 agentes con nombre, propietario, badge de estado y resumen corto.
   Comportamiento: los datos de agentes deben ser consistentes con Contrataciones y Log de errores.

2. Componente: Skills colapsables por agente.
   Contenido: cada agente incluye una lista de skills inicialmente colapsada.
   Comportamiento: el control expandir/colapsar debe animar altura y opacidad de forma suave.

3. Componente: Dropdown de acciones por agente.
   Contenido: opciones Configurar y Eliminar.
   Comportamiento: Configurar abre un modal con textarea editable del prompt de sistema del agente; Eliminar cierra dropdown y marca la accion como simulada.

### 3.4 Skills
1. Componente: Catalogo de skills.
   Contenido: minimo 4 skills con nombre, descripcion breve y numero de agentes que la usan.
   Comportamiento: distribucion responsive por tarjetas.

2. Componente: Texto explicativo de contexto.
   Contenido: bloque explicando que una skill es una capacidad reutilizable que puede adjuntarse a un agente.
   Comportamiento: visible dentro de la misma seccion de Skills.

3. Componente: Dropdown de acciones por skill.
   Contenido: opciones Ver detalle y Eliminar por cada skill.
   Comportamiento: Ver detalle abre modal con descripcion ampliada y agentes asociados.

### 3.5 Contrataciones de agentes
1. Componente: Tabla de contratos.
   Contenido: minimo 4 contratos con cliente, agente, skills contratadas, fecha inicio, fecha fin e importe total pagado.
   Comportamiento: scroll horizontal en mobile.

2. Componente: Dropdown de acciones por fila.
   Contenido: opcion Ver detalle.
   Comportamiento: abre un modal con desglose del contrato.

3. Componente: Modal de desglose de contrato.
   Contenido: lista itemizada de skills contratadas con precio individual y total.
   Comportamiento: cierre con boton y con click en backdrop.

### 3.6 Log de errores
1. Componente: Tabla de errores.
   Contenido: minimo 6 entradas con timestamp, agente, badge de tipo/gravedad y descripcion breve.
   Comportamiento: badges con color por severidad (critico, warning, info).

2. Componente: Dropdown de acciones por entrada.
   Contenido: opciones Ver detalle y Marcar como resuelto.
   Comportamiento: Marcar como resuelto actualiza visualmente la fila a estado resuelto.

3. Componente: Modal de detalle de error.
   Contenido: vista extendida con traza simulada, contexto y recomendacion.
   Comportamiento: cierre con boton y con click en backdrop.

## 4) Inventario de componentes reutilizables
- Sidebar con links de navegacion y estado activo.
- Header superior con toggle oscuro/claro.
- Tarjeta de metrica.
- Tabla responsive con overflow horizontal.
- Badge de estado/severidad.
- Dropdown de acciones reutilizable.
- Modal reutilizable con titulo y contenido dinamico.
- Lista colapsable de skills por agente.
- Placeholder de grafico semanal.

## 5) Criterios de aceptacion
1. Existen exactamente 6 secciones funcionales accesibles desde sidebar: Dashboard, Gestion de usuarios, Gestion de agentes, Skills, Contrataciones de agentes y Log de errores.
2. El Dashboard muestra 4 tarjetas de metrica con icono, etiqueta y valor hardcodeado, mas un bloque placeholder de actividad semanal de ancho completo.
3. Gestion de usuarios contiene al menos 5 filas y cada fila tiene dropdown con Ver detalle y Eliminar.
4. Gestion de agentes contiene al menos 4 agentes y cada uno tiene skills colapsables con transicion visible.
5. Cada agente tiene dropdown con Configurar y Eliminar; Configurar abre modal con textarea editable del prompt del sistema.
6. La seccion Skills contiene al menos 4 cards y cada card tiene dropdown con Ver detalle y Eliminar.
7. La tabla de Contrataciones contiene al menos 4 contratos e incluye skills contratadas e importe total pagado.
8. El Log de errores contiene al menos 6 entradas con timestamp, agente, badge de severidad y descripcion.
9. Todos los dropdowns se cierran al hacer click fuera de su area.
10. Todos los modales se cierran con boton y al clickear el backdrop.
11. El toggle de modo oscuro/claro cambia todo el panel con clases dark de Tailwind y persiste estado en localStorage.
12. Los datos hardcodeados son consistentes entre secciones (mismos agentes en gestion, contratos y errores).
13. Se usan etiquetas semanticas (header, nav, main, section, table) y no hay estilos inline.
14. El layout es usable en escritorio y tablet, y las tablas permiten lectura en mobile mediante scroll horizontal.
