# miniCompiler

*************************
词法分析使用状态机即可。
语法分析可采用自底向上或自顶向下。1.自底向上：采用栈和状态机的形式完成。2.自顶向下：采用递归实现。
语法分为：类定义，函数定义，变量定义。定义中包括变量和语句。

DEF--->STATE
STATE------>IFSTATE|FORSTATE|CALLSTATE.etc
*STATE----->EXP + STATE
EXP-------->NUM | ID | INFIX.etc
NUM | ID | INFIX.etc--->123abc+-*

*************************
语义分析采用遍历“语法分析树”的形式实现。在语法分析中使用EXPRESS完成。
语义分析完成字节码的编制
