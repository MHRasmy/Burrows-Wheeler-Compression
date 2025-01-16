# Burrows-Wheeler Compression

## Overview
This project implements the Burrows-Wheeler compression algorithm, a three-step process that efficiently compresses text files by leveraging the principles of sorting, frequency reduction, and entropy encoding. The project integrates the Burrows-Wheeler Transform (BWT), Move-to-Front (MTF) encoding, and Huffman coding to achieve significant compression rates while ensuring reversibility.

---

## Features
- **Burrows-Wheeler Transform (BWT):**
  - Transforms input text to group similar characters, optimizing it for compression.
  - Supports efficient inverse transformation for decompression.
  
- **Move-to-Front (MTF) Encoding:**
  - Converts clustered characters into small integers.
  - Ideal for creating frequent symbols suitable for Huffman encoding.
  
- **Huffman Coding:**
  - Encodes integers from MTF into binary code with variable lengths.
  - Ensures minimal storage for frequent symbols.
  
- **Compression Pipeline:**
  - Compresses input text files into binary format.
  - Calculates compression ratio and execution time.

- **Decompression Pipeline:**
  - Restores original text from compressed files.
  - Logs the execution time for each decompression step.

---

## File Structure
```
├── Node.cs              # Defines the Node class used for Huffman Tree representation.
├── PriorityQueue.cs     # Implements a priority queue using a binary heap for Huffman coding.
├── HuffmanTree.cs       # Constructs and manages the Huffman Tree for encoding and decoding.
├── Program.cs           # Main logic for compression and decompression pipelines.
```

---

## How It Works
### Compression
1. **Burrows-Wheeler Transform (BWT):**
   - Cyclically permutes the input string.
   - Sorts the permutations alphabetically.
   - Extracts the last column and the index of the original string.

2. **Move-to-Front Encoding (MTF):**
   - Encodes the BWT result into a sequence of integers based on frequency.

3. **Huffman Encoding:**
   - Constructs a Huffman Tree using the frequency of integers from MTF.
   - Outputs compressed binary data.

4. **Execution Time Logging:**
   - Tracks and logs the time for each compression step.

### Decompression
1. **Huffman Decoding:**
   - Reconstructs the Huffman Tree and decodes the binary data.

2. **Move-to-Front Decoding (MTF):**
   - Restores the original sequence of characters.

3. **Inverse Burrows-Wheeler Transform:**
   - Reconstructs the original text from the decoded sequence.

---

## Input/Output
- **Input:** Text file to be compressed.
- **Output:**
  - Compressed binary file.
  - Decompressed text file identical to the original input.
  - Compression ratio and execution times.

---

## Usage
1. Clone this repository:
   ```bash
   git clone https://github.com/username/B_wheeler.git
   cd B_wheeler
   ```

2. Open the project in Visual Studio.

3. Build and run the project:
   - For CLI execution, configure the `Main` method in `Program.cs`.
   - For GUI-based execution, run the `WinFormsApp1` project.

4. Use the compression pipeline to compress a text file:
   - Select a file via the GUI or specify it in the code.

5. Decompress the binary file to validate the pipeline.
