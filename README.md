# hello-word
have a try

public class Insert {
	static int count = 0;
    /***
    * 把n个待排序的元素看成一个有序表和一个无序表， 开始有序表只包含一个元素，无序表中包含n-1个元素，
    * 排序过程中每次从无序表中取出第一个元素，把它的排序码依次与有序表元素的排序码进行比较， 将它插入到有序表中的适当位置，使之成为新的有序表。
    */
   public static void runInsertSort(int[] a) {
       for (int i = 1; i < a.length; i++) {
           int insertVal = a[i];
           // insertValue准备和前一个数比较
                      int index = i - 1;

           while (index >= 0 && insertVal < a[index]) {
               // 将把a[index]向后移动
                               a[index + 1] = a[index];
               // 让index向前移动一位
                              index--;
           }

           // 将insertValue插入到适当位置
                       a[index + 1] = insertVal;
           System.out.println("indexPos>>>"+(index+1));
           System.out.print("第" + (i) + "次排序结果：");
           for (int k = 0; k < a.length; k++) {
               System.out.print(a[k] + "\t");
           }
           System.out.println("");
           count++;
       }
       System.out.print("最终排序结果：");
       for (int l = 0; l < a.length; l++) {
           System.out.print(a[l] + "\t");
       }
   }

public static void main(String[] args) {
       int[] array = new int[100];  
       for (int k = 0; k < array.length; k++) {  
           array[k] = (int) (Math.random() * 1000);  
       }
       System.out.print("排序之前结果为:");
       for (int i = 0; i < array.length; i++) {
           System.out.print(array[i] + "\t");
       }
       System.out.println("");
       runInsertSort(array);
       System.out.println("交换次数："+count);
   }
}
