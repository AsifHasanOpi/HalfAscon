# HalfASCON

A lightweight hardware implementation and analysis project based on the ASCON authenticated cipher, optimized for a 32-bit datapath.

## Overview

This repository contains the design and analysis of **HalfASCON**, a scaled-down variant of the [ASCON](https://ascon.iaik.tugraz.at/) lightweight authenticated cipher. The original ASCON algorithm is designed for 64-bit operations. This project adapts it for efficient 32-bit hardware implementations, making it suitable for even more constrained embedded environments.

## Key Features

- **32-bit Datapath Optimization:** Redesigns ASCON's linear diffusion layer to operate efficiently on a 32-bit word size, as original rotation constants (>32) are not directly applicable.
- **Optimized Rotation Constants:** New constants were carefully selected based on:
  - Branch Number
  - Avalanche Effect
  - Avoidance of Symmetry
  - A mix of small and large shifts
- **Hardware Obfuscation Research:** Explores the application of logic locking techniques on the HalfASCON design to provide protection against IP piracy and unauthorized use.
- **Netlist-Level Analysis:** Utilizes open-source obfuscation/deobfuscation tools like **RANE** and **NEOS** for security evaluation.

## Results

Analysis confirms that the adapted linear diffusion layer for HalfASCON maintains strong cryptographic properties like diffusion and avalanche effect, crucial for security, while being tailored for a 32-bit architecture.

## Future Work

- Complete ASIC implementation and tapeout
- Side-Channel Analysis (SCA) evaluation on the locked design
- Explore more robust locking techniques compatible with sequential elements (flip-flops) using formal tools like **Cadence JasperGold**

## Contributors

- **[Asif Hasan](https://www.asifhasan.com/home)** - Initial design and analysis

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- The ASCON team for the original, well-designed cipher
