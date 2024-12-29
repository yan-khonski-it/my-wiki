# RAM troubleshooting


Get ram status
`wmic memorychip get > outpuit.txt`


The result is
```
Attributes  BankLabel  Capacity     Caption          ConfiguredClockSpeed  ConfiguredVoltage  CreationClassName     DataWidth  Description      DeviceLocator  FormFactor  HotSwappable  InstallDate  InterleaveDataDepth  InterleavePosition  Manufacturer  MaxVoltage  MemoryType  MinVoltage  Model  Name             OtherIdentifyingInfo  PartNumber         PositionInRow  PoweredOn  Removable  Replaceable  SerialNumber  SKU  SMBIOSMemoryType  Speed  Status  Tag                TotalWidth  TypeDetail  Version  
2           BANK 0     17179869184  Physical Memory  3200                  1200               Win32_PhysicalMemory  64         Physical Memory  DIMM1          8                                      2                    1                   Kingston      1200        0           1200               Physical Memory                        HP32D4U8D8HC-16XR  1                                                 52CD60B4           26                3200           Physical Memory 0  64          128                  
2           BANK 1     17179869184  Physical Memory  3200                  1200               Win32_PhysicalMemory  64         Physical Memory  DIMM2          8                                      2                    1                   Kingston      1200        0           1200               Physical Memory                        HP32D4U8D8HC-16XR  1                                                 50CD60B6           26                3200           Physical Memory 1  64          128                  
2           BANK 2     17179869184  Physical Memory  3200                  1200               Win32_PhysicalMemory  64         Physical Memory  DIMM3          8                                      2                    2                   Kingston      1200        0           1200               Physical Memory                        HP32D4U8D8HC-16XR  1                                                 4FCE196D           26                3200           Physical Memory 2  64          128                  
2           BANK 3     17179869184  Physical Memory  3200                  1200               Win32_PhysicalMemory  64         Physical Memory  DIMM4          8                                      2                    2                   Kingston      1200        0           1200               Physical Memory                        HP32D4U8D8HC-16XR  1                                                 4ECD7BDD           26                3200           Physical Memory 3  64          128                  

```

Windows RAM diagnositic
Run terminal as administrator
Run command
`mdsched`
After PC reboots, it will run memory tests. If the test has errors, for example hardware failures, consider removing |RAM sticks one by one to find out if the problem is with the RAM stick or with the motherboard.
If the problem is with RAM, replace all RAM sticks to ensure that the RAM set is in sync.