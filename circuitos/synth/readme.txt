jemplos «síntesis / modular / MIDI» (lógica digital)
====================================================

Estos circuitos modelan bloques típicos de sintetizadores y modular
usando solo lógica digital del simulador (no hay audio analógico real).
Sirven para entender relojes, secuenciadores, patrones y latches de nota.

Cómo usar
---------
1. Archivo → Cargar (.json)
2. Selecciona relojes/osciladores → Acciones → Arrancar
3. Ejecutar (menú Ejecutar) para que la simulación avance sola
4. Interruptores y DIP: Acciones → Alternar (por bit en DIP)
5. Pulsadores: Acciones → Pulsar

Archivos
--------
clock_divider.json
  Divisor de reloj modular. MASTER → contador → salidas ÷2 ÷4 ÷8 ÷16.
  Análogo a un clock divider de Eurorack.

gate_sequencer_4.json
  Secuenciador de 4 pasos de puerta (gate). Contador 2 bits + decodificador.
  RUN habilita; RST reinicia al paso 1.

note_sequencer.json
  Secuenciador de «notas» (valores 0–15). Escala mayor en PATTERN_GENERATOR.
  La salida es un número de nota digital (CV cuantizado conceptual).

johnson_sequencer.json
  Contador Johnson (modo johnson). Patrón de unos que se desplazan;
  muy usado en secuenciadores analógicos clásicos.

ring_sequencer.json
  Ring counter de 8 pasos (one-hot). Solo un LED activo a la vez:
  típico «step lamp» de un secuenciador.

random_gates.json
  LFSR (generador pseudoaleatorio). Bits como gates/triggers aleatorios.
  Caos controlado / noise gates.

trigger_to_gate.json
  Monoestable 555: dispara un GATE de duración fija desde Acciones
  («Disparar pulso»). El LFO de referencia es un CLOCK aparte.

dual_osc_lfo.json
  Tres osciladores: VCO rápido, LFO lento (555 simétrico) y PWM
  (555 asimétrico high/low). Arranca cada uno desde Acciones.

rhythm_pattern.json
  Dos generadores de patrón rítmico (kick / hi-hat) sobre el mismo tempo.
  Edita el array "pattern" en el JSON para cambiar el ritmo.

arpeggiator_4.json
  Arpegiador de 4 notas fijas (0, 4, 7, 12) vía MUX + contador de paso.
  Cambia las CONSTANT para otras notas.

midi_note_latch.json
  Modelo simplificado de Note On: DIP de nota (7 bit, p.ej. 60 = C4) y
  velocidad (4 bit). Al pulsar NOTE ON se enganchan en registros.
  GATE hold es un interruptor manual (sustain conceptual).
  No es el protocolo MIDI serie completo; es la idea «capturar nota+vel».

midi_serial_shift.json
  Entrada serie bit a bit (como un byte MIDI). Ajusta SERIAL IN (0/1) y
  pulsa BIT CLK ocho veces; el shift register muestra el byte en hex/bin.
  Útil para entender el desplazamiento serie de un mensaje.

Limitaciones
------------
- No hay DAC ni salida de audio: los LEDs/monitores representan gates,
  clocks y números de nota.
- No hay filtros ni envolventes analógicas (ADSR real); el monoestable
  solo aproxima un gate de duración fija.
- MIDI aquí es didáctico (latch / shift), no un stack MIDI completo.
