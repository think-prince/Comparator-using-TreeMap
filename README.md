# Comparator-using-TreeMap
Coding for Comparator using TreeMap

import java.util.Iterator;
import java.util.Comparator;
import java.util.TreeSet;

public class BookComparatorTreeMap {
    private String title;
    private double price;

    BookComparatorTreeMap(String title, double price){
        this.title = title;
        this.price = price;
    }

    public String getTitle(){
        return title;
    }
    public double getPrice(){
        return price;
    }
}

class MyComparator implements Comparator{
    public int compare(Object o1, Object o2){
        BookComparatorTreeMap book1 = (BookComparatorTreeMap) o1;
        BookComparatorTreeMap book2 = (BookComparatorTreeMap) o2;
        if(book1.getPrice() > book2.getPrice()){
            return -1;
        }
        else
        return 1;
    }
}

class TestBook{
    public static void main(String[] args) {

        BookComparatorTreeMap b1 = new BookComparatorTreeMap("php", 400.00);
        BookComparatorTreeMap b2 = new BookComparatorTreeMap("java", 500.00);
        BookComparatorTreeMap b3 = new BookComparatorTreeMap("C", 300.00);
        MyComparator o = new MyComparator();
        TreeSet t = new TreeSet(o);
        t.add(b1);
        t.add(b2);
        t.add(b3);
        BookComparatorTreeMap b;
        Iterator it = t.iterator();
        while(it.hasNext()){
           b=(BookComparatorTreeMap) it.next();
            System.out.println("Title:"+b.getTitle()+ "Price: "+b.getPrice());
        }
    }
}
