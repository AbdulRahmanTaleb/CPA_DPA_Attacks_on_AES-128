# CPA_DPA_Attacks_on_AES-128
This project is the implementation of CPA &amp; DPA Attacks applied to AES-128 algorithm, in C language

## Usage
You can execute the code using the command : 
```bash
./main knownkeys_file plaintexts_file traces_file CPA/DPA [ind_bit (if attack is DPA, ind_bit in [0;7] is to partition traces)]
```

Data files (knownkey, plaintexts and traces) should be in a raw format (int8, int8, float32). The program considers that its the same key
used for all traces, so only 1 key entry (the first one) will be read from knownkeys_file.

To execute a CPA attack, run : 
```bash
./main knownkeys_file plaintexts_file traces_file CPA
```

To execute a DPA attack (and bit index 2 to partition the traces for example), run :
```bash
./main knownkeys_file plaintexts_file traces_file DPA 2
```

To modify the number of traces, the size of traces, or the sub-interval of samples in the traces to consider in the attack, modify defined constants in attack.h file:
```
NB_TRACES: Defines the number of traces

SIZE_TRACE : Defines the total number of samples in each trace

SUBINTERVAL1 and SUBINTERVAL2 : Defines the subinterval of samples of each trace to consider for the attack [SUBINTERVAL1; SUBINTERVAL2], if all samples are to be considered use SUBINTERVAL1 0  and SUBINTERVAL2 (SIZE_TRACE - 1)
```


