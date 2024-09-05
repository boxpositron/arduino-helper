# Arduino CLI Helper Script

This script is a simple command-line tool for managing Arduino projects with the [arduino-cli](https://github.com/arduino/arduino-cli). It allows you to compile, upload, and manage your Arduino boards using interactive commands with the help of `fzf` for board and file selection and `jq` for JSON parsing.

## Features

- **Device Listing**: Lists all connected Arduino boards.
- **Build**: Compiles Arduino sketches for a selected board.
- **Upload**: Uploads a compiled sketch to the selected Arduino board.
- **Launch**: Combines the `build` and `upload` steps into a single command.
- **Interactive File Selection**: Automatically lists `.ino` files for easy selection if not provided as an argument.

## Requirements

- [arduino-cli](https://github.com/arduino/arduino-cli) installed and available in your `PATH`.
- [fzf](https://github.com/junegunn/fzf) installed for interactive selection.
- [jq](https://stedolan.github.io/jq/) installed for parsing JSON output.

## Installation

1. Ensure that `arduino-cli`, `fzf`, and `jq` are installed on your system.
   
   For Debian-based Linux systems:
   ```bash
   sudo apt install arduino-cli fzf jq
   ```

   For macOS using Homebrew:
   ```bash
   brew install arduino-cli fzf jq
   ```

2. Clone or download this repository and place the script in a directory accessible via your `PATH` (e.g., `/usr/local/bin`).

3. Make the script executable:
   ```bash
   chmod +x arduino
   ```

## Usage

### Commands

```bash
./arduino <command> [file.ino]
```

Where `<command>` can be one of the following:

- **help**: Displays help information.
- **list**: Lists the connected Arduino boards.
- **build [file.ino]**: Compiles the specified `.ino` file.
- **upload [file.ino]**: Uploads the compiled file to the connected board.
- **launch [file.ino]**: Compiles and uploads the file to the connected board.

If `file.ino` is not provided, the script will prompt you to select one interactively using `fzf`.

### Examples

1. **Listing connected boards:**
   ```bash
   ./arduino list
   ```

2. **Compiling a sketch:**
   ```bash
   ./arduino build Blink.ino
   ```

   If no file is specified, you will be prompted to select a `.ino` file interactively.

3. **Uploading a sketch to the board:**
   ```bash
   ./arduino upload Blink.ino
   ```

   Again, if no file is specified, the script will prompt you for a selection.

4. **Compiling and uploading:**
   ```bash
   ./arduino launch Blink.ino
   ```

### Example Workflow

1. **Connect your Arduino board to your computer.**
2. **List available devices:**
   ```bash
   ./arduino list
   ```
3. **Compile a sketch:**
   ```bash
   ./arduino build Blink.ino
   ```
4. **Upload the sketch to your Arduino board:**
   ```bash
   ./arduino upload Blink.ino
   ```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributions

Feel free to submit issues or pull requests if you have any improvements or bug fixes.
