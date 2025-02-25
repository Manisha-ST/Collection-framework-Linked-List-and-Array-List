# Collection-framework-Linked-List-and-Array-List

package verysimplecalculator;
import java.util.Stack;

public class VerySimpleCalculator {
public static int evaluateExpression(String expression){
    Stack<Integer>stack=new Stack<>();
    for(char ch:expression.toCharArray()){
        if(Character.isDigit(ch)){
            stack.push(Character.getNumericValue(ch));
        }else if(ch=='+'){
            int operand2 = stack.pop();
            int operand1 = stack.pop();
            stack.push(operand1 + operand2);
        } else if (ch =='-') {
            int operand2 = stack.pop();
            int operand1 = stack.pop();
            stack.push(operand1 - operand2);
        }
    }
    return stack.pop();
        }
   
    public static void main(String[] args) {
       
        String expression="2+7-1";
        int result = evaluateExpression(expression);
        System.out.println("Result of the expression" + expression + ":" + result);
    }
}

Output:
Enter Integers Separated by Spaces:22 33 44 55
Initial Linked List:[22, 33, 44, 55]
Initial Array List:[22, 33, 44, 55]
Enter elements to be added (separated by spaces):3 29
Final Linked List:[3, 22, 33, 44, 55, 29]
Final Array List:[3, 22, 33, 44, 55, 29]
