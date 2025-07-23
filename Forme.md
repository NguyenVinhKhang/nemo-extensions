# Nemo Extensions Installation Guide

This guide provides instructions for installing the `nemo-python` and `nemo-terminal` extensions on a Debian/Ubuntu-based system.

## Installation Steps

1. **Update Package List and Install Dependencies**

   ```bash
   sudo apt update
   sudo apt install -y devscripts debhelper python3-all dh-python libglib2.0-dev gtk-doc-tools python3-gi-dev gir1.2-xapp-1.0 libnemo-extension-dev python-gi-dev
   ```

2. **Install Python pip**

   ```bash
   sudo apt install -y python3-pip
   ```

3. **Install Meson**

   Install Meson (>= 0.56) using pip. This will be installed in `~/.local/bin`.

   ```bash
   pip3 install --user --upgrade meson
   ```

4. **Build and Install nemo-terminal**

   ```bash
   cd ../nemo-terminal
   debuild -uc -us
   sudo dpkg -i ../nemo-terminal*.deb || sudo apt install -f -y
   ``` 
5. **Build and Install nemo-python if need**

   ```bash
   cd nemo-python
   debuild -uc -us
   sudo dpkg -i ../nemo-python*.deb || sudo apt install -f -y
   ```
