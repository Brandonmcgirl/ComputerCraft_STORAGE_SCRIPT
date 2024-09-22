# CC_STORAGE_SCRIPT
# Refined Storage/Applied Energistics Sorting System with Danks and Functional Storage

## Overview
This Lua script integrates with **Refined Storage** and **Applied Energistics 2** to manage and automate item transfers between **Functional Storage**, **Danks**, and your main storage system. The system compares item quantities between the connected storage devices and your main RS/ME system, moving items accordingly to balance the storage. It supports advanced features like batch item transfers, status monitoring on an external monitor, and prioritization logic.

## Key Features
- **Bridge Support**: Connects via RS Bridges or ME Bridges to your main storage system.
- **Danks Integration**: Easily manage Danks (multiblock storages), supporting billions of items when maxed.
- **Functional Storage Integration**: Efficiently stores items in Functional Storage drawers.
- **External Monitor**: Provides visual feedback on transfer status, progress, and system state.
- **Batch Item Transfers**: Moves items in predefined batches to avoid overwhelming the system.
- **Pause/Resume Functionality**: Allows you to pause and resume transfers easily via the monitor.
- **Flexible Storage Capacity**: Supports up to 243 slots using Danks alone, with a total storage capacity of over 486 billion items!

## Basic Setup Instructions
1. **Connect Bridges**: Attach RS/ME Bridges using wired modems to the Advanced Computer on any side.
2. **Link Storage Devices**: Ensure your Danks and Functional Storage controllers are connected to the Advanced Computer via wired modems.
3. **Monitor**: Attach a 2x4 (width x height) monitor to the Advanced Computer for real-time system updates (this is not optional).
4. **Link Storage Buses**: Make sure that all storage devices (Danks and Functional Storage) are linked to your main RS/ME storage system using **External Storage Buses** (RS) or **Storage Buses** (ME).
5. **Danks Setup**: Fill each Dank slot one by one to ensure proper allocation and lock each slot (CTRL) to avoid overwriting.
6. **Functional Storage Setup**: Ensure each drawer contains at least one item type. Locked but empty drawers won’t work!

## Advanced Setup
- Configure peripheral sides (`cSide1`, `cSide2`, etc.) based on where your bridges and storage devices are located (north, south, east, west).
- Use F3 to determine the correct sides and ensure all cables are connected without overlapping to avoid detection issues.

## How It Works
1. **Item Comparison**: The script compares the quantity of items in your main system to the quantities in the attached Danks and Functional Storage.
2. **Item Transfer**: Based on the difference, the system will move items in batches to balance the overall storage.
3. **Mode Support**: Switch between **Dank Mode** and **Functional Storage Mode** to control different types of storage systems.

## Priority Logic
To ensure items move correctly between storage systems:
- The storage bus connected to the source storage (e.g., a disk drive) should have a **lower priority** than the destination storage (e.g., Danks or Functional Storage).
- Reversing this priority will prevent items from transferring!

## Performance
- One bridge supports 3 Danks and one Functional Storage Controller, allowing up to 243 slots.
- With max-level Danks, the system can handle nearly **700 billion items** across 324 slots (if Danks are used on all sides).

## Troubleshooting
- **Connection Issues**: Ensure cables are not overlapping. Overlapping connections can cause detection issues.
- **Storage Bus Issues**: Check your priorities. Incorrect priority settings can stop item transfers.
- For more support, please join our [Discord Support Server](https://discord.gg/GVtY9YcASR) and contact **FriedAlltheTime** for assistance.

## Example Usage
1. **Functional Storage**:
    - Make sure each drawer contains at least one item of the type to transfer.
    - For example, to move cobblestone, place cobblestone in one drawer and another item in a different drawer to avoid distributing items between empty slots.
  
2. **Danks**:
    - Place an item in a Dank slot and lock it (press `CTRL`) to start porting.
    - Press `RESUME` on the Dank mode monitor interface to begin item transfers.

## Warning
- **Single Bridge Usage**: The script currently sends transfer messages to all connected bridges. Using multiple bridges **won’t increase speed**—it only increases the number of Danks you can connect.
- Support for additional Danks and speed improvements may be added if the project gains enough support.

## Functions and System Details
### Peripheral Detection
- **refreshPeripherals()**: Detects and wraps ME/RS bridges and connected Danks/Functional Storage controllers. Ensures peripherals are wrapped correctly each cycle.

### Item Retrieval
- **getFSItems()**: Retrieves the list of items from Functional Storage.
- **getDankItems(dank)**: Retrieves item details from connected Dank storage.
- **getMEItems(meBridge) / getRSItems(rsBridge)**: Fetches item details from either ME or RS systems.

### Item Transfer Logic
- **transferItems()**: Moves items from the ME/RS system using predefined batch sizes. Transfers items based on the configured peripheral sides (cSide1, cSide2, etc.).
  
### Core Logic: Compare and Move Items
- **compareAndMoveItems()**: Main loop that compares item quantities and moves items if necessary.
  - Refreshes peripherals.
  - Retrieves and compares item counts.
  - Transfers items in batches.
  - Displays transfer progress on the monitor.

### Monitor Display
- **updateMonitor()**: Updates the external monitor with system status (paused or running), progress, and item counts.

### Pause and Resume Functionality
- **isPaused**: Toggles the transfer process between paused and running states via the monitor.

## Support and Feedback
If you encounter any issues or need help, please join our [support Discord](https://discord.gg/GVtY9YcASR) and contact **FriedAlltheTime** for support. 
## Note
If you prefer pastebin use pastebin get bdm2g5wi startup
or for github download use wget https://raw.githubusercontent.com/Brandonmcgirl/ComputerCraft_STORAGE_SCRIPT/main/startup startup


---

Thank you for using the sorting system! If you find this project helpful, consider leaving a star on the repository and providing feedback.
