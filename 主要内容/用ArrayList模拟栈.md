# 用ArrayList模拟栈
---
---


```java
import java.lang.reflect.Array;
import java.util.ArrayList;
import java.util.List;

public class main{
    public static void main(String[] args){
        stackDemo s = new stackDemo();
        s.push(1);
        s.push(2);
        s.push(3);
        s.push(4);
        System.out.println(s.peek());
    }
}


class stackDemo{

    List<Object> stack;
    public stackDemo(){
    stack = new ArrayList<>();
    }

    public void push(Object o){
        stack.add(o);
    }

    public boolean pop(){
        if(stack.isEmpty() == true){
            return false;
        }
        stack.remove(stack.size()-1);
        return true;
    }

    public Object peek(){
        if(stack.isEmpty() == true){
            return false;
        }
        return stack.get(stack.size()-1);//这里直接return就算是peek了。不用System.Out.Println();
    }
    public boolean isEmpty() {
        return stack.isEmpty();
    }
}
```

