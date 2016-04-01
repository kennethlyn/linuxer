
# Direct Memory Access and Scatter Gather

scatter/gather方式是与block dma方式相对应的一种dma方式。

在dma传输数据的过程中，要求源物理地址和目标物理地址必须是连续的。但在有的计算机
体系中，如IA，连续的存储器地址在物理上不一定是连续的，则dma传输要分成多次完成。
如果传输完一块物理连续的数据后发起一次中断，同时主机进行下一块物理连续的传输，则
这种方式即为block dma方式。

scatter/gather方式则不同，它是用一个链表描述物理不连续的存储器，然后把链表首地址
告诉dma master。dma master传输完一块物理连续的数据后，就不用再发中断了，而是根据
链表传输下一块物理连续的数据,最后发起一次中断。

很显然scatter/gather方式比block dma方式效率高。

