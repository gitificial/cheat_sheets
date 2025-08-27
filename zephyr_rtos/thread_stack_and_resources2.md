## Zephyr RTOS Thread Stack and Resources API cheat sheet

### Thread Stack Management

| Function | Description |
|----------|-------------|
| `k_thread_stack_alloc(size, flags)` | Dynamically allocate a thread stack. |
| `k_thread_stack_free(stack)` | Free a dynamically allocated thread stack. |
| `k_thread_stack_init(stack, stack_size)` | Initialize a thread stack (for static stacks). |
| `K_THREAD_STACK_DEFINE(name, size)` | Define a static thread stack. |

### Thread Heap Assignment

| Function | Description |
|----------|-------------|
| `k_thread_heap_assign(thread, heap)` | Assign a resource memory pool (heap) to a thread. |

### Thread Custom Data

| Function | Description |
|----------|-------------|
| `k_thread_custom_data_set(value)` | Set current thread's custom data. |
| `k_thread_custom_data_get()` | Get current thread's custom data. |

### Thread Naming

| Function | Description |
|----------|-------------|
| `k_thread_name_set(thread, str)` | Set a thread's name. |
| `k_thread_name_get(thread)` | Get a thread's name. |
| `k_thread_name_copy(thread, buf, size)` | Copy the thread's name into a supplied buffer. |

### Thread State Queries

| Function | Description |
|----------|-------------|
| `k_thread_state_str(thread_id, buf, buf_size)` | Get thread state as a string. |
