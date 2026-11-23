# Pruebas del módulo Personal médico (Guía 04)

Fecha: 23/11/2026 · Responsable: Carlos Olivera

Base de partida: `php artisan migrate:fresh --seed` y cuenta `medico2@posta.test` creada en Tinker (paso C.5).

| Caso | Resultado | Observación |
|------|-----------|-------------|
| CP01 | OK        | 5 profesionales activos con etiqueta verde y su n.° de citas (19, 20, 19, 32 y 25) |
| CP02 | OK        | Inactivos: 1 profesional · Todos: 6 profesionales |
| CP03 | OK        | Medicina general + «a»: solo aparecen profesionales de Medicina general |
| CP04 | OK        | Errores en español en DNI, colegiatura, nombres, apellidos y especialidad; la cuenta es opcional |
| CP05 | OK        | Colegiatura 123: «La colegiatura debe tener de 4 a 6 dígitos.» |
| CP06 | OK        | «Ya existe un profesional con este DNI.» y «Esta colegiatura ya está registrada.» |
| CP07 | OK        | Especialidad «Cardiología»: «Seleccione una especialidad de la lista.» |
| CP08 | OK        | Registrado con medico2: aviso verde y 6 profesionales activos |
| CP09 | OK        | Al registrar otro, el selector solo ofrece «Sin cuenta» |
| CP10 | OK        | Cambio de especialidad a Pediatría sin falsos duplicados |
| CP11 | OK        | Colegiatura de la Dra. Huamán: «Esta colegiatura ya está registrada.» |
| CP12 | OK        | Dra. Huamán desactivada: «Tiene 12 citas próximas por reprogramar.»; etiqueta Inactivo |
| CP13 | OK        | «Profesional activado.»; etiqueta Activo |
| CP14 | OK        | `route:list --path=personal-medico`: 7 rutas, ninguna DELETE |
