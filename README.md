# Gobuster Deluxe

Welcome to **Gobuster Deluxe** - a powerful, enhanced version of the popular Gobuster tool, designed to streamline and improve your directory and file brute-forcing experience. This script automates multiple wordlist usage, offers flexible protocol options, and ensures clean and organized output, all while keeping the user in control with intuitive command-line flags.

## TODO
- Add the feature to enum vhosts/subdomains

## Features

- **Protocol Flexibility**: Easily switch between HTTP and HTTPS protocols.
- **Custom Wordlists**: Start your brute-forcing with your custom wordlist before falling back on default ones.
- **Clean and Organized Output**: Results are automatically cleaned and saved in a user-friendly format.
- **Interactive Control**: Cancel the script anytime with CTRL + C without losing your progress.
  - The script is designed to handle this interruption gracefully, ensuring that any results collected up to that point are saved properly, and any temporary resources are cleaned up.
- **Robust and User-Friendly**: Includes detailed help and usage instructions.


# Install

```
git clone https://github.com/suljov/Gobuster-deluxe
cd Gobuster-deluxe
chmod +x Gobuster-deluxe.sh
sudo cp Gobuster-deluxe.sh /usr/local/bin/gobuster-deluxe 
```

# Usage

```
$ gobuster-deluxe --help
Usage: gobuster-deluxe <ip> [--https] [--cw <custom_wordlist>] [extra_gobuster_options]

Options:
  <ip>                     The target IP address or domain.
  --https                  (Optional) Use HTTPS protocol instead of HTTP.
  --cw <custom_wordlist>   (Optional) Use a custom wordlist before the default wordlists.
  [extra_gobuster_options] (Optional) Additional options for the gobuster command.

Examples:
  gobuster-deluxe 192.168.1.1
  gobuster-deluxe example.com --https
  gobuster-deluxe 192.168.1.1 --cw /path/to/custom_wordlist.txt
  gobuster-deluxe example.com --https --cw /path/to/custom_wordlist.txt --delay=500ms --hide-length -x ph,txt,zip
```

# Examples

#### Basic Usage
```
gobuster-deluxe example.com
```
#### Using HTTPS
```
gobuster-deluxe example.com --https
```
#### With Custom Wordlist
```
gobuster-deluxe example.com --cw /path/to/custom_wordlist.txt
```
#### With Extra Gobuster Options
```
gobuster-deluxe example.com --https --cw /path/to/custom_wordlist.txt --delay=500ms --hide-length -x ph,txt,zip
```
# The ability to customize
This tool is customizable in the script for easily add or remove wordlists. 
by simply edit the file by typing:
```
sudo gedit /usr/local/bin/gobuster-deluxe
```
and find the this part on line `67`:
```
# List of wordlists
WORDLISTS=(
    "/usr/share/wordlists/seclists/Discovery/Web-Content/quickhits.txt"
    "/usr/share/wordlists/seclists/Discovery/Web-Content/directory-list-2.3-medium.txt"
    # Add more wordlists here as needed
)
```
you can simply add how many you want if you have a custom wordlists you always use etc:
```
# List of wordlists
WORDLISTS=(
    "/usr/share/wordlist/myonly-owrdlist.txt"
)
```
its up to use what wordlist it uses. 


# Cleaning Up
To ensure that partial results are not lost, the tool saves and cleans the output on-the-fly. Even if you cancel the script using CTRL + C, the results gathered up to that point will be cleaned and saved.



# Acknowledgments
Gobuster: The original tool by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart) which this script builds upon.




