# Packet Tracer – Troubleshooting Serial Interfaces

## Objectives
- Diagnose and repair issues at the Physical Layer.
- Diagnose and repair issues at the Data Link Layer.
- Diagnose and repair issues at the Network Layer.

## Topology
- Telco Router (DCE)
- R1, R2, R3, R4 (DTE Routers)

## Addressing Table
| Device | Interface | IP Address     | Subnet Mask       | Default Route   |
|--------|-----------|----------------|-------------------|-----------------|
| Telco  | S0/0/0    | 64.100.34.17   | 255.255.255.252   | N/A             |
| Telco  | S0/0/1    | 64.100.34.21   | 255.255.255.252   | N/A             |
| Telco  | S0/1/0    | 64.100.34.25   | 255.255.255.252   | N/A             |
| Telco  | S0/1/1    | 64.100.34.29   | 255.255.255.252   | N/A             |
| R1     | S0/0/0    | 64.100.34.18   | 255.255.255.252   | 64.100.34.17    |
| R2     | S0/0/1    | 64.100.34.22   | 255.255.255.252   | 64.100.34.21    |
| R3     | S0/0/0    | 64.100.34.26   | 255.255.255.252   | 64.100.34.25    |
| R4     | S0/0/1    | 64.100.34.30   | 255.255.255.252   | 64.100.34.29    |

## Steps

### Part 1: Physical Layer
1. Check cabling with `show controllers`.
2. Correct any reversed or misconnected cables.
3. Ensure serial ports are not administratively down.

### Part 2: Data Link Layer
1. Set clock rate on Telco’s DCE interfaces.
2. Verify encapsulation is HDLC on all serial links.

### Part 3: Network Layer
1. Verify IP addressing matches the table.
2. Correct any misconfigured IPs (no overlaps or broadcast addresses).
3. Test connectivity between all routers with ping.

## ✅ Expected Result
- All routers should establish connectivity via the Telco router.
- Pings between R1, R2, R3, and R4 should succeed.
