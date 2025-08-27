## Yocto Project cheat sheet

### **Basic Commands**

| **Command**                                          | **Description**                                              |
|------------------------------------------------------|--------------------------------------------------------------|
| `source oe-init-build-env`                            | Set up the build environment for Yocto (Run from the Yocto directory). |
| `bitbake <target>`                                    | Build a specific target (e.g., `bitbake core-image-minimal`). |
| `bitbake <image>`                                     | Build a specified image (e.g., `bitbake core-image-sato`).   |
| `bitbake -c clean <recipe>`                           | Clean the recipe build, removing all build artifacts.        |
| `bitbake -c fetch <recipe>`                           | Download the source files for a specific recipe.             |
| `bitbake -c compile <recipe>`                         | Compile a specific recipe.                                   |
| `bitbake -c install <recipe>`                         | Install the compiled recipe to the target directory.         |
| `bitbake -c do_image_complete`                        | Complete image creation (bundles up the final image).        |
| `bitbake -b <recipe>`                                 | Build a specific recipe from source.                         |
| `bitbake -B <recipe>`                                 | Build all recipes that are dependencies of the given recipe. |
| `bitbake -p`                                          | Parse all recipes in the configuration.                      |
| `bitbake -s`                                          | Show a list of all available recipes and their status.       |

### **Yocto Build Directory**

| **Directory**                                        | **Description**                                              |
|------------------------------------------------------|--------------------------------------------------------------|
| `build/`                                             | Main build directory (created by `oe-init-build-env`).       |
| `build/conf/`                                        | Configuration files for Yocto build (e.g., `local.conf`).    |
| `build/tmp/`                                         | Temporary working directory for all build files (intermediate files). |
| `build/tmp/deploy/`                                  | Deploy directory, contains built images, artifacts, and packages. |
| `build/tmp/work/`                                    | Working directory for all recipes being built.              |
| `build/meta/`                                         | Contains the layers for the Yocto build.                     |

### **Configuration Files**

| **File**                                             | **Description**                                              |
|------------------------------------------------------|--------------------------------------------------------------|
| `conf/local.conf`                                    | Main configuration file for the build system (set machine, image, and other build parameters). |
| `conf/bblayers.conf`                                 | Specifies the layers included in the build.                  |
| `meta-<layer>/conf/layer.conf`                       | Configuration for a specific Yocto layer.                    |
| `meta-<layer>/recipes-*/<recipe>/<recipe-name>.bb`     | A specific recipe file for building software packages.      |
| `meta-<layer>/recipes-*/<recipe>/<recipe-name>.bbappend` | A file to append additional build steps or modifications to a recipe. |
| `meta-<layer>/conf/distro/<distro>.conf`              | Configuration for the distribution to be built.              |

### **Common Configuration Variables**

| **Variable**                                          | **Description**                                              |
|------------------------------------------------------|--------------------------------------------------------------|
| `MACHINE`                                            | Defines the target machine (e.g., `qemuarm`, `raspberrypi3`). |
| `DISTRO`                                             | Defines the target distribution (e.g., `poky`, `yocto`).     |
| `DL_DIR`                                             | Directory where downloaded source code and patches are stored. |
| `SSTATE_DIR`                                         | Directory for shared state cache (used for incremental builds). |
| `BB_NUMBER_THREADS`                                  | Number of parallel threads for building.                    |
| `PARALLEL_MAKE`                                      | Number of parallel make jobs for compilation.                |
| `BB_ENV_EXTRAWHITE`                                  | List of environment variables to pass through during build.  |

### **Common Yocto Tasks**

| **Command**                                          | **Description**                                              |
|------------------------------------------------------|--------------------------------------------------------------|
| `bitbake-layers show-layers`                         | Display the layers included in your build configuration.     |
| `bitbake-layers add-layer <path_to_layer>`           | Add a new layer to your Yocto build configuration.           |
| `bitbake-layers remove-layer <layer>`                | Remove a layer from the build configuration.                 |
| `bitbake-layers show-recipes`                        | List available recipes in the current configuration.        |
| `bitbake-layers show-appends`                        | Show which recipes have `.bbappend` files.                   |
| `bitbake -c menuconfig <recipe>`                     | Open kernel configuration menu for a specific recipe.       |
| `bitbake -c cleansstate <recipe>`                    | Clean all build artifacts for a specific recipe.            |
| `bitbake -c fetchall <recipe>`                       | Fetch all sources (e.g., download files, git repositories). |
| `bitbake <image> -D`                                 | Build an image in debug mode (verbose logging).              |
| `bitbake <image> -v`                                 | Build in verbose mode (more detailed output).               |

