- [基本用法与类型擦除](https://segmentfault.com/a/1190000005179142)
 1. 基本用法
 2. 类型擦除
 3. 类型擦除后的补偿：工厂设计模式和模板设计模式
 
- [泛型与数组](https://segmentfault.com/a/1190000005179147)
 1. 成功创建泛型数组的唯一方式是创建一个类型擦除的数组，然后转型，如代码： gia = (Generic<Integer>[])new Generic[SIZE]。（**在创建时转型**）
 2. 由于擦除，运行期的数组类型只能是 Object[]，如果我们立即把它转型为 T[]，那么在编译期就失去了数组的实际类型，编译器也许无法发现潜在的错误。因此，更好的办法是在内部最好使用 Object[] 数组，在取出元素的时候再转型。（**在取值时转型**）
 3. 使用 Class 对象作为类型标识是更好的设计。（**利用Array.newInstance(Class<?> componentType, int length)创建**）
 
 （**Java中不允许直接创建泛型数组，3种创建泛型数组的方法，第3种为最优**）
 
- [通配符的使用](https://segmentfault.com/a/1190000005337789)
 1. 数组的协变，Java中将数组设置成协变的 Fruit[] fruit = new Apple[10]; 泛型不支持协变
 2. 泛型设计的目的之一是要使运行时期的错误在编译期就能发现
 3. 上边界限定通配符:<? extends Fruit>   **泛型参数使用了受限制的通配符，所以我们失去了向其中加入任何类型对象的例子**
 4. **如果我们指定泛型参数为 <? extends Fruit> 时，add() 方法的参数变为 ? extends Fruit，编译器无法判断这个参数接受的到底是 Fruit 的哪种类型，所以它不会接受任何类型**
 5. 下边界限定通配符 List<? super T>
 6. 无边界通配符 List<?>
 7. 使用 List<? extends C> list 这种形式，表示 list 可以引用一个 ArrayList ( 或者其它 List 的 子类 ) 的对象，这个对象包含的元素类型是 C 的子类型 ( 包含 C 本身）的一种。
 8. 使用 List<? super C> list 这种形式，表示 list 可以引用一个 ArrayList ( 或者其它 List 的 子类 ) 的对象，这个对象包含的元素就类型是 C 的超类型 ( 包含 C 本身 ) 的一种。



