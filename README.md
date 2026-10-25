# Sabores del Puerto - Prototipo de reservas

Este es el prototipo funcional de la Actividad 4. Es la continuación del proyecto que formulé en la Actividad 2: un sistema web para que el restaurante Sabores del Puerto (un caso hipotético, sin datos reales) maneje sus reservas sin depender de llamadas ni de WhatsApp.

- **Demo:** https://TU-USUARIO.github.io/sabores-del-puerto/
- **Repositorio:** https://github.com/TU-USUARIO/sabores-del-puerto

## Cómo correrlo

Descarga el repositorio (botón verde Code → Download ZIP), descomprímelo y abre el archivo `index.html` en el navegador. No hay que instalar nada. También puedes entrar directo al enlace de la demo.

## Qué se puede hacer

- **Cliente:** reservar una mesa, y con su código y correo consultar, modificar o cancelar la reserva.
- **Mesero:** ver qué mesas están libres, registrar reservas que llegan por teléfono o en persona, y marcar si el cliente llegó, no llegó o canceló.
- **Propietario:** lo mismo que el mesero, más los indicadores, la bandeja de correos y las pruebas automáticas.

Para entrar al panel del personal:

| Usuario | PIN |
|---|---|
| propietario | owner2026 |
| mesero | mesa2026 |

## Cómo lo imaginé

Como es un caso académico, tuve que inventar algunos datos del restaurante:

- 10 mesas: cuatro de 2 personas, cuatro de 4, una de 6 y una de 8.
- Abre de 12:00 a 22:00 y cada reserva dura 2 horas.
- Se aceptan grupos de 1 a 8 personas, con hasta 30 días de anticipación.
- La mesa se asigna sola: el sistema escoge la más pequeña que le sirva al grupo.

## Cosas que simulé

- Los correos no se envían de verdad. Quedan guardados en una bandeja de salida con su estado, y si falla el envío se puede reintentar.
- Los datos se guardan en el navegador (localStorage), así que no hay servidor ni base de datos. Por eso la verificación de doble reserva la hace la misma página; en un sistema real iría en la base de datos.
- El login del personal es solo demostrativo, no es una autenticación real.

## Pruebas

En el panel del propietario, en la pestaña Pruebas, hay un botón que ejecuta seis pruebas: que no se pueda reservar dos veces la misma mesa, que la disponibilidad se actualice al cancelar, que nadie cancele reservas ajenas, que el mesero no vea lo del propietario, que aguante 50 solicitudes al tiempo (10 entran y 40 se rechazan porque solo hay 10 mesas) y que un correo fallido se pueda reenviar.
