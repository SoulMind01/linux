# Steps to install linux kernel
- cd into linux source code directory
- Copy the current system's kernel config file (under /boot) to `.`
- Modify the configuration
   - Under `./.config`, modify the following:
     - `CONFIG_SYSTEM_REVOCATION_KEYs = ""`
     - `config_system_trusted_keys=""`
 - Generate config file
  ```bash
    sudo make -j$(nproc)
  ```
  - Install the kernal
    ```bash
      sudo make modules_install
      sudo make install
      reboot
    ```
  - verify installation
    ```bash
      uname -r
    ```
