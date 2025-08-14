# pd

pure data

## Files

main file is `sandbox.pd`, the others are components made to be used in the main file.

- `bpm2clk.pd`, convert bpm to clock
  - inlets: toggle | bpm
  - outlets: 1 | 1/2 | 1/4 | 1/8 | 1/16 | 1/32 
- `mutation.pd`, a mutating 16-step midi sequencer.
  - inlet 1 (clock)
  - inlet 2 (proba) [0-100]: probability that each timestep is mutated
  - inlet 3 (force) [1-12]: strength of mutation (in semitones)
  - inlet 4 (fforce) [bool]: if full force, mutation will always be the force amount, if not, a random amount of semitones between 0 and force will be used
  - inlet 5 (lomidi) [0-127] minimum MIDI note allowed
  - inlet 6 (himidi) [0-127] maximum MIDI note allowed
  - outlet: midi note
  - **TODO: possibility to have a smaller sequence than 16 - possibilities to have CV / Gate sequences ?**
- `sr8.pd`, a 8 bit shift register.
  - inlet: banged float
  - outlets: left is most recent, right is the oldest
