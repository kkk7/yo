package codility3;

import java.awt.Color;
import java.awt.FlowLayout;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.print.PrinterJob;
import javax.print.attribute.HashPrintRequestAttributeSet;
import javax.print.attribute.PrintRequestAttributeSet;
import javax.print.attribute.standard.DialogTypeSelection;
import javax.swing.JButton;
import javax.swing.JColorChooser;
import javax.swing.JFrame;
import javax.swing.JTextField;



public class Codility3 extends JFrame {

     static int x,z;
     static int[]A=new int[]{20,30,22,50,-46,46,20,10,500,33,9,8,31,40,5,33};
     static int[]B=new int[]{-1,33,-40,5,1,-6,200,10,5,32,9,8,31,50,1,3,6,-5,5,5,9,7,4,64,5,-406};
     public static int solution(int[] B, int[] A) {
        // write your code in Java SE 8
             bbb(B);
             bbb(A);
             // System.out.println("A0: "+A[0]+"");
             // System.out.println("B0: "+B[0]+"");
             // System.out.println("Array A After Bubble Sort");
              for(int i=0; i < A.length; i++){
             //  System.out.print(A[i] + " ");
               }
             // System.out.println("");
             // System.out.println("Array B After Bubble Sort");
              for(int i=0; i < B.length; i++){
            //   System.out.print(B[i] + " ");
               }
            //   System.out.println("");
        
                 for(int j=0; j<B.length; j++)
                 for(int i=0; i<A.length; i++){
                     if(B[j]==A[i])
                         x=A[i];
                 }
              return x;
    }
    public static void main(String[] args) {
       Codility3 w = new Codility3();
       w.setVisible(true); 
       System.out.println("Wynik: "+solution(B,A)+"");
       
             
    }
    public Codility3() {
    this.setSize(300, 300);
    this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    this.setLayout(new FlowLayout());


    JButton p = new JButton(" Drukuj ");
    JTextField pp = new JTextField("Wynik: ");
    JTextField pp2 = new JTextField(+solution(B,A)+"   ");
    p.addActionListener(new ActionListener() {
      public void actionPerformed(ActionEvent event) {
        final PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
        attributes.add(DialogTypeSelection.COMMON);
        PrinterJob printJob = PrinterJob.getPrinterJob();
        printJob.printDialog(attributes);

      }
    });
    this.add(pp);
    this.add(pp2);
    this.add(p);
   }
   
        public static void bbb(int[] A) {
              int n = A.length;
              int tt = 0;
         for(int i=0; i < n; i++){
                      for(int j=1; j < (n-i); j++){
                            if(A[j-1] < A[j]){
                                      tt = A[j-1];
                                      A[j-1] = A[j];
                                   A[j] = tt;
              }}}   
      }
}
