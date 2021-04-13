# x86TestData
Test data for x86 instructions

## What is this?
This is a collection of x86 instructions executed with specific inputs to capture the outputs serialized as json. 
All of the test data was generated on the "Intel(R) Core(TM) i7-8700K" CPU.

## How is this useful?
If you are by any chance writing an x86 Emulator this can be useful to check if your emulation is correct.

## NOTE
This is not the complete instruction set and it may lack a few specific flags/inputs. The tool used to generate this data is trying
to exhaust all possible combinations but sometimes breaks out because the search space is getting too big.

## Thanks
Special thanks to [AsmJIT](https://github.com/asmjit/asmjit) and [Zydis](https://github.com/zyantific/zydis) for their awesome projects that also made this possible.
