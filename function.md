在 ECMAScript中，Function（函数）类型实际上是引用类型。每个函数都是Function类型的对象
而且都与其他引用类型一样具有属性和方法。由于函数是对象，因此函数名实际上也是一个指向函数对象的引用类型变量
一，函数的声明方式：
1，普通方式：  function fun(num1, num2)   {  return  num1+num2 };
2,使用变量方式声明 ： var fun2=function(a,b){ return a+b }
3,使用new创建函数 var fun3=new Function（'n1','n2';'return n1+n2')
二，函数作为参数来传递：
ECMAScript 中的函数名本身就是变量，所以函数也可以作为值来使用。 也就是说，不仅可以像传递参数一样把一个函数传递给另一个函数，而且可以将一个函数作为另一个函数的结果返回。
例子： function add(a,b) {
        return a+b;
    }
        function show(fun,num) {
            return fun(num,88);
        }
        alert(show(add,66));  //154
函数的内部属性：
1，arguments属性：指向一个类似数组但不是数组的对象，存储的是实际传递给函数的参数，而不是局限于函数声明所定义的参数列表
 function show (a,b) { if (arguments.length==2) alert(a+b); else if (arguments.length==3) alert(.....)}  show("hha","hehe","heihei") 备注：函数本身就赋予两个变量，就只会显示两个，但是arguments 实际调用是实际上函数传过来的对象。 （忘记就去百度吧）
2，length属性：函数定义时所指定参数的个数
3，arguments中callee属性：他表示对函数本身的引用，---例子：function jie(n){if (n=1) return 1; else return n*arguments.callee(n-1)备注：无论前面jie名字变不变，}
4，全局变量和局部变量 ：  全局变量--就是函数外面的变量，所有的函数都可以调用，  局部变量--在函数里面的变量，只能函数自身调用。
