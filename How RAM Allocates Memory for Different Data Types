  How RAM Allocates Memory for Different Data Types
  RAM is just a big array of memory cells, where each cell stores a small amount of data (typically 1 byte). When a variable is declared, the system assigns a memory block based on its type and size.

    
  1. How Different Types Are Stored
    Each data type requires a different number of bytes:
    
    int (Integer) → Typically 4 bytes
    double (Floating-point number) → Typically 8 bytes
    char (Character) → 1 byte
    bool (Boolean) → Usually 1 byte
    ============================================================================================
  2. Memory Allocation Process
    When you declare a variable (e.g., int age = 45;), the system does the following:
    
    Finds a free memory block of size sizeof(int) (usually 4 bytes).
    Assigns an address to the variable (e.g., 0x7fff5694dc58).
    Stores the binary representation of 45 into those 4 bytes.
    ============================================================================================
  3. Example: Storing int age = 45;
    Binary representation of 45 (in 4 bytes)
    00000000 00000000 00000000 00101101  (45 in binary)
    Stored in 4 consecutive bytes in RAM.
    ============================================================================================
      Breaking it Down
    This is a 32-bit (4-byte) representation of int 45.
    Each group of 8 bits (1 byte) is stored in one memory cell.
    Since int takes 4 bytes, it occupies 4 memory cells in RAM.
