## The Basics

Paging allows for the division of a **program's** **address space** into fixed size *pages*, dividing the **physical memory of the computer** into *page frames* of the same size.

Your **hardware** will then contain *page tables* with an entry for each page in the address space.

A page table entry contains the real memory page frame for the page, or some bits to mark the page not present. If a not present page gets an access attempt by a program the OS generates a *page fault*.

[[Operating Systems]] can load a copy of the contents page from disk into a free page frame then let the application continue. By moving these pages around between main mem. and disk the OS can provide *virtual memory* which appears to the application far larger than the real memory in use.

## The Sticky Bits

There is a cost, solo instructions execute fast but a page fault and consequent page-in/page-out (transfer from disk to main mem. or vice versa) will take far longer.

Therefore, the more page faults, the slower a program runs. Worst case scenario, *thrashing*, where the program is doing no work and page faulting constantly.

***Theeeeerefore***, the less pages a program needs, the fewer page faults it will generate. If a [[Linkers]] can pack related routines into a single page or small group of pages, the performance will naturally improve.

Further, pages marked read-only don't need to be paged out since they can be reloaded from wherever they originally came from, improving performance. So if identical pages appear in multiple address spaces, i.e. when multiple copies of a program are running, a single physical page will suffice for all address spaces.

A good example is shared [[Object Code Libraries]], which use [[Position-Independent Code (PIC)]] so can be mapped read-only.

See also:
- [[Computer Science Fundamentals]]