# Server Monitor

A lightweight Bash script that monitors CPU, memory, and disk usage in real time and alerts when any resource exceeds a configurable threshold.

## Features

- Real-time monitoring of CPU, memory, and disk usage
- Configurable alert thresholds (default: 80% for all resources)
- Colour-coded alerts printed to the terminal
- Continuous logging of resource usage to `resource_usage.log`

## Usage

```bash
chmod +x system.sh
./system.sh
```

The script runs in a continuous loop, refreshing every 2 seconds.

## Configuration

Edit the threshold variables at the top of `system.sh`:

| Variable           | Default | Description                        |
|--------------------|---------|------------------------------------|
| `CPU_THRESHOLD`    | `80`    | CPU usage alert threshold (%)      |
| `MEMORY_THRESHOLD` | `80`    | Memory usage alert threshold (%)   |
| `DISK_THRESHOLD`   | `80`    | Disk usage alert threshold (%)     |

## Output

### Terminal

The current resource usage is displayed and refreshed every 2 seconds:

```
Resource Usage:
CPU: 23%
Memory: 45%
Disk: 60%
```

If a threshold is exceeded, an alert is printed in red:

```
ALERT: CPU usage exceeded threshold! Current value: 85%
```

### Log file

Usage data is appended to `resource_usage.log` in the working directory with a timestamp:

```
2026-05-22 14:30:01 CPU: 23% Memory: 45% Disk: 60%
```

## Requirements

- Bash
- Standard Unix utilities: `top`, `free`, `df`, `awk`, `tput`
