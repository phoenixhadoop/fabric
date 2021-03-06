# peer logging
## Description

The `peer logging` subcommand allows administrators to dynamically view and
configure the log levels of a peer.

## Syntax

The `peer logging` subcommand has the following syntax:

```
peer logging getlevel
peer logging setlevel
peer logging revertlevels
```

The different subcommand options (getlevel, setlevel, and revertlevels) relate
to the different logging operations that are relevant to a peer.

Each peer logging subcommand is described together with its options in its own
section in this topic.

## peer logging getlevel

### Get Level Description

The `peer logging getlevel` command allows administrators to get the current
level for a logging module.

### Get Level Syntax

The `peer logging getlevel` command has the following syntax:

```
peer logging getlevel <module-name>
```

### Get Level Flags

The `peer logging getlevel` command does not have any command-specific flags.

### Get Level Usage

Here is an example of the `peer logging getlevel` command:

  * To get the log level for module `peer`:

    ```
    peer logging getlevel peer

    2018-02-22 19:10:08.633 UTC [cli/logging] getLevel -> INFO 001 Current log level for peer module 'peer': DEBUG
    2018-02-22 19:10:08.633 UTC [main] main -> INFO 002 Exiting.....

    ```

## peer logging setlevel

### Set Level Description

The `peer logging setlevel` command allows administrators to set the current
level for all logging modules that match the module name regular expression
provided.

### Set Level Syntax

The `peer logging setlevel` command has the following syntax:

```
peer logging setlevel <module-name-regular-expression> <log-level>
```

### Set Level Flags

The `peer logging setlevel` command does not have any command-specific flags.

### Set Level Usage

Here are some examples of the `peer logging setlevel` command:

  * To set the log level for modules matching the regular expression `peer` to
    log level `WARNING`:

    ```
    peer logging setlevel peer warning
    2018-02-22 19:14:51.217 UTC [cli/logging] setLevel -> INFO 001 Log level set for peer modules matching regular expression 'peer': WARNING
    2018-02-22 19:14:51.217 UTC [main] main -> INFO 002 Exiting.....

    ```

  * To set the log level for modules that match the regular expression `^gossip`
    (i.e. all of the `gossip` logging submodules of the form
    `gossip/<submodule>`) to log level `ERROR`:

    ```
    peer logging setlevel ^gossip error

    2018-02-22 19:16:46.272 UTC [cli/logging] setLevel -> INFO 001 Log level set for peer modules matching regular expression '^gossip': ERROR
    2018-02-22 19:16:46.272 UTC [main] main -> INFO 002 Exiting.....
    ```

## peer logging revertlevels

### Revert Levels Description

The `peer logging revertlevels` command allows administrators to revert the
log levels of all modules to their level at the time the peer completed its
startup process.

### Revert Levels Syntax

The `peer logging revertlevels` command has the following syntax:

```
peer logging revertlevels
```

### Revert Levels Flags

The `peer logging revertlevels` command does not have any command-specific
flags.

### Revert Levels Usage

Here is an example of the `peer logging revertlevels` command:

  * ```
    peer logging revertlevels

    2018-02-22 19:18:38.428 UTC [cli/logging] revertLevels -> INFO 001 Log levels reverted to the levels at the end of peer startup.
    2018-02-22 19:18:38.428 UTC [main] main -> INFO 002 Exiting.....

    ```
