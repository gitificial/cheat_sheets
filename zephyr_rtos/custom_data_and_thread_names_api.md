## Zephyr RTOS Custom Data and Thread Names API Cheat Sheet

### Thread Custom Data

| Function | Description |
|----------|-------------|
| `k_thread_custom_data_set(value)` | Set the current thread's custom data (any `void*` value). |
| `k_thread_custom_data_get()` | Get the current thread's custom data. |

### Thread Naming

| Function | Description |
|----------|-------------|
| `k_thread_name_set(thread, str)` | Set the name of a thread. |
| `k_thread_name_get(thread)` | Get the name of a thread. |
| `k_thread_name_copy(thread, buf, size)` | Copy the thread's name into a supplied buffer of given size. |
