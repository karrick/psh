# psh

parallel shell

## Description

Parallel shell launches remote ssh shells to multiple hosts. It is
compatible with tmux, screen, Apple Terminal, and iTerm.

## Usage

### Use -m to specify hosts

Connect to a single host `foo.example.com`.

```Bash
psh -m foo.example.com
```

Connect to a several hosts: `foo.example.com` and `bar.example.com`.

```Bash
psh -m foo.example.com,bar.example.com
```

Also connect to a several hosts: `foo.example.com` and `bar.example.com`.

```Bash
psh -m foo.example.com -m bar.example.com
```

### Optionally add command and arguments to end to execute command on hosts

```Bash
psh -m foo.example.com -m bar.example.com uptime
```

Notice the terminal closes after the command completes. To keep the
terminal open after completion of the command, use the -o option.

### Use -o to keep terminal open after command completion

```Bash
psh -m foo.example.com -m bar.example.com -o uptime
```

### Use -p option to specify pane name (tmux only)

```Bash
psh -p messages -m foo.example.com -m bar.example.com tail -F /var/log/messages
```
