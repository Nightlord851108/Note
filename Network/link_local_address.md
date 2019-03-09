# Link Local Address(LLA)

## Convert between MAC address and IPv6 LLA

If Mac address = XX:XX:XX:XX:XX:XX

The IPv6 LLA = fe80::XYXX:XXff:feXX:XXXX
where Y = X XOR 2, which means inverse the second bit of X

For example:
IPv6 LLA = fe80::0288:ccff:fe12:3456
MAC address = 00:88:cc:12:34:56