### **Working with Recipes**

| **Command**                                          | **Description**                                              |
|------------------------------------------------------|--------------------------------------------------------------|
| `bitbake <recipe> -c compile`                        | Compile the recipe source code.                              |
| `bitbake <recipe> -c do_package`                     | Build the package (e.g., create a `.ipk` or `.rpm` package). |
| `bitbake <recipe> -c fetch`                          | Fetch source code for the recipe.                            |
| `bitbake <recipe> -c clean`                          | Clean the recipe build (remove all output).                 |
| `bitbake <recipe> -c do_configure`                   | Run the configure step for the recipe.                       |
| `bitbake <recipe> -c install`                        | Install the recipe to the target filesystem.                 |
| `bitbake <recipe> -c rootfs`                         | Build the root filesystem from the recipe.                   |
| `bitbake <recipe> -c patch`                          | Apply patches to the recipe.                                 |

### **Building Images**

| **Command**                                          | **Description**                                              |
|------------------------------------------------------|--------------------------------------------------------------|
| `bitbake core-image-minimal`                         | Build a minimal Linux image (with basic utilities).          |
| `bitbake core-image-sato`                            | Build a Sato-based graphical image.                          |
| `bitbake core-image-full-cmdline`                    | Build a full command line image.                             |
| `bitbake <image> -c populate_sdk`                    | Create the SDK (Software Development Kit) for the image.     |
| `bitbake <image> -c deploy`                          | Deploy the image to the target directory.                    |

### **Yocto Tools**

| **Command**                                          | **Description**                                              |
|------------------------------------------------------|--------------------------------------------------------------|
| `bitbake -c devshell <recipe>`                       | Open a shell with the environment set for a specific recipe. |
| `bitbake -c menuconfig <recipe>`                     | Open the kernel configuration menu.                          |
| `runqemu <machine>`                                  | Launch a QEMU virtual machine with the specified machine type.|
| `oe-pkgdata-util`                                    | Utility to manipulate package metadata.                      |
| `pylint`                                             | Run Python linting on Yocto recipes.                         |
| `bitbake -s`                                         | Show the status of recipes in the configuration.             |

### **Creating Custom Layers**

| **Command**                                          | **Description**                                              |
|------------------------------------------------------|--------------------------------------------------------------|
| `yocto-layer create <layer_name>`                     | Create a new layer for Yocto development.                    |
| `bitbake-layers show-layers`                         | Show all available layers in your current Yocto configuration.|
| `bitbake-layers add-layer <path_to_layer>`           | Add a new layer to your Yocto build configuration.           |
| `bitbake-layers remove-layer <layer_name>`           | Remove a layer from the Yocto build configuration.           |

### **Debugging Yocto Builds**

| **Command**                                          | **Description**                                              |
|------------------------------------------------------|--------------------------------------------------------------|
| `bitbake -v <recipe>`                                | Show verbose output for a specific recipe build.             |
| `bitbake -D <recipe>`                                | Show debug output for the build process.                     |
| `bitbake -e <recipe>`                                | Display environment variables for a specific recipe.         |
| `bitbake -p`                                         | Parse the recipes without building.                          |
| `bitbake -b`                                         | Show bitbake flags and variable information.                 |

### **Useful Tips**

- **Out-of-source builds**: Always use a separate directory for building (`build/`), rather than building inside the Yocto directory.
- **Use `bitbake -s`** to check recipe status and identify missing dependencies.
- **Layer management**: Use `bitbake-layers` to manage and inspect layers in your build.
- **Layer debugging**: If you encounter build issues, review layer configurations and check for any missing or incorrect `bbappend` files.
