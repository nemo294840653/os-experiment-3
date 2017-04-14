# os-experiment-3
                本实验实现了三种进程间通讯的方式，分别为fifo，pipe，shared_memory，以下是每种方式的功能和使用方法

                1. fifo
                源代码： fifoclient.c fifoserver.c
                编译后，首先将fifoserver.out在后台运行: $ ./fifoserver.out &
                fifoserver.out用于接受fifoclient.out程序所传的字符串
                fifoclient.out程序使用方式：$ ./fifoclient.out +字符串
                例如输入 $ ./fifoclient.out "Hello world!"
                fifoserver.out程序将打印出: Received string: Hello world!

                2. pipe
                源代码：pipe.c
                使用方法：$ ./pipe.out +字符串
                例如输入 $./pipe.out "hello world"
                程序将打印出：
                Received string: hello world
                size = 12 bytes

                3. shared_memory
                源代码：shm.c
                使用说明：该程序在一个程序内从内存的不同位置访问shared memory，打印出两次的地址、共享内存块大小和第一次访问共享内存时所存入的字符串
                使用方法：$./shm.out
                输出为：
                shared memory attached at address 0x7fc60398c000
                segment size: 25600
                shared memory reattached at address 0x5000000
                Hello, world.
