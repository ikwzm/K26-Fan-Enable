K26-Fan-Enable
====================================================================================

This repository provides fan-enabled PL bitstreams for Kv260/Kr260 and script files to build them.

Overvier
------------------------------------------------------------------------------------

### Requirement

* Board: any of the following
  - Kv260
* OS: any of the following
  - https://github.com/ikwzm/ZynqMP-FPGA-Debian11
  - https://github.com/ikwzm/ZynqMP-FPGA-Ubuntu22.04-Console
  - https://github.com/ikwzm/ZynqMP-FPGA-Ubuntu22.04-Desktop

### Licensing

Distributed under the BSD 2-Clause License.

Build Bitstream file
------------------------------------------------------------------------------------

### Requirement

* Xilinx Vivado 2021.2

### Download K26-Fan-Enable

```console
shell$ git clone --depth 1 --recursive https://github.com/ikwzm/K26-Fan-Enable
shell$ cd K26-Fan-Enable
```

### Build K26-Fan-Enable.bin

#### Create Project

```
Vivado > Tools > Run Tcl Script... > fpga/create_project.tcl
```

#### Implementation

```
Vivado > Tools > Run Tcl Script... > fpga/implementation.tcl
```

#### Convert from Bitstream File to Binary File

```console
vivado% cd fpga
vivado% bootgen -image k26-fan-enable.bif.bif -arch zynqmp -w -o ../k26-fan-enable.bin
vivado% cd ..
```

#### Compress k26-fan-enable.bin to k26-fan-enable.bin.gz

```console
vivado% gzip k26-fan-enable.bin
```

