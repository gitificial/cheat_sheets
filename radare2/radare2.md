## Radare 2 cheat sheet

### Basics
| Command          | Description                   |
| ---------------- | ----------------------------- |
| `r2 <binary>`    | Open a binary in analysis mode|
| `r2 -A <binary>` | Analyze binary automatically  |
| `r2 -d <binary>` | Open in debug mode            |
| `aaa`            | Perform full analysis         |
| `aa`             | Analyze functions and symbols |
| `afl`            | List functions                |
| `pdf @ <func>`   | Disassemble function          |
| `s <addr/sym>`   | Seek to address/symbol        |
| `q`              | Quit                          |
| `Ps my.r2`       | Save session                  |
| `Po my.r2`       | Load session                  |


### Analysis
| Command          | Description                           |
| ---------------- | ------------------------------------- |
| `af`             | Analyze current function              |
| `afl`            | List all functions                    |
| `afi`            | Show current function info            |
| `afn <new_name>` | Rename current function               |
| `agf`            | Show function graph                   |
| `agf @ sym.main` | Graph of specific function            |
| `pdf`            | Print disassembly of current function |
| `pd <N>`         | Disassemble next N instructions       |
| `pdr`            | Show function returns                 |
| `aaa`            | Perform full analysis                 |
| `aa`             | Basic analysis                        |
| `afvd`           | Show local variables in function      |
| `afv`            | View function variables               |

### Disassembly & Navigation
| Command               | Description                  |
| --------------------- | ---------------------------- |
| `pdf @ sym.func`      | Disassemble function         |
| `pd 20 @ 0xADDR`      | Disassemble 20 instructions  |
| `s sym.main`          | Seek to function             |
| `s 0xADDR`            | Seek to address              |
| `s+ 0x10` / `s- 0x10` | Move forward/back 0x10 bytes |
| `VV`                  | Visual mode with CFG         |
| `V`                   | Visual disassembly           |
| `VVv`                 | Visual function graph view   |

### Strings, Imports and Symbols
| Command    | Description    |
| ---------- | -------------- |
| `izz`      | List strings   |
| `iz~<str>` | Search strings |
| `ii`       | List imports   |
| `iij`      | Imports in JSON|
| `is`       | List symbols   |
| `iS`       | List sections  |
| `iI`       | Binary info    |
| `iR`       | RELRO info     |
| `iLl`      | PIE check      |
| `ic`       | List classes (if applicable) |

### Info & Headers
| Command | Description          |
| ------- | -------------------- |
| `i`     | Info about binary    |
| `iI`    | Detailed binary info |
| `iH`    | ELF headers          |
| `iS`    | Sections             |
| `iM`    | Memory maps          |
| `iR`    | RELRO check          |


### Cross-References (XREFs)
| Command          | Description                         |
| ---------------- | ----------------------------------- |
| `axt`            | Show references to current location |
| `axt <addr/sym>` | Show references to symbol/address   |
| `axf <addr>`     | Show references from address        |
| `axtj`           | JSON XREFs                          |
| `axtd`           | Data cross references               |

### Debugging
| Command             | Description                    |
| ------------------- | ------------------------------ |
| `ood`               | Restart binary in debug mode   |
| `db <addr>`         | Set breakpoint                 |
| `db sym.main`       | Break at main                  |
| `dcu`               | Continue until next breakpoint |
| `dc`                | Continue execution             |
| `ds` / `dso`        | Step into / step over          |
| `dr`                | Show registers                 |
| `dr eax=0x41414141` | Set register value             |
| `px <N> @ <addr>`   | Hexdump N bytes from address   |
| `dk`                | Kill debug process             |

### Memory & Stack
| Command            | Description                       |
| ------------------ | --------------------------------- |
| `pxw @ esp`        | Hexdump words at stack            |
| `x @ <addr>`       | Show string at address            |
| `wx <hex> @ addr`  | Write hex bytes at address        |
| `f tainted @ addr` | Set flag (e.g., tainted variable) |
| `pf <fmt> @ addr`  | Parse structure with format       |

### Flags & Comments
| Command              | Description            |
| -------------------- | ---------------------- |
| `f flag_name @ addr` | Create a flag          |
| `f- flag_name`       | Delete a flag          |
| `CC comment @ addr`  | Add comment at address |
| `CC- @ addr`         | Remove comment         |

### Searching
| Command         | Description               |
| --------------- | ------------------------- |
| `/ magic`       | Search for string "magic" |
| `/x 41414141`   | Search for hex 0x41414141 |
| `/c mov eax,`   | Search for opcode string  |
| `/v 0xdeadbeef` | Find value in memory      |

### Scripting & Automation
| Command                  | Description                   |
| ------------------------ | ----------------------------- |
| `#!pipe python`          | Start Python script inside r2 |
| `r2 -qi script.r2`       | Run script with quiet mode    |
| `r2 -e scr.prompt=false` | Disable prompt for scripting  |

### Evaluation & Arithmetic
| Command         | Description                         |
| --------------- | ----------------------------------- |
| `? 0x20 + 0x10` | Evaluate expression (result = 0x30) |
| `?v`            | Show variables used in expressions  |
| `?e`            | Evaluate expression in decimal      |

### Binary Patching (Write Mode)
| Command                    | Description                            |
| -------------------------- | -------------------------------------- |
| `wx 90 @ 0xADDRESS`        | Write hex bytes (e.g., NOP)            |
| `wa nop`                   | Assemble instruction at current offset |
| `s 0xADDR; wa jmp 0xADDR2` | Patch a jump                           |
| `wtf file.bin`             | Write current buffer to file           |


### ESIL (Emulation)
| Command | Description              |
| ------- | ------------------------ |
| `aei`   | Initialize ESIL          |
| `aeip`  | Set ESIL IP              |
| `aes`   | Step ESIL                |
| `aer`   | Show ESIL registers      |
| `aeim`  | Map memory for emulation |


