```markdown
# Peripheral Identification and Operations Project

This project allows users to detect and identify connected peripheral devices (such as USB, Bluetooth, and Wi-Fi devices), display detailed information about each device, and perform operations such as mounting, unmounting, ejecting, and configuring Bluetooth devices.

## Features

1. **Detect and Identify Connected Peripheral Devices**:
   - Lists connected USB devices.
   - Lists paired Bluetooth devices.
   - Lists Wi-Fi devices.

2. **Display Detailed Information about Devices**:
   - Displays detailed information about each USB device (vendor, product ID, etc.).
   - Displays detailed Bluetooth device information.

3. **Perform Operations on Devices**:
   - Mount a device to a specified mount point.
   - Unmount a device from a specified mount point.
   - Eject a device.
   - Configure Bluetooth devices (connect to Bluetooth devices).

## Prerequisites

Before running the project, make sure you have the following installed:

- **Linux-based OS** (Ubuntu or similar is preferred).
- **gcc**: For compiling C code.
- **bluetoothctl**: For interacting with Bluetooth devices (you must have Bluetooth enabled on your system).
- **iwconfig**: For listing Wi-Fi devices.
- **lsusb**: For listing USB devices.

To install these tools, you can run the following commands on a Debian-based system (like Ubuntu):

```bash
sudo apt update
sudo apt install bluetooth bluez iwconfig lsusb
```

## Directory Structure

The project structure is organized as follows:

```
PeripheralProject/
├── include/
│   ├── device_detection.h
│   ├── device_info.h
│   └── device_operations.h
├── src/
│   ├── device_detection.c
│   ├── device_info.c
│   └── device_operations.c
└── main.c
```

- `include/` - Contains all the header files, which declare the functions for device detection, device information, and device operations.
- `src/` - Contains the source files, which define the functions declared in the header files.
- `main.c` - The main entry point for the program where the user can select various operations.

## How to Run the Project

1. **Compile the Project**:
   - Navigate to the project directory in your terminal.
   - Run the following command to compile the project:
   ```bash
   gcc main.c src/device_detection.c src/device_info.c src/device_operations.c -o peripheral_project
   ```

2. **Run the Program**:
   - Once compiled, run the program using:
   ```bash
   ./peripheral_project
   ```

## How to Use the Program

- **Listing Connected Devices**:
    - Select option `1` to view all connected devices by type. The program will display information about USB, Bluetooth, and Wi-Fi devices.

- **Listing Detailed Device Information**:
    - Select option `2` to get detailed information about each device.
    - **For USB Devices**: Detailed information includes vendor and product IDs, which can help you identify the device.
    - **For Bluetooth Devices**: Displays paired Bluetooth devices along with available details.

- **Performing Device Operations**:
    - Select option `3`, then choose an operation to perform on a device.

    - **Mount a Device**:
        - Enter the device path (e.g., `/dev/sdb1`) and the mount point (e.g., `/mnt/usb`).
        - If you want to set a custom mount point, first create a directory using `mkdir /mnt/usb`, then specify this as the mount point.

    - **Unmount a Device**:
        - Enter the mount point where the device is currently mounted (e.g., `/mnt/usb`).

    - **Eject a Device**:
        - Enter the device path (e.g., `/dev/sdb`).

    - **Configure a Bluetooth Device**:
        - Before configuring,  the Bluetooth device can be paired or not paired. You can scan by entering:
        ```bash
        bluetoothctl
        scan on
        ```
        - After obtaining the MAC address of the device, input it into the program to pair/connect/both.

- **Exit**:
    - Select option `4` to end the program.

## Additional Information

- **Listing Device Mounting Points**:
    - Run the following command to list all mounted devices that start with `/dev`:
    ```bash
    mount | grep '^/dev'
    ```
    - This command lists devices and their mounting points.

- **Creating a Custom Mount Point**:
    - Use `mkdir` to create a custom mount directory. For example:
    ```bash
    mkdir /mnt/usb
    ```
    - Specify this path as the mount point when prompted.

- **Configuring Bluetooth Devices**:
    - To pair with a Bluetooth device, open `bluetoothctl`:
    ```bash
    bluetoothctl
    scan on
    ```
    - Once you have the MAC address of the device, you can input it into the program to establish a connection.

## Exit

- To end the program, select the exit option from the main menu.


