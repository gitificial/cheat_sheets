## Zephyr RTOS Semaphore API cheat sheet

### Semaphore Initialization

| Function | Description |
|----------|-------------|
| `k_sem_init(sem, initial_count, max_count)` | Initialize a semaphore with an initial and maximum count. |
| `K_SEM_DEFINE(name, initial_count, max_count)` | Define and initialize a semaphore statically. |

### Semaphore Take (Acquire)

| Function | Description |
|----------|-------------|
| `k_sem_take(sem, timeout)` | Take (acquire) a semaphore, with a timeout. |
| `k_sem_take(&sem, K_NO_WAIT)` | Try to take the semaphore without waiting. |
| `k_sem_take(&sem, K_FOREVER)` | Wait indefinitely until the semaphore is available. |

### Semaphore Give (Release)

| Function | Description |
|----------|-------------|
| `k_sem_give(sem)` | Release (give) a semaphore, increasing its count. |
| `k_sem_reset(sem)` | Reset the semaphore count to its initial value. |

### Semaphore Inspection

| Function | Description |
|----------|-------------|
| `k_sem_count_get(sem)` | Get the current count of a semaphore. |
| `k_sem_owner_get(sem)` | Get the current thread owning the semaphore (if used for mutex). |

### Mutex (Binary Semaphore) Functions

| Function | Description |
|----------|-------------|
| `k_mutex_init(mutex)` | Initialize a mutex (binary semaphore). |
| `k_mutex_lock(mutex, timeout)` | Lock a mutex with optional timeout. |
| `k_mutex_unlock(mutex)` | Unlock a mutex. |

### Semaphore Utilities

| Function | Description |
|----------|-------------|
| `k_sem_take(&sem, K_MSEC(ms))` | Take a semaphore with millisecond timeout. |
| `k_sem_take(&sem, K_USEC(us))` | Take a semaphore with microsecond timeout. |
| `k_sem_give(&sem)` | Release a semaphore and wake up waiting threads. |
| `k_sem_reset(&sem)` | Reset semaphore count to initial count. |
