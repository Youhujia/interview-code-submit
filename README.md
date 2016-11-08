public interface Inteator {
    boolean hasNext();
    Object next(); 
}
 
public interface Iterable {
    Iterator iterator();
}
 
public interface Collection extends Iterable {
    Iterator iterator();
}
 
public interface List extends Collection {
    Iterator iterator();
}
 
public class ArrayList implements List {
    public Iterator iterator() {
        return new Itr();
    }
     
    private class Itr implements Iterator {
        public boolean hasNext() {}
        public Object next(){} 
    }
}
 
 
Collection c = new ArrayList();
c.add("hello");
c.add("world");
c.add("java");
Iterator it = c.iterator();   //new Itr();
while(it.hasNext()) {
    String s = (String)it.next();
    System.out.println(s);
}
