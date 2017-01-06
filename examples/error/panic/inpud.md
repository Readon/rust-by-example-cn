我们将要看到的最简单的错误处理机制就是 `panic`。它会打印一个错误消息，开始展开任务（译注：感觉此句翻译不好，望指正，原文为 starts unwinding the task），且通常退出程序。这里我们显式地在错误条件上调用 `panic`：

{panic.play}

这表明我们可以根据自己的想法来引发程序失败，但会出现一个问题：要是公主（princess）**没**得到礼物会发生什么？就像处理蛇那样的方式，我们**可以**针对空字符串（`""`）的检查进行显式地测试。问题在于程序员并没有习惯测试这些检查，除非编译器指出这些检查是必需的。

为了使这变得更可靠，我们需要编译器指出可能没有礼物的情形。在本章，我们将学习使用 `Option` 来应对这种情况，以及各种各样的函数来处理 `Option` 的一个或多个用法的结果。