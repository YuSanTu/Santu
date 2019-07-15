### 主题：日报

### 汇报人：余振垚

### 日期：2019年7月15日 周一

### 内容：

#### 今日学习内容：

- 塔罗牌项目前端部分
- Gitee注册和git使用

#### 明天学习计划：

- Bootstrap知识

### 面试题：

###### 题目一：

```java
package com.xzy;
/*题目描述
        在一个二维数组中（每个一维数组的长度相同），每一行都按照从左到右递增的顺序排序，
        每一列都按照从上到下递增的顺序排序。请完成一个函数，输入这样的一个二维数组和一个整数
        ，判断数组中是否含有该整数。

        时间限制：1秒 空间限制：32768K
        */

import java.util.Scanner;

public class text0715 {

   public void Find(int target,int [][]data,int row,int col){
       /*for(int i=0;i<row;i++)
       {
           for(int j=0;j<col;j++)
           {
               System.out.print(data[i][j]+" ");
           }
           System.out.println();
       }*/
        int i,j;

       for(i=0,j=col-1;i<row;)
       {
           if(target>data[i][j]){
               i++;
           }else{
               break;
           }
       }
       for(j=0;i<col;)
       {
           if(target>data[i][j]){
               j++;
           }else if(target==data[i][j]){
               break;
           }
       }
       if(i==row||j==col)
       {
           System.out.println("找不到值");
       }else{
           System.out.println("找到了值");
       }
    }


    public static void main(String[] args) {
        //1.首先构建二维数组
        int row,col;
        int target;
        Scanner in=new Scanner(System.in);
        System.out.println("请输入这个二维数组有多少行");
        row=in.nextInt();
        System.out.println("请输入这个二维数组有多少列");
        col=in.nextInt();
        int [][]data=new int[row][col];
        System.out.println("请输入数组的值");
        for(int i=0;i<row;i++)
        {
            for(int j=0;j<col;j++)
            {
                data[i][j]=in.nextInt();
            }
        }



        System.out.println("请输入你要查找要的值");
        target=in.nextInt();
        //2.进行查找
        text0715 text=new text0715();
        text.Find(target,data,row,col);
    }
}

```

###### 题目二：

```java
package com.xzy;

import java.util.Scanner;

/*题目描述
        请实现一个函数，将一个字符串中的每个空格替换成“%20”。
        例如，当字符串为We Are Happy.则经过替换之后的字符串为We%20Are%20Happy。
        时间限制：1秒 空间限制：32768K
        */
public class text0715_2 {

    public String replaceSpace(StringBuffer str) {

        return str.toString().replaceAll(" ","%20");
    }

    public static void main(String[] args) {
        StringBuffer str=new StringBuffer("We are happy");
        System.out.println(str);
        String freshtr;
        freshtr=new text0715_2().replaceSpace(str);
        System.out.println(freshtr);
    }
}

```

