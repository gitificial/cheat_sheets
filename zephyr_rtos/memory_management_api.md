## Zephyr RTOS Memory Management API cheat sheet

### Memory Pools

| Function | Description |
|----------|-------------|
| `K_MEM_POOL_DEFINE(name, block_size, max_blocks, max_alloc, align)` | Define and initialize a memory pool. |
| `k_mem_pool_alloc(pool, block, timeout)` | Allocate a memory block from a memory pool with timeout. |
| `k_mem_pool_free(block)` | Free a memory block back to the memory pool. |
| `k_mem_pool_init(pool, blocks, block_size, num_blocks, align)` | Initialize a memory pool dynamically. |

### Heap Memory

| Function | Description |
|----------|-------------|
| `k_heap_init(heap, base, size)` | Initialize a heap memory region. |
| `k_heap_alloc(heap, size, timeout)` | Allocate memory from a heap with timeout. |
| `k_heap_free(heap, ptr)` | Free memory back to the heap. |

### Slab Memory Allocator

| Function | Description |
|----------|-------------|
| `K_MEM_SLAB_DEFINE(name, num_blocks, block_size, align)` | Define a memory slab (fixed-size blocks). |
| `k_mem_slab_alloc(slab, ptr, timeout)` | Allocate a block from a memory slab with timeout. |
| `k_mem_slab_free(slab, ptr)` | Free a block back to the memory slab. |

### Dynamic Memory Allocation

| Function | Description |
|----------|-------------|
| `k_malloc(size)` | Allocate memory dynamically (from the heap). |
| `k_free(ptr)` | Free dynamically allocated memory. |
| `k_calloc(n, size)` | Allocate and zero-initialize memory for an array of `n` elements. |
| `k_realloc(ptr, size)` | Resize a previously allocated memory block. |

### Memory Inspection

| Function | Description |
|----------|-------------|
| `k_heap_aligned_alloc(heap, size, align, timeout)` | Allocate aligned memory from a heap. |
| `k_mem_pool_max_block_size(pool)` | Get maximum block size for a memory pool. |
| `k_mem_slab_num_free_get(slab)` | Get the number of free blocks in a memory slab. |
| `k_mem_slab_num_used_get(slab)` | Get the number of used blocks in a memory slab. |
