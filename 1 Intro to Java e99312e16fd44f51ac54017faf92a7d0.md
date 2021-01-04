# 1.Intro to Java

## 1.1 Essentials

Study Guide Link: [http://fa20.datastructur.es/materials/lectures/lec1/lec1.html](http://fa20.datastructur.es/materials/lectures/lec1/lec1.html)

- **Recall Question:**
    1. Redo HW0 exercise 1.
    2. Redo HW0 exercise 2.
    3. Redo HW0 exercise 3.
    4. What's the difference between do-while and while?

## **Notes:**

### 1. TriangleDrawer.java

The drawTriangle method should take one parameter named N, and it should print out a triangle exactly like your triangle from exercise 1a, but N asterisks tall instead of 5.

```java
public class TriangleDrawer {
    public static void drawTriangle(int N) {
        int row = 1;
        int col = 1;
        while(row < N + 1){
            while(row >= col){  
                System.out.print("*");  //print第i行有i个*， 不换行
                col = col + 1;
            }
            row = row + 1;
            col = 1;  //col 始终保持1
            System.out.println();  //打印完换行
        }
    }
    
    public static void main(String[] args) {
        TriangleDrawer.drawTriangle(10);
    }
 }
```

### 2. ClassNameHere.java

while loop vs. for loop

/** Returns the maximum value from m. */

```java
//1.while loop
public class ClassNameHere {
    public static int max(int[] m){
        int i = 0;     //initializaton
        int max_num = 0;
        while(i < m.length){     //termination
            if (m[i] > max_num){
                max_num = m[i];
            }
            i = i + 1;     //increment
        }
        return max_num;
    }
    public static void main(String[] args){
        int[] numbers = new int[]{9,2,15,2,22,10,6};
        System.out.println(max(numbers));
    }
}

// 2.for loop
public class ClassNameHere {
    public static int max(int[] m){
        int max_num = 0;
				
				//for(initialization; termination; increment)
        for (int i=0; i<m.length; i++){  
            if (m[i] > max_num){
                max_num = m[i];
            }
        }
        return max_num;
    }
    public static void main(String[] args){
        int[] numbers = new int[]{9,2,15,2,22,10,6};
        System.out.print(ClassNameHere.max(numbers));
        // System.out.println(max(numbers));
    }
}
```

### 3. BreakContinue.java

Continue = "skip". 比如string contain “horse“， 一次含有horse的都不print出来。

Break 相当于只执行一次。

```java
/** Exercise 4 
 * Write a function windowPosSum(int[] a, int n) that replaces each element a[i] with 
 * the sum of a[i] through a[i + n], but only if a[i] is positive valued. If there are 
 * not enough values because we reach the end of the array, we sum only as many values 
 * as we have.
*/
public class BreakContinue {
    public static void windowPosSum(int[] a, int n){
        for (int i = 0; i < a.length; i++){
            //if the value is less than 0
            if (a[i] < 0){
                continue;
            }
            int a_sum = 0;
            //sum a[i] to a[i+n]
            for (int j = 0; j <= n; j++){
                a_sum += a[i+j];
                if (i+j+1 == a.length){
                    break;
                }
            }  
            a[i] = a_sum;
        }
    }

    public static void main(String[] args){
        int[] a = {1,2,-3,4,5,4};
        int n = 3;
        windowPosSum(a, n);

        //Should print 4,8,-3,13,9,4
        System.out.println(java.util.Arrays.toString(a));
    }
}
```

### 4. Do-while vs. while

The difference between do-while and while is that do-while evaluates it expression at the bottom of the loop instead of the top. Therefore, the statements within the do block are always executed at least once.

## 1.2 Static vs. Non-Static

Study Guide Link: [http://fa20.datastructur.es/materials/lectures/lec2/lec2.html](http://fa20.datastructur.es/materials/lectures/lec2/lec2.html)

- **Recall Question:**
    1. What's the difference between static and non-static method?
    2. What is instance variable?
    3. What is the use for javac and java?
    4. Explain each word in "public static void main(String[] args)".
    5. What is "this" in a method?

## **Notes:**

### 1. Static vs. Non-Static

- **Static methods** are invoked using the class name, e.g. Dog.makeNoise(); Static methods can’t access “my” instance variables, because there is no “me”. (eg. cannot access weightInPounds.)
- **Instance methods** are invoked using an instance name, e.g. maya.makeNoise();

More details: The distinction between static and instance methods is incredibly important. Instance methods are actions that can only be taken by an instance of the class (i.e. a specific object), whereas static methods are taken by the class itself. An instance method is invoked using a reference to a specific instance, e.g. d.bark(), whereas static methods should be invoked using the class name, e.g. Math.sqrt(). Know when to use each.

### 2. Instance variables/ non-static variables

Dog class has its own variable, which is also known as **instance variables** or non-static variables.

### 3. Command line compilation and execution

javac is used to compile programs. java is used to execute programs. We must always compile before execution.

```bash
//DogLauncher is a "client" of Dog class. （两个class间的关联）
$ javac DogLauncher.java
$ java DogLauncher
```

### 4. public static void main(String[] args)

- public: So far, all of our methods start with this keyword.
- static: It is a static method, not associated with any particular instance.
- void: It has no return type.
- main: This is the name of the method.
- String[] args: This is a parameter that is passed to the main method.

### 5. "This"

Inside a method, we can use the this keyword to refer to the **current instance**. This is equivalent to **self** in Python.

## ** Git

**1. Git  教程：[https://sp18.datastructur.es/materials/guides/using-git.html](https://sp18.datastructur.es/materials/guides/using-git.html)**

2. Git 基本操作：https://sp18.datastructur.es/materials/lab/lab1setup/lab1setup.html

3. Video: (example of kung_pao_tofu) https://www.youtube.com/watch?v=KoPxeLqWRTY

![1%20Intro%20to%20Java%20e99312e16fd44f51ac54017faf92a7d0/Screen_Shot_2564-01-02_at_6.15.11_PM.png](1%20Intro%20to%20Java%20e99312e16fd44f51ac54017faf92a7d0/Screen_Shot_2564-01-02_at_6.15.11_PM.png)

*视频中用到的git command：

subl kung_pao_tofu.txt   //write something to the file

git   //show all git command

git init   //create an empty git repository

git add ./tofu/kung_pao_tofu.txt  //tells git this file exist

git status  //git’s thinking

git commit -m “added tofu recipes”  //add message and stick to the safe

git log  //show the commit safe number

git show + (commit number)  //take me to the box and show the detail

git checkout + commit number(use git log to check the number) + ./tofu   //want to old stuff back