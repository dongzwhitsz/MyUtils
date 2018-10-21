    using System;
    namespace ConsoleApp1
    {    
        class Publisher    //定义一个可以事件发布器
        {
            public delegate int MyDelegate(int a);      //声明一个可以处理事件的委托
            public event MyDelegate MyEvent;            //声明一个事件，处理的委托类型为 MyDelegate
            public void test()
            {
                MyEvent(66);        //构造一个可以触发事件的函数； 
            }
        }
        class Receiver     //定义一个事件处理器
        {
            public int onMyEvent(int a) //接收事件者的事件处理函数，其也可以在发布者中
            {
                Console.WriteLine("hi , i am Receiver, {0}", a);
                return 0;
            }
        }
        class Program
        {
            static void Main(string[] args)
            {
                Publisher p = new Publisher();  //实例化一个事件发生器
                Receiver r = new Receiver();    //实例化一个事件处理器
                p.MyEvent += new Publisher.MyDelegate(r.onMyEvent); //在将事件处理器中用来处理的函数注册在事件发生器中的事件里面
                p.test();            
                Console.ReadKey();
            }
        }
    }
