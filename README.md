# **Crab CLI**

**`crab`** is the official command-line interface for Blue CrabDB, a lightweight, portable key-value database designed for embedded systems, scripting environments, and efficient local storage. With a single executable and a suite of powerful subcommands, `crab` lets you insert, query, export, import, and manage `.crabdb` files directly from the terminal. Whether you're building automation scripts, logging sensor data, or managing configurations, `crab` offers a streamlined, shell-friendly experience with both structured and raw access modes via MyShell and NoShell. It’s small, fast, and designed to fit into your workflow like a natural extension of the UNIX philosophy.

### 🧰 `crab` CLI Command Reference

| Command                         | Description                                               |
|---------------------------------|-----------------------------------------------------------|
| `crab --version`                | Show the current version of the CLI                       |
| `crab --help`                   | Show help information and command usage                   |
| `crab get <db> <key>`           | Fetch the value for a given key                           |
| `crab put <db> <key> <val>`     | Insert or update a key-value pair                         |
| `crab del <db> <key>`           | Delete a key from the database                            |
| `crab ls <db> [prefix]`         | List all keys, optionally filtered by prefix              |
| `crab keys <db> <pattern>`      | Find keys by pattern (wildcard or regex)                  |
| `crab grep <db> <query>`        | Search values for matching text                           |
| `crab watch <db> <pattern>`     | Watch key changes in real-time like `tail -f`             |
| `crab export <db>`              | Export database contents (e.g., to JSON/CSV)              |
| `crab import <db>`              | Import entries from a file (JSON/CSV)                     |
| `crab diff <a.crab> <b.crab>`   | Show differences between two `.crabdb` files              |
| `crab backup <db>`              | Backup the database with a timestamped file               |
| `crab compact <db>`             | Optimize the database file by removing obsolete data      |
| `crab pipe <db> <mode>`         | Read/write via stdin/stdout for shell scripting           |
| `crab sh <db> [--as <mode>]`    | Launch MyShell by default, or NoShell with `--as noshell` |

---

### 🧪 Examples:

```sh
# Get a value
crab get my.crabdb user:001:name

# Add or update a value
crab put my.crabdb user:001:name "Jellyfish"

# Delete a key
crab del my.crabdb user:001:name

# Interactive shell (default to MyShell)
crab sh my.crabdb

# Interactive shell with NoShell mode
crab sh my.crabdb --as noshell

# Export to JSON
crab export my.crabdb --format json > mydata.json

# Import from CSV
crab import my.crabdb --format csv < newdata.csv

# Watch keys for changes
crab watch my.crabdb "logs:*"
```

---

## **Prerequisites**

Ensure you have the following installed before starting:

- **Meson Build System**: This project relies on Meson. For installation instructions, visit the official [Meson website](https://mesonbuild.com/Getting-meson.html).

## **Setting Up Meson Build**

1. **Install Meson**:
    - Follow the installation guide on the [Meson website](https://mesonbuild.com/Getting-meson.html) for your operating system.

## **Setting Up, Compiling, Installing, and Running the Project**

1. **Clone the Repository**:

    ```sh
    git clone https://github.com/fossillogic/crab.git
    cd crab
    ```

2. **Configure the Build**:

    ```sh
    meson setup builddir
    ```

3. **Compile the Project**:

    ```sh
    meson compile -C builddir
    ```

4. **Install the Project**:

    ```sh
    meson install -C builddir
    ```

5. **Run the Project**:

    ```sh
    crab
    ```

## **Contributing**

Interested in contributing? Please open pull requests or create issues on the [GitHub repository](https://github.com/fossillogic/crab).

## **Feedback and Support**

For issues, questions, or feedback, open an issue on the [GitHub repository](https://github.com/fossillogic/crab/issues).

## **License**

This project is licensed under the [Mozilla Public License](LICENSE).
