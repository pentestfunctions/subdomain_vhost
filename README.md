# Subdomains & Virtual Hosts Discovery Tool 🚀

This tool is designed to streamline the process of discovering subdomains and virtual hosts, making it easier for penetration testers and security researchers to uncover potential entry points in a target's web infrastructure. Utilizing `ffuf`, `zenity`, and the `seclists` wordlist, this bash script provides a user-friendly interface and powerful scanning capabilities.


## Overview 💻

Essentially it runs ffuf for subdomains for 5 seconds, checks their wordcount/size response etc - then based on duplicates it will rerun ffuf with those filters in place to get rid of the junk responses.

## Prerequisites 📋

Before you start, make sure you have the following dependencies installed on your system:

- `ffuf` - Fast web fuzzer written in Go
- `zenity` - Tool for displaying GTK+ dialogs from command-line or shell scripts
- `seclists` - Collection of multiple types of lists used during security assessments


- **Notes:** I didn't add recursion in but that's a simple modification. Easier to just run recursion against the subdomains you have found already.

### Installing Dependencies

#### On Debian-based systems
- **ffuf**
    ```bash
    sudo apt-get install -y ffuf
    ```
- **Zenity**
    ```bash
    sudo apt-get install -y zenity
    ```
- **Seclists**
    ```bash
    sudo apt-get install -y seclists
    ```

#### On Arch Linux (or derivatives)
- **ffuf**
    ```bash
    sudo pacman -S ffuf
    ```
- **Zenity**
    ```bash
    sudo pacman -S zenity
    ```
- **Seclists**
    ```bash
    sudo yay -S seclists
    ```

## Installation 🛠️

1. Download the script from this repository.
2. Make the script executable:
    ```bash
    chmod +x subdomains
    ```
3. Move the script to `/bin` to use it from anywhere:
    ```bash
    sudo mv subdomains /bin/subdomains
    ```

## Usage 📖

To start discovering subdomains, simply type `subdomains` in your terminal. A GUI prompt will ask for the target domain. Enter the domain name and let the tool do its magic!

```bash
subdomains
```

The tool will initially run a short scan to determine common sizes, words, and lines in responses. Based on this preliminary scan, it will then automatically refine its search parameters and perform a more targeted subdomain discovery operation.


## Acknowledgements 🙏

- [ffuf](https://github.com/ffuf/ffuf) for the powerful fuzzing engine.
- [Zenity](https://help.gnome.org/users/zenity/) for the GUI dialogs.
- [Seclists](https://github.com/danielmiessler/SecLists) for the extensive wordlists.

---

**Happy Hacking!** 🚀
