
import java.util.Scanner;
//----------- Первый вариант с арабскими цифрами (работает) ------------

//
//public class Calculator {
//    static Scanner scanner = new Scanner(System.in);
//    public static void main(String[] args){
//        int a = getInt(), b = getInt();
//        char operation = getOp();
//        int result = calc(a, b, operation);
//        System.out.print("Попали " + result);
//    }
//    public static int getInt() {
//        System.out.print("задайте через Enter два целых числа, координаты: ");
//        int num;
//        if(scanner. hasNextInt()){
//            num = scanner.nextInt();
//        }else{
//            System.out.print("Промах, Вы совершили ошибку ");
//            scanner.next();
//            num = getInt();
//        }
//        return  num;
//    }
//
//    public static char getOp(){
//        System.out.println("задать операцию ");
//               char operation;
//               if (scanner.hasNext()){
//                   operation = scanner.next().charAt(0); // это делается для определения, является ли char действие (+-/*)
//               }else{
//                   System.out.print("Промах, Вы совершили очередную ошибку");
//                   scanner.next();
//                   operation = getOp();
//               }
//        return  operation;
//    }
//    public static int calc( int a, int b, char operation){
//        int result;
//
//        switch(operation) {
//            case '+':
//                result= a + b;
//                break;
//            case '-':
//                result= a - b;
//                break;
//            case '*':
//                result= a * b;
//                break;
//            case '/':
//                result= a / b;
//                break;
//            default:
//                System.out.printf("Error! Enter correct operator");
//                result = calc(a, b, getOp()); //рекрусия
//        }
//        return result;
//
//    }
//}

//_______Второй вариант с римскими и арабскими не рабочий вариаент ___________________

public class Calculator {
    static Scanner scanner = new Scanner(System.in);
    public static void main(String[] args){
        int a = getInt(), b = getInt();
//        String num1 = getInt(), num2 = getInt();
        char operation = getOp();
        int result = calc(a, b, operation);
        System.out.print("Попали " + result);
    }
    public static int getInt() {
        System.out.print("задайте через пробел два целых числа, координаты: ");
        int num;
        String  num1 = Integer.parseInt(num);
        if(scanner. hasNextInt()){
            num = scanner.nextInt();
        }if (!scanner. hasNextInt()){
            num1 = convert(num);
        }else{
            System.out.print("Промах, Вы совершили ошибку ");
            scanner.next();
            num = getInt();
            num1 = getInt();
        }return  num, num1;
    }
    public static char getOp(){
        System.out.println("задать операцию ");
        char operation;
        if (scanner.hasNext()){
            operation = scanner.next().charAt(0);
        }else{
            System.out.print("Промах, Вы совершили очередную ошибку");
            scanner.next();
            operation = getOp();
        }
        return  operation;
    }

    public static int convert(String с) {
        if (с.equals("I")) return 1;
        if (с.equals("II")) return 2;
        if (с.equals("III")) return 3;
        if (с.equals("IV")) return 4;
        if (с.equals("V")) return 5;
        if (с.equals("VI")) return 6;
        if (с.equals("VII")) return 7;
        if (с.equals("VIII")) return 8;
        if (с.equals("IX")) return 9;
        if (с.equals("X")) return 10;
        return 0;
    }
    public static int calc( int a, int b, char operation){
        int result;

        switch(operation) {
            case '+':
                result= a + b;
                break;
            case '-':
                result= a - b;
                break;
            case '*':
                result= a * b;
                break;
            case '/':
                result= a / b;
                break;
            default:
                System.out.printf("Error! Enter correct operator");
                result = calc(a, b, getOp()); //рекрусия
        }
        return result;
    }
}
