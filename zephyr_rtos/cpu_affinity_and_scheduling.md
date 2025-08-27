## Zephyr RTOS CPU Affinity and Scheduling API cheat sheet

### Scheduler Control

| Function | Description |
|----------|-------------|
| `k_sched_lock()` | Lock the scheduler to prevent context switches. |
| `k_sched_unlock()` | Unlock the scheduler to allow context switches. |
| `k_reschedule()` | Invoke the scheduler to run the highest-priority ready thread. |

### Thread Time-Slicing

| Function | Description |
|----------|-------------|
| `k_sched_time_slice_set(slice, prio)` | Set time-slicing period and scope for threads of a given priority. |
| `k_thread_time_slice_set(thread, slice_ticks, expired_fn, data)` | Set thread-specific time slice and callback for expiration. |

### CPU Affinity and Pinning

| Function | Description |
|----------|-------------|
| `k_thread_cpu_mask_clear(thread)` | Clear all CPU enable masks for a thread. |
| `k_thread_cpu_mask_enable_all(thread)` | Enable a thread to run on all CPUs. |
| `k_thread_cpu_mask_enable(thread, cpu)` | Enable a thread to run on a specified CPU. |
| `k_thread_cpu_mask_disable(thread, cpu)` | Prevent a thread from running on a specified CPU. |
| `k_thread_cpu_pin(thread, cpu)` | Pin a thread to a specific CPU. |

### Current Thread Queries

| Function | Description |
|----------|-------------|
| `k_sched_current_thread_query()` | Query thread ID of the current thread. |
| `k_current_get()` | Get thread ID of the current thread. |
