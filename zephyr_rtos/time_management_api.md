## Zephyr RTOS Time Management API Cheat Sheet

### Delays and Sleep

| Function | Description |
|----------|-------------|
| `k_sleep(timeout)` | Put the current thread to sleep. |
| `k_msleep(ms)` | Sleep for a specified number of milliseconds. |
| `k_usleep(us)` | Sleep for a specified number of microseconds. |
| `k_busy_wait(usec_to_wait)` | Busy wait for a specified time in microseconds. |

### Ticks and Time Conversion

| Function | Description |
|----------|-------------|
| `k_uptime_get()` | Get system uptime in milliseconds. |
| `k_uptime_get_32()` | Get system uptime as 32-bit milliseconds (wraps around). |
| `k_uptime_delta(&start)` | Get delta time since a previous timestamp in milliseconds. |
| `k_cycle_get_32()` | Get system cycle counter (32-bit). |
| `k_ticks_to_ms(ticks)` | Convert ticks to milliseconds. |
| `k_ms_to_ticks(ms)` | Convert milliseconds to system ticks. |
| `k_ticks_to_us(ticks)` | Convert ticks to microseconds. |
| `k_us_to_ticks(us)` | Convert microseconds to system ticks. |

### Timeouts

| Function | Description |
|----------|-------------|
| `K_NO_WAIT` | Constant: Do not wait, return immediately. |
| `K_FOREVER` | Constant: Wait indefinitely. |
| `k_timeout_t` | Data type used to specify timeouts in functions. |
| `k_thread_timeout_expires_ticks(thread)` | Get wake-up time of a thread in system ticks. |
| `k_thread_timeout_remaining_ticks(thread)` | Get remaining time before a thread wakes up in system ticks. |

### Timers

| Function | Description |
|----------|-------------|
| `k_timer_init(timer, expiry_fn, stop_fn)` | Initialize a kernel timer with expiry and stop callbacks. |
| `k_timer_start(timer, duration, period)` | Start a timer with duration and optional periodic interval. |
| `k_timer_stop(timer)` | Stop a running timer. |
| `k_timer_status_get(timer)` | Get the number of times the timer has expired since last read. |
| `k_timer_status_sync(timer)` | Synchronize the timer status. |
