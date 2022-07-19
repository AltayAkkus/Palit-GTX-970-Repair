# Palit-GTX-970-Repair
A amateur boardview and repair manual for the Palit GTX 970 (Jetstream). 

I am not responsible for any damage on the GPU, or on your self.

Also, I am not a hardware engineer, and not a native english speaker. So if you spotted any mistakes, submit a PR, if it clarifies instead of making things more obscure I will accept it.

Just open up the Boardview in one tab, and this manual in another, go through this manual one by one, in this order.

If you need to measure resistance, turn the board off. If you need to measure voltage, turn the board on (unless this manual instructed you to not do it)
# Boardview
Soon.
# Check for shorts
## Fuze
Measure the resistance of the fuzes.

If they are blown (very high resistance), you know that something caused a high current, which blew them out.

You should not just bridge them, if you do and there still is a short, best case your PSU will die, worst case your GPU will catch flames.

You can measure both terminals, and one should be short to Ground, typically the Output.

12V is connected to the Input of the Fuze directly from your power supply, PCI-E or the PEG, a short there is very unlikely and frankly I would not know what to do. If the fuze is intact, it is connected to the rest of the internal power supply, so a short on the output means that something there is broken and is pulling the 12V rail to Ground, or would if the fuze was not blown.

If both terminals do not short to ground, check the other two options below, and if they also are not connected directly to Ground, maybe (!!!) your fuze is just faulty. This is very unlikely, though.


## PEG 6-Pin Connectors

1 to 6 should not be short to ground! (Measure ohms, connect one probe to the chassis or any other ground, the other one to the pins)

7 to 12 is ground, so you will detect a "short".

If short, your 12V power rail is short. Check other components to find it.

DO NOT CONNECT TO PSU IF IT IS SHORT!

## Shunt Resistor
This is the shunt resistor (Google it) for the PCI-E power supply.

Measure the lower pin (in the boardview) against Ground, if it is short, your PCI-E power supply runs short. Do not connect.

# Check power supply
The power from the mainboard (12V) first goes through the Gate Drivers. 

These Drivers "reduce" the voltage by modulating it, so the actual GTX 970 Chip can use it.

This voltage then is further "cleaned" by the Inductors. 
## Check Gate Driver Power Supply
Check each and every Gate Driver, if they get the 12V they need.

In order to do so, you have to measure the upper pad of the right Input MLCC (see Boardview) against Ground. 

You should get 12 Volts. If you don't, there is a problem with the power supply to the Gate Drivers, not with the Gate Driver itself.

The shown Gate Driver is a FDMF6823C, you should be able to find alternatives though.

## Check Gate Driver Power Output
The Gate Drivers output their voltage through their own Inductor (I won't explain which Inductor belongs to which driver, it's directly beside each other)

Measure the output (on the right side) against Ground. The PCB makes it seem like there are two pads, the Inductor has two terminals, two outputs, so don't bother, just measure the right (sided) one.

You should get a voltage of around 0,8V or 0,9V. 0,1 V or something like that is definitely not enough, so it seems that your Gate Driver is not putting out the correct voltage, or your Inductor is broken (unlikely, but it can happen, check via reading the resistance of it).

#Work in progress...




