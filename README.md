# Outback_Tuning
## This is my repository for the tuning of my 2005 Outback XT Manual. First time using GitHub so wish me luck!

## To do:
- [x] Get logcfg.txt working at a basic level and able to capture ssmk data.
- [ ] [Get AEM Serial Logging working](https://github.com/jayge91/Outback_Tuning/issues/5)
- [ ]
- [ ]


# Notes on logcfg.txt:
- Definitions from RomRaider translate pretty easily to logging parameters once converted to a format the OP2.0 can read.

- OBD Pins 8, 12, and 16 can be read via ADC.
- OBD pins can be set manually to ground or a voltage using [setpinvoltage=X(Pin),(-2:GND)(-1:HighImp)(5000-25000:mV)] (Not sure on how this is implemented or where yet).
- OP2.0 can read serial on the 2.5mm jack (ring) using type=ascii.

## Switches are read in the same way a parameter is read except that it will return up to 8 individual ON/OFF flags in the individual bits of the return byte. 
```
Switch P0x061
7 -----------------------
6 AT Vehicle ID
5 Test Mode Connector
4 Read Memory Connector
3 -----------------------
2 -----------------------
1 -----------------------
0 -----------------------
```
```
Switch P0x062
7 Neutral Position Switch
6 Idle Switch
5 -----------------------
4 Intercooler AutoWash Switch
3 Ignition Switch
2 Power Steering Switch
1 Air Conditioning Switch
0 -----------------------
```

```
Switch P0x063
7 Handle Switch
6 Starter Switch
5 Front O2 Rich Signal
4 Rear O2 Rich Signal
3 Front O2 #2 Rich Signal
2 Knock Signal 1
1 Knock Signal 2
0 Electrical Load Signal
```

```
Switch P0x064
7 Crank Position Sensor
6 Cam Position Sensor
5 Defogger Switch
4 Blower Switch
3 Interior Light Switch
2 Wiper Switch
1 Air-Con Lock Signal
0 Air-Con Mid Pressure Switch
```

```
Switch P0x065
7 Air-Con Compressor Signal
6 Radiator Fan Relay #3
5 Radiator Fan Relay #1
4 Radiator Fan Relay #2
3 Fuel Pump Relay
2 Intercooler Auto-Wash Relay
1 CPC Solenoid Valve
0 Blow-By Leak Connector
```

```
Switch P0x066
7 PCV Solenoid Valve
6 TGV Output
5 TGV Drive
4 Variable Intake Air Solenoid
3 Pressure Sources Change
2 Vent Solenoid Valve
1 P/S Solenoid Valve
0 Assist Air Solenoid Valve
```

```
Switch P0x067
7 Tank Sensor Control Valve
6 Relief Valve Solenoid 1
5 Relief Valve Solenoid 2
4 TCS Relief Valve Solenoid
3 Ex. Gas Positive Pressure
2 Ex. Gas Negative Pressure
1 Intake Air Solenoid
0 Muffler Control
```

```
Switch P0x068
7 -----------------------
6 -----------------------
5 -----------------------
4 -----------------------
3 Retard Signal from AT
2 Fuel Cut Signal from AT
1 Ban of Torque Down
0 Request Torque Down VDC
```

```
Switch P0x069
7 Torque Control Signal #1
6 Torque Control Signal #2
5 Torque Permission Signal
4 EAM Signal
3 AT coop. lock up signal
2 AT coop. lean burn signal
1 AT coop. rich spike signal
0 AET Signal
```

```
Switch P0x120
7 -----------------------
6 ETC Motor Relay
5 -----------------------
4 -----------------------
3 -----------------------
2 -----------------------
1 -----------------------
0 -----------------------
```

```
Switch P0x121
7 Clutch Switch
6 Stop Light Switch
5 Set/Coast Switch
4 Rsume/Accelerate Switch
3 Brake Switch
2 -----------------------
1 Accelerator Switch
0 -----------------------
```
