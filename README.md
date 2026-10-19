# The Register Lab

An interactive x86-64 assembly course that runs entirely in the browser. Step through real instructions on a simulated CPU and watch values move between registers, flags, the stack and memory, with a plain-English explanation of every step.

**Live:** https://register-lab.vercel.app

## Features

- **8 lessons**: Registers, Math & flags, Loops, The stack, Functions (`call`/`ret` and the System V convention), Memory (arrays with `[base + index*8]` addressing), Bits, and a free-form Sandbox.
- **Built-in simulator** for a subset of x86-64 with 64-bit registers, ZF/SF/CF flags, a downward-growing stack, and a `.data` memory region (`dq` arrays).
- **Animated machine view**: values "fly" between operands, the ALU panel shows its arithmetic, and the low 16 bits of RAX are displayed bit by bit.
- **Narration** of each instruction, including why a conditional jump was or was not taken.
- **Controls**: Step (or press →), Run with a speed slider, Reset, and an editable code pane per lesson.
- **"Predict it" quizzes** in every lesson except the Sandbox: guess a register's final value before running.
- Progress and current lesson are remembered in `localStorage`.
- Light and dark themes (follows the system preference), responsive layout for mobile.
- Guards for common mistakes: parse errors, popping an empty stack, and an infinite-loop step limit.

### Supported instructions

`mov lea add sub imul inc dec neg and or xor shl shr cmp jmp je jz jne jnz jg jge jl jle ja jb push pop call ret nop hlt`

## Tech stack

A single `index.html` with HTML, CSS and vanilla JavaScript (64-bit arithmetic via `BigInt`). No build step and no JavaScript dependencies (fonts load from Google Fonts).

## Getting started

```bash
git clone https://github.com/Yafai01/register-lab.git
cd register-lab
```

Open `index.html` in a browser, or serve the folder with any static server, for example:

```bash
python -m http.server 8000
# open http://localhost:8000
```

It can be deployed as-is to any static host (it is deployed on Vercel).

## Project structure

```text
index.html   Lessons, simulator, and UI in one file
.gitignore   Ignores the local .vercel directory
```
