## Shutting Down:
- `shutdown [OPTIONS] TIME [MESSAGE]`
- All logged-in users are notified that the system is going down.
- A time of day in the format hh:mm or the number of minutes to delay in the format +minutes.

## Network Configuration:
- `ifconfig [OPTIONS]`
- 
> The iwconfig command is similar to the ifconfig command, but it is dedicated to wireless network interfaces.
> The lo device is the loopback device, a special network device used by the system when sending network-based data to itself.
- `ping ipaddress/hostname`
- The ping command is used to verify connectivity between two computers.


## Viewing Processes:
- `Running a command results in something called a process.`
- Users who have administrative privileges can control any user processes, including stopping any user process.
- `ps`
- <img width="222" alt="image" src="https://user-images.githubusercontent.com/40174034/234070764-149beb71-82ce-4659-b69c-17a54926e737.png">
- The `ps -e & -f` option will display every process & more verbose details


## Package Management:
- Package management is a system by which software can be installed, updated, queried or removed from a filesystem.
### Installing Packages
- 1. sudo apt-get update
- 2. apt-cache search [keyword] (Package files are commonly installed by downloading them directly from repositories located on Internet servers. The Debian repositories contain more than 65,000 different packages of software. Before installing a package, it is good practice to refresh the list of available packages)
- 3. sudo apt-get install [package]
- 4. apt-get upgrade

### Removing Packages
- 
