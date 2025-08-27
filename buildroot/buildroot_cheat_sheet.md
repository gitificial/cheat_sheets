## Buildroot cheat sheet

### Basic Commands

| Command | Description |
|---------|-------------|
| `make` | Build the default target (e.g., the default configuration). |
| `make menuconfig` | Open the configuration menu (text-based UI). |
| `make xconfig` | Open the configuration menu (Qt-based GUI). |
| `make nconfig` | Open the configuration menu (ncurses-based UI). |
| `make defconfig` | Set up default configuration for the architecture. |
| `make all` | Build everything in Buildroot. |
| `make clean` | Clean up the build directory (removes the build output). |
| `make distclean` | Complete cleanup (removes everything, including configuration). |
| `make world` | Build everything (similar to `make all`). |
| `make <package_name>` | Build a specific package. |
| `make <image_name>` | Build a specific image. |

### Configuring Buildroot

| Command | Description |
|---------|-------------|
| `make menuconfig` | Configure Buildroot settings for your target. |
| `make BR2_DEFCONFIG=<file>` | Use a custom defconfig file. |
| `make BR2_EXTERNAL=<dir>` | Specify an external Buildroot directory. |
| `make <target>_defconfig` | Use a pre-defined configuration (e.g., `x86_64_defconfig`). |

### Target Architecture and Options

| Command | Description |
|---------|-------------|
| `make ARCH=<architecture>` | Specify the architecture (e.g., x86_64, arm, aarch64). |
| `make O=<output_dir>` | Specify the output directory for the build. |
| `make BR2_TARGET_GENERIC_X86_64=y` | Set the target architecture and options. |

### Packages and Dependencies

| Command | Description |
|---------|-------------|
| `make package/<pkg>/download` | Download a specific package. |
| `make package/<pkg>/extract` | Extract a package's source code. |
| `make package/<pkg>/build` | Build a specific package. |
| `make package/<pkg>/install` | Install a package into the target directory. |
| `make package/<pkg>/clean` | Clean a specific package. |
| `make package/<pkg>/rebuild` | Rebuild a specific package. |

### Cross-Compilation

| Command | Description |
|---------|-------------|
| `make toolchain` | Build the cross-compilation toolchain. |
| `make toolchain_only` | Build only the toolchain. |
| `make target` | Build the target (root filesystem, kernel, etc.). |
| `make <package_name>` | Cross-compile a specific package. |

### Filesystem and Output

| Command | Description |
|---------|-------------|
| `make fs` | Build the root filesystem for the target. |
| `make iso` | Create an ISO image for the target. |
| `make uimage` | Build a U-Boot image. |
| `make rootfs` | Build the root filesystem. |
| `make <image_type>` | Build a specified image type (e.g., `ext4`, `sqfs`). |

### Package Management

| Command | Description |
|---------|-------------|
| `make menuconfig` | Open Buildroot configuration menu to select packages. |
| `make <package_name>_list` | List selected packages. |
| `make package/install` | Install selected packages into the target filesystem. |
| `make package/extract` | Extract source code of selected packages. |

### Kernel Configuration

| Command | Description |
|---------|-------------|
| `make linux-menuconfig` | Configure the Linux kernel using menuconfig. |
| `make linux-<target>` | Build the Linux kernel for the target architecture. |
| `make linux-headers` | Install kernel headers to the output directory. |

### Miscellaneous

| Command | Description |
|---------|-------------|
| `make help` | Show help for Buildroot commands and targets. |
| `make VERSION` | Display the current Buildroot version. |
| `make show-config` | Show the current configuration options. |

## **Example Workflow**

1. **Start a build with the default configuration**:
    ```bash
    make
    ```

2. **Configure Buildroot**:
    ```bash
    make menuconfig
    ```

3. **Build a specific package**:
    ```bash
    make package/example-package
    ```

4. **Build a specific architecture**:
    ```bash
    make ARCH=arm
    ```

5. **Create a custom image**:
    ```bash
    make <image_type>
    ```

## **Useful Tips**

- **Defconfig**: Use `make <arch>_defconfig` to quickly configure for a specific architecture.
- **Custom Configuration**: Store custom configurations in a `BR2_DEFCONFIG` file.
- **External Packages**: Use the `BR2_EXTERNAL` option to add external package trees.

