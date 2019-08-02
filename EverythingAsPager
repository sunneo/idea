Mock Everything As Page Server
1. Page Client (Allocator) 
  * Allocate Movable Memory
  * Registry As Movable
  * A Table which record entries
  * MemoryEntry( dirty, serverid(-1:local), pageindex, pagecount )
2. Movable Object Pool
  * allocate half of memory space for caching.
  * request object before accessing(swap in/cache)
  * move objects to remote site when allocating/request (swap out)
  * api
     * void* objectpool_request(void* objectaddr); 
        * Of course, this function can also be triggered by mprotect with PROT_NONE within page fault handler. 
        * But we can also positively request for it without cache penalty. 
     * void* objectpool_allocate(size_t size);
     * [optional] status objectpool_info(void* objectaddr);
