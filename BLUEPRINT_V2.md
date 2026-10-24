# Interrail Histórico — Blueprint V2 aprobado
Fecha: 24 octubre 2026. Referencia: maqueta de tres vistas aprobada por el usuario. Prioridad iPad Safari.

## Diseño
- Fondo #0B1821, tarjetas #142C3B, dorado #E7BD7B, texto crema #F5EEE3. Fotografías grandes, tipografía editorial en títulos y sistema para cuerpos.
- Navegación fija inferior en móviles/tabletas: Inicio, Libro, Ciudades, Rutas, Trenes, Viaje. La ficha de ciudad incluye subpestañas Historia, Itinerario, Mapa, Trenes, Alojamiento.
- Inicio: siete ciudades como mosaico fotográfico interactivo (dos columnas con última fila de tres), nombre y jornadas superpuestas; línea de ruta debajo.
- Ciudad: fotografía hero, título/fechas, dos tarjetas-capítulo, resumen de itinerario y presupuesto. Todos los botones llevan a vistas funcionales o señalan explícitamente pendientes.
- Viaje: buscador de trenes (origen/destino/fecha/2 adultos), Booking (ciudad/entrada/salida/2 adultos), mapa global, checklist, registros y presupuesto.

## Datos (fuente única)
city(id,name,country,image,lat,lng); day(id,city_id,sequence,period,chapter_id); chapter(id,title,sections,source_refs,status); place(id,city_id,name,lat,lng,verified); visit(id,day_id,place_id,position,notes,duration,status); rail_leg(id,from_id,to_id,date,time,operator,price,status); stay(id,city_id,checkin,checkout,name,price,status); expense(id,category,amount,paid); checklist(id,title,done). No inventar reservas.
Días 1–14: París, Berlín, Praga, Cracovia, Varsovia, Viena, Budapest, 2 cada una; objetivo máximo 16 días calendario por validar. Regreso Budapest–París en tren.

## Contrato de interacción
1. Tap ciudad → ficha de ciudad correcta y día inicial.
2. Tap día 1/2 → contexto, capítulo e itinerario coherente.
3. Capítulo → lector con fuentes y estado de completitud sin contenido ficticio.
4. Tap parada → mapa, orden y navegación externa si está localizada.
5. Trenes → búsqueda real externa, registrar la reserva elegida manualmente. No afirmar compra ni disponibilidad.
6. Alojamientos → enviar ciudad/fechas/2 adultos a Booking; registrar manualmente la selección.
7. Agenda/presupuesto → estados y costes compartidos, persistencia y backup.
8. Todo control visible tiene acción real; estados vacíos honestos.

## Limitaciones V2 incremental
GitHub Pages estático sin autenticación ni sincronización. LocalStorage es almacenamiento local, no seguridad para documentación personal. Mapas completos, trenes nocturnos verificados, 14 capítulos largos y datos en nube requieren fases posteriores.

## Pruebas mínimas
Inicio y 7 tarjetas; 14 días y sus capítulos; cambios de vistas; formularios de trenes y alojamiento; presupuesto; exportación; móvil iPad sin scroll horizontal. Confirmar Safari real antes de dar por completada la fase.
