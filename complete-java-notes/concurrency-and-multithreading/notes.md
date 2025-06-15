Thread has a group, name, id, state, priority(1 min to 10 max)
Thread.toString gives \[name, id, group\]

Creating thread

Runnable is an interface with only one method run
Thread class implements runnable

1. Extend Thread class and overwrite run method and create instance of this new class
2. Implement Runnable with run method and create instance of this new class, pass this instance to Thread constructor to create thread. Lambda expression is instance of Runnable.
3. Using Executor

Thread.start() adds thread in current thread group and calls native start0()
Thread creation is native operation becuase is uses platform specific libraries and performance reasons.

Runnable interface is a functional interface.
Runnable type is target for lambda expression

Runnable myrunnable = () -> {
// task
}
Thread myThread = new Thread(myRunnable);
myThread.start();

Thread implements Runnable, has run() and start(). CustomThread extends Thread. new CustomThread() start.
Since Java doesn't allow multiple inheritance, you can't extend any other class if you extend Thread class. 
Tight coupling with Thread class.

Any class can implement Runnable.
Can pass Runnanle instance, Anonymous class, lambda expression or method reference to Thread constructor.
Less control over thread behaviour and properties as they can't be accessed from run method.

After being interrupted, thread doesn't immediately change it's state (there is no particular state for interrupted)
If the thread is sleeping or waiting:  The thread moves to the RUNNABLE state after throwing an InterruptedException.
If the thread is actively running:  The thread remains in the RUNNABLE state until it explicitly checks the interrupted flag and decides how to handle it.
If the thread is blocked on I/O or synchronization:The thread remains in the BLOCKED state until the blocking operation completes or the thread reacts to the interruption.
