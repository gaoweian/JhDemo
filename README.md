##Java——集合
* 1、Set
 * a.创建
 * b.添加元素（add）
 * c.删除元素（remove）
 * d.清空（clear）
 * e.遍历（for——each，Iterator）
 ```
import java.util.*;
public class SetDemo{
    public static void main(String[] args){
        //创建对象
        Set<String> s = new HashSet<String>();
        //添加元素
        s.add("A");
        s.add("C");
        s.add("B");
        s.add("D");
        //返回s中的元素个数
        System.out.println("s中的元素个数:"+s.size());
        //删除指定元素
        s.remove("A");
        //清空
        s.clear();
        //直接输出所有元素
        System.out.println(s);
        //for-each遍历
        for(String i:s){
            System.out.println(i);
        }
        //迭代器
        Iterator  a  =  s.iterator();
        while(a.hasNext()){
            System.out.println(a.next());
        }
    }
}
```
* 特性：
 * HashSet 能够快速定位一个元素。 
 * TreeSet 将放入其中的元素按序存放。
 
* 2、 List
 * a.创建
 * b.添加
 * c.查询
 * d.删除
 * e.遍历
 * f.清空
 ```
import java.util.*;
public class ListDemo{
    public static void main(String[] args){
        //创建对象
        List<String> l = new ArrayList<String>();
        //List<String> l = new LinkedList<String>();
        //添加元素
        l.add("A");
        l.add("C");
        l.add("D");
        l.add("B");
        //返回l中的元素个数
        System.out.println("l中的元素个数:"+l.size());
        //查询
        System.out.println("查询0号索引的内容:"+l.get(0));
        //删除指定元素
        l.remove("A");
        清空所有元素
        l.clear();
        for-each遍历
        for(String i:l){
            System.out.println(i);
        }
        //迭代器
        Iterator  a  =  l.iterator();
        while(a.hasNext()){
            System.out.println(a.next() );
        }
    }
}
```
* 特性：
 * ArrayList 实现一个数组，它的规模可变并且能像链表一样被访问。它提供的功能类似Vector类但不同步，它是以Array方式实现的List，允许快速随机存取
 * LinkedList实现一个链表，提供最佳顺序存取，适合插入和移除元素。由这个类定义的链表也可以像栈或队列一样被使用。提供最佳顺序存取，适合插入和移除元素。
 
* 3、Map
 * .创建
 * b.添加
 * c.查询
 * d.删除
 * e.遍历
 * f.清空
 ```
import java.util.*;
public class MapDemo{
     public static void main(String[] args){
         //创建对象
        Map<String,String>  hm = new  HashMap<String,String>();
        //Map<String,String>  hm = new  LinkedHashMap<String,String>();
        //添加元素
        hm.put("1","a");
        hm.put("2","b");
        hm.put("6","Eric");
        hm.put("3","d");
        hm.put("7","Eric");
        //返回hm中的元素个数
        System.out.println("hm中的元素个数:"+hm.size());
        hm.remove("1");//删除指定数据
        hm.clear();//清空所有元素
        hm.get("7");//查询，返回7这个键中的value
        System.out.println(hm.entrySet());//遍历
        Set keys = hm.keySet();//得到所有的key，并保存在一个Set中
        //遍历
        Iterator  i  =  keys.iterator();
        while(i.hasNext()){
            String key = (String)i.next(); 
            String value = (String)hm.get(key);
            System.out.println(key+"------"+value);
        }
     }
}
```
* 特性：
 * HashMap 实现一个键到值映射的哈希表，通过键取得值对象，没有顺序，通过get(key)来获取value，允许存储空对象，而且允许键是空(由于键必须是唯一的，当然只能有一个)；
 * HashTable 实现一个映象，所有的键必须非空。为了能高效的工作，定义键的类必须实现hashcode()方法和equal()方法。这个类是前面java实现的一个继承，并且通常能在实现映象的其他类中更好的使用。
 * 所以说：当元素的顺序很重要时选用TreeMap，当元素不必以特定的顺序进行存储时，使用HashMap。Hashtable的使用不被推荐，因为HashMap提供了所有类似的功能，并且速度更快。当你需要在多线程环境下使用时，HashMap也可以转换为同步的。
