1. Fixed Stack and Dynamic Stack using Interface
interface Stack {
void push(int item);
int pop();
}
class FixedStack implements Stack {
int[] stack;
int top = -1;
FixedStack(int size) {
stack = new int[size];
}
public void push(int item) {
if (top == stack.length - 1)
System.out.println("Stack Overflow");
else
stack[++top] = item;
}
public int pop() {
if (top == -1) {
System.out.println("Stack Underflow");
return -1;
}
return stack[top--];
}
}
class DynamicStack implements Stack {
int[] stack = new int[2];
int top = -1;
public void push(int item) {
if (top == stack.length - 1) {
int[] temp = new int[stack.length * 2];
System.arraycopy(stack, 0, temp, 0, stack.length);
stack = temp;
}
stack[++top] = item;
}
public int pop() {
if (top == -1)
return -1;
return stack[top--];
}
}
public class StackDemo {
public static void main(String[] args) {
FixedStack fs = new FixedStack(3);
fs.push(10);
fs.push(20);
fs.pop();
DynamicStack ds = new DynamicStack();
ds.push(1);
ds.push(2);
ds.push(3);
}
}
2. Student Management System – Exception Handling
class InvalidMarksException extends Exception {
InvalidMarksException(String message) {
super(message);
}
}
public class StudentExceptionDemo {
static void validateMarks(int marks) throws InvalidMarksException {
if (marks < 0 || marks > 100)
throw new InvalidMarksException("Marks must be between 0 and 100");
}
public static void main(String[] args) {
try {
validateMarks(120);
} catch (InvalidMarksException e) {
System.out.println(e.getMessage());
}
try {
String name = null;
name.length();
} catch (NullPointerException e) {
System.out.println("Null student record");
}
try {
int a = 10 / 0;
} catch (ArithmeticException e) {
System.out.println("Arithmetic Exception");
}
try {
throw new IllegalAccessException("Unauthorized access");
} catch (IllegalAccessException e) {
System.out.println(e.getMessage());
}
try {
throw new RuntimeException("Unexpected runtime error");
} catch (RuntimeException e) {
System.out.println(e.getMessage());
}
}
}
3. Command Line Arguments – Arithmetic Operations
public class CommandLineArithmetic {
public static void main(String[] args) {
try {
int a = Integer.parseInt(args[0]);
int b = Integer.parseInt(args[1]);
System.out.println("Addition = " + (a + b));
System.out.println("Subtraction = " + (a - b));
System.out.println("Multiplication = " + (a * b));
System.out.println("Division = " + (a / b));
} catch (NumberFormatException e) {
System.out.println("String argument found");
} catch (ArrayIndexOutOfBoundsException e) {
System.out.println("Insufficient arguments");
}
}
}
4. Generic Method isIn()
class GenMethDemo {
static <T> boolean isIn(T x, T[] arr) {
for (T item : arr) {
if (item.equals(x))
return true;
}
return false;
}
public static void main(String[] args) {
Integer[] nums = {1, 2, 3, 4};
System.out.println(isIn(3, nums));
}
}
5. Generic Stack using Student Class
class Stack<E> {
private E[] arr;
private int top = -1;
Stack(int size) {
arr = (E[]) new Object[size];
}
void push(E item) {
arr[++top] = item;
}
E pop() {
return arr[top--];
}
boolean hasElements() {
return top >= 0;
}
}
class Student {
String name;
int id;
Student(String name, int id) {
this.name = name;
this.id = id;
}
}
public class GenericStackDemo {
public static void main(String[] args) {
Stack<Student> s = new Stack<>(2);
s.push(new Student("Rahul", 101));
s.push(new Student("Reddy", 102));
while (s.hasElements()) {
Student st = s.pop();
System.out.println(st.name + " " + st.id);
}
}
}
6. File Handling – Feedback System
import java.io.*;
public class FeedbackSystem {
public static void main(String[] args) {
try (
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
FileWriter fw = new FileWriter("feedback.txt")
) {
System.out.print("Enter Name: ");
String name = br.readLine();
System.out.print("Enter Course: ");
String course = br.readLine();
System.out.print("Enter Feedback: ");
String feedback = br.readLine();
fw.write(name + "\n");
fw.write(course + "\n");
fw.write(feedback);
System.out.println("Feedback saved successfully");
} catch (IOException e) {
System.out.println("File error");
}
}
}
7. Applet – Result Display
import java.applet.Applet;
import java.awt.Graphics;
public class ResultApplet extends Applet {
int m1, m2;
public void init() {
m1 = Integer.parseInt(getParameter("m1"));
m2 = Integer.parseInt(getParameter("m2"));
}
public void paint(Graphics g) {
int total = m1 + m2;
g.drawString("Total Marks = " + total, 20, 20);
g.drawString(total >= 50 ? "PASS" : "FAIL", 20, 40);
}
}
8. AWT Login Window
import java.awt.*;
import java.awt.event.*;
public class LoginAWT extends Frame implements ActionListener {
TextField username, password;
Label result;
LoginAWT() {
username = new TextField();
password = new TextField();
password.setEchoChar('*');
Button login = new Button("Login");
result = new Label();
setLayout(new GridLayout(4, 1));
add(username);
add(password);
add(login);
add(result);
login.addActionListener(this);
password.addActionListener(this);
setSize(300, 200);
setVisible(true);
}
public void actionPerformed(ActionEvent e) {
if (username.getText().equals("admin") &&
password.getText().equals("123"))
result.setText("Login Successful");
else
result.setText("Login Failed");
}
public static void main(String[] args) {
new LoginAWT();
}
}
9. JavaFX Online Examination UI
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.*;
import javafx.scene.layout.VBox;
import javafx.stage.Stage;
public class ExamUI extends Application {
public void start(Stage stage) {
Label q = new Label("2 + 2 = ?");
RadioButton a = new RadioButton("3");
RadioButton b = new RadioButton("4");
ToggleGroup tg = new ToggleGroup();
a.setToggleGroup(tg);
b.setToggleGroup(tg);
Button next = new Button("Next");
next.setOnAction(e -> {
if (tg.getSelectedToggle() == null)
System.out.println("Please select an option");
else
System.out.println("Answer saved");
});
VBox root = new VBox(10, q, a, b, next);
stage.setScene(new Scene(root, 300, 200));
stage.setTitle("Online Exam");
stage.show();
}
public static void main(String[] args) {
launch(args);
}
}
