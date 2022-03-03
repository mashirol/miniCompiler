# miniCompiler

仔细刻画代码执行使用的数据结构。

数据结构分为：1.全局使用的。2.局部使用的

*************************
词法分析使用状态机即可。

语法分析可采用自底向上或自顶向下。

1.自底向上：采用栈和状态机的形式完成。

2.自顶向下：采用递归实现。

语法分为：类定义，函数定义，变量定义。定义中包括变量和语句。

DEF--->STATE

STATE------>IFSTATE|FORSTATE|CALLSTATE.etc

*STATE----->EXP + STATE

EXP-------->NUM | ID | INFIX.etc

NUM | ID | INFIX.etc--->123abc+-*

*************************
语义分析采用遍历“语法分析树”的形式实现。在语法分析中使用EXPRESS完成。

语义分析完成字节码的编制。

字节码分为：1.变量的PUSH与STORE。2.函数的CALL与RETURN。3.JUMP,LOOP 4. create class等

**************************

EXPRESS完成语法树的构建，nud与led完成一些其他处理，核心在于递归调用EXPRESS


var expression = function (rbp){
var left; 
var t =token; 
advance();
left= t.nud(); 
while (rbp < token.lbp) {
t=token; 
advance(); 
left= t.led(left); 
}
return left; 
}

led(left) {
this.first = left;
this.second = expression(50);
return this;
}



 
