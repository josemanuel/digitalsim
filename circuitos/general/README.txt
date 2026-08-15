Ejemplos para el Simulador de Lógica Digital
============================================

Carga cualquiera con Archivo → Cargar (.json) en el editor.

Archivos
--------
1. full_adder.json      — Sumador completo (puertas XOR/AND/OR). Alterna A, B, Cin.
2. d_flipflop.json      — Flip-flop D. Fija D, pulsa CLK (flanco de subida).
3. register_4bit.json   — Registro de 4 bits con EN y CLR. DIP = dato, pulsa CLK.
4. decoder_2to4.json    — Decodificador 2→4. S0/S1 eligen qué LED se enciende.
5. mux_4to1.json        — Multiplexor 4→1. D0–D3 son datos; S0/S1 eligen la salida.
6. counter_enable.json  — Contador 4 bits con enable. Arranca el CLOCK, usa EN/CLR.
7. alu_4bit.json        — ALU de 4 bits. OP (3 bits) selecciona la operación.
8. adder_7seg.json      — Sumador 4 bits + display de 7 segmentos.
9. ram_demo.json        — RAM 4 direcciones × 4 bits. WE=1 + pulso CLK escribe.
10. ttl_74138.json      — Chip 74138 (decodificador 3→8). EN debe estar a 1.

Notas
-----
- Tras cambiar interruptores o pulsar botones, usa «Un paso» o «Ejecutar»
  para propagar las señales (salvo que el componente ya escriba en vivo).
- En el panel derecho, sección Acciones: Alternar / Pulsar / Arrancar reloj.
- Los DIP switch tienen una acción por bit.
