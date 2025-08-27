## Zephyr RTOS Thread API cheat sheet

### Thread Creation and Management

| Function | Description |
|----------|-------------|
| `k_thread_create(new_thread, stack, stack_size, entry, p1, p2, p3, prio, options, delay)` | Create a thread. |
| `k_thread_user_mode_enter(entry, p1, p2, p3)` | Drop a thread's privileges permanently to user mode. |
| `k_thread_start(thread)` | Start an inactive thread. |
| `k_thread_abort(thread)` | Abort a thread. |
| `k_thread_suspend(thread)` | Suspend a thread. |
| `k_thread_resume(thread)` | Resume a suspended thread. |
| `k_thread_join(thread, timeout)` | Sleep until a thread exits. |

### Thread Sleeping and Timing

| Function | Description |
|----------|-------------|
| `k_sleep(timeout)` | Put the current thread to sleep. |
| `k_msleep(ms)` | Sleep for a specified number of milliseconds. |
| `k_usleep(us)` | Sleep for a specified number of microseconds. |
| `k_busy_wait(usec_to_wait)` | Busy wait for a specified time in microseconds. |
| `k_thread_timeout_expires_ticks(thread)` | Get wake-up time of a thread (in system ticks). |
| `k_thread_timeout_remaining_ticks(thread)` | Get remaining time before a thread wakes up (in system ticks). |

### Thread Yielding

| Function | Description |
|----------|-------------|
| `k_yield()` | Yield the current thread. |
| `k_can_yield()` | Check if it is possible to yield in the current context. |
| `k_wakeup(thread)` | Wake up a sleeping thread. |
| `k_reschedule()` | Invoke the scheduler. |

### Thread Priority and Deadline

| Function | Description |
|----------|-------------|
| `k_thread_priority_get(thread)` | Get a thread's priority. |
| `k_thread_priority_set(thread, prio)` | Set a thread's priority. |
| `k_thread_deadline_set(thread, deadline)` | Set deadline expiration time for scheduler. |

### Thread CPU Affinity

| Function | Description |
|----------|-------------|
| `k_thread_cpu_mask_clear(thread)` | Clear all CPU enable masks. |
| `k_thread_cpu_mask_enable_all(thread)` | Enable all CPU masks. |
| `k_thread_cpu_mask_enable(thread, cpu)` | Enable a thread on a specific CPU. |
| `k_thread_cpu_mask_disable(thread, cpu)` | Disable a thread on a specific CPU. |
| `k_thread_cpu_pin(thread, cpu)` | Pin a thread to a specific CPU. |
| `k_thread_foreach(user_cb, user_data)` | Iterate over all threads in the system. |
| `k_thread_foreach_filter_by_cpu(cpu, user_cb, user_data)` | Iterate over threads running on a specific CPU. |
| `k_thread_foreach_unlocked(user_cb, user_data)` | Iterate over all threads without locking. |
| `k_thread_foreach_unlocked_filter_by_cpu(cpu, user_cb, user_data)` | Iterate over threads on a CPU without locking. |

### Thread Stack and Heap

| Function | Description |
|----------|-------------|
| `k_thread_stack_alloc(size, flags)` | Dynamically allocate a thread stack. |
| `k_thread_stack_free(stack)` | Free a dynamically allocated thread stack. |
| `k_thread_heap_assign(thread, heap)` | Assign a resource memory pool to a thread. |

### Thread Custom Data

| Function | Description |
|----------|-------------|
| `k_thread_custom_data_set(value)` | Set current thread's custom data. |
| `k_thread_custom_data_get()` | Get current thread's custom data. |

### Thread Naming

| Function | Description |
|----------|-------------|
| `k_thread_name_set(thread, str)` | Set a thread's name. |
| `k_thread_name_get(thread)` | Get thread's name. |
| `k_thread_name_copy(thread, buf, size)` | Copy thread's name into a buffer. |

### Thread State

| Function | Description |
|----------|-------------|
| `k_thread_state_str(thread_id, buf, buf_size)` | Get thread state as a string. |
| `k_sched_current_thread_query()` | Query thread ID of the current thread. |
| `k_current_get()` | Get thread ID of the current thread. |

### Time-Slicing and Scheduler

| Function | Description |
|----------|-------------|
| `k_sched_time_slice_set(slice, prio)` | Set time-slicing period and scope. |
| `k_thread_time_slice_set(thread, slice_ticks, expired, data)` | Set thread time slice. |
| `k_sched_lock()` | Lock the scheduler. |
| `k_sched_unlock()` | Unlock the scheduler. |
