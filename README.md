# HSHL-ELE22/23-Thesis Work-Improving Energy Efficiency in Object Identification in Smart Farming

Energy efficiency is not often talked about when it comes to neural network, overshadowed by other statistics such as accuracy. However, artificial intelligence are slowly being integrated to every part of life, which means, even for cloud applications, the power consumption of these algorithms can no longer be ignored. Especially in applications like smart farming, where the purpose is to improve revenue, if the cost of operating the server outweight the improvement in revenue then there is no point. Therefore, this bachelor thesis work would like to find and compare solutions to improve energy efficiency when running neural networks, with the focus on object identification and convolutional neural network.

## Goal and milestones:
The goal is to be able to find a solution that will provide the best energy efficiency that also will degrade the performance the least. In addition, there should be no proprietary solution as this is end-user based.

## Possible solutions:
- Implementation on FPGA: While GPUs are great for processing neural networks thanks to their parallelism and computation power, they are not the most energy efficient beacuse they are usually made for general purposes, even for data processing cards. Instead, implmenting an accelerator on FPGA, where the circuit can be customised specifically for the application, is believed to be better not only for energy efficiency, but also latency.

- Quantizing the model: Quantization of the model, instead of using full-precision floating point number and instead using fixed-point or integer, is known to reduce computational complexity and thus needing less computational power from the hardware. Therefore, it is believed to reduce the energy consumption. It is possible to further quantize the model also using binary weights and activation.

## Methodology:
- Control implemation of VGG19 CNN architecture, an architecture with one of the highest parameter count and computational requirements, on GPU via PyTorch.
- Quantize the model, one with int8 and the other with binary, test the efficiency on GPU.
- Create the hardware accelerator, deploy on FPGA and test efficiency.

## Tooling:
Since proprietary solution are not desired, and the enviroment to build the neural network of the stakeholder is PyTorch, the model will be quantized with the help of Brevitas and the hardware accelerator will be compiled using FINN, both made by Xilinx to work with Xilinx FPGA.
