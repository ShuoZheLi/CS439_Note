## C 语言结构体的一些常见用法（实践非理论）
### gcc 编译参数
gcc main.c -O0 -g
-g GDB debug
-O0 无优化

### 插入汇编
```C
int func(int x){
	__asm__(
	"movq $0xffffffffffffffff, %rax 					\n\t"
	"movl $0x0, %eax 					\n\t"
	"addq $0, %rax 					\n\t"
	"setne %al 					\n\t"
    "ret							\n\t"		
		);
}
```

### GDB
* break +行数 +函数名称 ex: main
* layout asm 显示汇编代码
* si 一个一个汇编指令
* ni 可以跳过一个函数

### 结构体的构造
```C
struct ListNode{
	int value;
	struct ListNode *prev;
	struct ListNode *next;
}*head; //这里已经默认初始化了一个变量head指针，如果不加*则可以按head.value访问

typedef struct{ //这里typedef让我我们可以像原始数据类型那样使用这个自定义类型
	int value;
	struct ListNode *prev;
	struct ListNode *next;
}ListNode;
EX：ListNode head;
    head.value = 1;
```

### 指针的一些fun fact
假设我们定义了一个结构体
```C
typedef struct{
	int value;
	struct ListNode *prev;
	struct ListNode *next;
}ListNode;
```
那么我们在初始化ListNode时候，我们最好描述下malloc返回指针的类型
```
ListNode *head = (ListNode*)malloc(sizeof(ListNode));
```
因为如果类型不强调，就有可能出现这个问题，虽然也能编译通过 :D
```char *head = malloc(sizeof(ListNode));```
但运行问题不言而喻

### free heap objects
```Warning: attempt to free a non-heap object ‘list’```
```Never free array, or primitive data type```
only free ```heap object``` definied by __***struct***__

### static variable
```C
static int x = 2;
// static variable is declared inside of function but exist throughout the life of the program
// it can be declared every where in the program
```
```static variable in static data segment```
So, not like stack variable get reset each time