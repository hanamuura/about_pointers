# about_pointers

## Stack
Memory of computer represented as stack and heap.
![image](https://github.com/user-attachments/assets/b4c9335a-08f2-4ef4-a7b8-5a75d23dd572)
this is a stack in memory which store some value. stack can store defferrent type of values. the main benefits of using stack is that stack is faster than heap.

```c
#include <stdio.h>

void nothing() {
  printf("my call should be store in stack")
}

int main() {
  int var = 5; //this variable should be store in stack 
  nothing() //call this func
  int buff[1024] //this is also store in stack which takes sizeof(int) * 1024 = 4KB
}
```

## Heap
Heap in memory represented as tree structure and also store values. heap slower than stack, but have much more available memory. if we talking about c language we should 
know, that heap also provide to us ability of dynamic change values in heap. this is called mutatuion. all values in stack are immutable. as programmer you can only assign it
but never change.

usage of heap:

```c
#include <stdlib.h>

typedef struct some_struct {
  int val;
  bool is_in_heap;
} t_struct

int main() {
  t_struct struct_instance = (t_struct*)malloc(sizeof(t_struct)) //this instance should be store in heap because malloc func returns pointer to ur instance
  t_struct another_instance; // this should allocate instance in stask
}  
```

another interesting example 

```c
#include <stdlib.h>

void heap_param(*int array, int arr_size) {} // in this example array represented as pointer to some point in memory. this mean that variable takes any size of memory, which we cant predict
void stack_param(int[1024] buffer) {} //in this example buffer takes sizeof(int) * 1024 memory in stack and we can predict how long they can be

```

programs need this but this is memory unsafe for us. in example with buffer we can just add a simple if statement and secure our mem. but in heap we cant. program easly can take more than we expected.

ty for attention 

