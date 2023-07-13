# internsctl - Custom Linux command

The `internsctl` command is a custom Linux command that provides various functionalities related to system administration tasks. It allows you to perform the following operations:

## Usage

```shell
internsctl [OPTIONS] COMMAND [ARGS]
```

## Options

- `--version`: Display the version of internsctl.
- `--help`: Display the help message.

## Commands

- `cpu getinfo`: Get CPU information of the server.
- `memory getinfo`: Get memory information of the server.
- `user create <username>`: Create a new user on the server.
- `user list`: List all regular users on the server.
- `user list --sudo-only`: List users with sudo permissions on the server.
- `file getinfo [OPTIONS] <file-name>`: Get information about a file.

## Command Details

### cpu getinfo

This command retrieves CPU information of the server using the `lscpu` command.

Example:
```shell
internsctl cpu getinfo
```

### memory getinfo

This command retrieves memory information of the server using the `free` command.

Example:
```shell
internsctl memory getinfo
```

### user create <username>

This command creates a new user on the server with the provided `<username>`. It uses the `useradd` command to add the user.

Example:
```shell
internsctl user create john
```

### user list

This command lists all regular users on the server using the `getent passwd` command.

Example:
```shell
internsctl user list
```

### user list --sudo-only

This command lists users with sudo permissions on the server. It retrieves the sudo users by querying the `sudo` group using the `getent group sudo` command.

Example:
```shell
internsctl user list --sudo-only
```

### file getinfo [OPTIONS] <file-name>

This command retrieves information about a file specified by `<file-name>`. You can provide additional options to get specific information about the file.

Options:
- `--size` or `-s`: Get the file size in bytes.
- `--permissions` or `-p`: Get the file permissions.
- `--owner` or `-o`: Get the file owner.
- `--last-modified` or `-m`: Get the last modification timestamp of the file.

Example:
```shell
internsctl file getinfo --size myfile.txt
internsctl file getinfo --permissions myfile.txt
internsctl file getinfo --owner myfile.txt
internsctl file getinfo --last-modified myfile.txt
```

## Version

The current version of internsctl is v0.1.0.

To display the version, use the `--version` option.

Example:
```shell
internsctl --version
```

## Help

To display this help message, use the `--help` option.

Example:
```shell
internsctl --help
```

## Manual Page

For detailed information about the `internsctl` command and its usage, please refer to the manual page. To view the manual page, run the following command:

```shell
man internsctl
```

Note: Make sure to save the script as a shell file (e.g., `internsctl.sh`) and make it executable using the `chmod +x internsctl.sh` command before running it.
