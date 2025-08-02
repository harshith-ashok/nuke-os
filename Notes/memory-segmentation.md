`real_segment = segment * 16 + offset`

```asm
org 0x7C00
```
this uses one of the available registry with no offset to start the program
## Segments in Registries
`CS` - currently runnign code segment
`DS` - data segment
`SS` - stack segment 
`FS` - current segment

segment: `[base + index * scale + displacement]`

- segment: CS, DS, ES, FS, GS, SS (DS if unspecified)
- base: (16 bits) BP/BX 
	- (32/64 bits) any general purpose register
- index: (16 bits) SI/DI
	- (32/64 bits) any general purpose register
- scale: (32/64 bits only) 1, 2, 4 or 8 
- displacement: a (signed) constant value

## Referencing
```asm
var: dw 100
	mov ax, var      ; copy offset to ax
	mov ax, [var]    ; copy memeory contents
```
