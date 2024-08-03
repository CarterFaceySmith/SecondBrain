This works even for the root partition, which cannot be done when in your Linux environment to my knowledge due to being mounted and busy at all times.

## Step-by-step

1. Download GParted to your [[Linux]] environment via your package manager.
2. Ensure free space is available and adjacent to the partition you want to resize (see contiguous section in [[Memory]]).
3. If unable to create or see free space, enter Windows environment.
	1. Run disc/partition manager and resize your Windows drive to create space.
	2. Re-enter Linux environment.
4. Create a live USB of GParted by downloading and flashing the iso file to a USB.
5. Reboot into the USB via your motherboard firmware settings menu or alternative.
6. Enter the simple GParted GUI environment and resize the unmounted Linux partition.
7. Reboot, removing the USB to enter your standard boot sequence.