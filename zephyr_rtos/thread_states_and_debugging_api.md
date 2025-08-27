## Zephyr RTOS Thread States and Debugging API cheat sheet

### Thread State Queries

| Function | Description |
|----------|-------------|
| `k_thread_state_str(thread_id, buf, buf_size)` | Get the current state of a thread as a human-readable string. |
| `k_thread_is_ready(thread)` | Check if a thread is in the ready state. |
| `k_thread_is_suspended(thread)` | Check if a thread is suspended. |
| `k_thread_is_dead(thread)` | Check if a thread has terminated. |
| `k_thread_is_pending(thread)` | Check if a thread is waiting for a resource (blocked). |

### Thread Debugging Utilities

| Function | Description |
|----------|-------------|
| `k_thread_foreach(user_cb, user_data)` | Iterate over all threads in the system and execute a user callback. |
| `k_thread_foreach_filter_by_cpu(cpu, user_cb, user_data)` | Iterate over threads running on a specified CPU. |
| `k_thread_foreach_unlocked(user_cb, user_data)` | Iterate over all threads without locking the scheduler. |
| `k_thread_foreach_unlocked_filter_by_cpu(cpu, user_cb, user_data)` | Iterate over threads on a specific CPU without locking. |
| `k_thread_stack_alloc(size, flags)` | Allocate a thread stack (useful for inspecting stack usage). |
| `k_thread_stack_free(stack)` | Free a dynamically allocated thread stack. |
