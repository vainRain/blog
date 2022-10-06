#### X86指令编码

x86 指令编码的核心是Opcode、ModRM 以及 SIB。Opcode 提供指令的操作码，ModRM 及 SIB 提供操作数的寻址模式。

###### Opcode

在 1 个字节的空间里：00 ~ FF，Prefix 与 Opcode 共同占用这个空间。因为指令不定长，解码器解码的唯一途径就是按指令编码的序列进行解码，关键是第 1 字节是什么？ 如：遇到 66h，它就是 Prefix，遇到 89h，它就是 Opcode。

Prefix 与 Opcode 共享空间的原因是：prefix 是可选的。在编码序列里，只有 Opcode 是不可缺少的，其它都是可选。这就决定了指令编码中的第 1 个字节对解码工作的重要性。

除了 1 个字节的 Opcode 外，还有 2 个字节的 Opcode 以及 3 个字节的 Opcode。第 2 个 Opcode 码由 0F 字节进行引导，这个 0F 被称为 escape prefix。即：2 个字节的 Opcode 码，其第 1 个 Opcode 必是 0F 字节。
