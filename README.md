# x86TestData
Test data for x86 instructions

## What is this?
This is a collection of x86 instructions executed with specific inputs to capture the outputs serialized as json. 
All of the test data was generated on the "Intel(R) Core(TM) i7-8700K" CPU.

## How is this useful?
If you are by any chance writing an x86 Emulator this can be useful to check if your emulation is correct.

## Format
```
 {
  "data": "0400",
  "inputs": {
   "rax": "7FFFFFFFFFFFFFFF",
   "rip": "E607C9EFF77F0000"
  },
  "instr": "add al, 0x00",
  "outputs": {
   "rax": "7FFFFFFFFFFFFFFF",
   "rip": "FC07C9EFF77F0000"
  }
 },
 ```
- ```data``` The bytes of the encoded instruction used to execute.
- ```inputs``` The data from the context used to execute the instruction. This will always use the biggest register size, this ensures that all bits are tested regardless of operand form.
- ```instr``` Readable form of the executed instruction.
- ```outputs``` The data from the context after executing the instruction.
### Gotchas
When registers like (E/R)IP/(E/R)SP are in the outputs it will always have it in the inputs aswell. To simplify testing you can use this to measure the distance of the values for when you can not emulate at the specific memory address, so instead of comparing the concrete value you should compare the distance from input to output.
When ```flags``` are in the inputs or outputs this refers to CPU ```EFlags``` or ```RFlags```

## NOTE
This is not the complete instruction set and it may lack a few specific flags/inputs. The tool used to generate this data is trying
to exhaust all possible combinations but sometimes breaks out because the search space is getting too big.

## Thanks
Special thanks to [AsmJIT](https://github.com/asmjit/asmjit) and [Zydis](https://github.com/zyantific/zydis) for their awesome projects that also made this possible.
