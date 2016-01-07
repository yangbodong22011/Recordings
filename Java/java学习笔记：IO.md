## 写文件的几种方法  
### 一：  写文件的几种方法。
```
package IO;

import java.io.*;

/**
 * Created by student on 12/22/15.
 */
public class Exercise4 {
    public static void main(String[] args) throws IOException{
        //DataOutputStream output = new DataOutputStream(new FileOutputStream("/home/student/IdeaProjects/JAVA/src/IO/Exercise19_1.txt",true));
        //FileOutputStream output = new FileOutputStream("/home/student/IdeaProjects/JAVA/src/IO/Exercise19_1.txt",true);
        //BufferedWriter output = new BufferedWriter(new FileWriter("/home/student/IdeaProjects/JAVA/src/IO/Exercise19_1.txt",true));
        //PrintStream output = new PrintStream(new FileOutputStream("/home/student/IdeaProjects/JAVA/src/IO/Exercise19_1.txt",true));
        PrintWriter output = new PrintWriter(new FileWriter("/home/student/IdeaProjects/JAVA/src/IO/Exercise19_1.txt",true));
        //FileWriter output = new FileWriter("/home/student/IdeaProjects/JAVA/src/IO/Exercise19_1.txt",true);
        for (int i = 0; i < 3; i++) {
            int a = (int)(Math.random()*1000);
            output.print(a);
            output.print(" ");
        }
        output.close();
    }
}

```