類似FSM的VM可以用ExecutionEngine的方式設計
包含
* context
  * 共享狀態的中心，類似暫存器
  * 至少要有可寫入的instruction pointer，用來支援jump/goto
* instruction-pool，
  * 放code的地方
* 執行指令的函式
  * Advance/VisitInstruction

* Advance/VisitInstruction等於實質上取出最基礎的指令再轉譯執行的行為
  * 如果指令集有function, basic block的概念，可以考慮binary translation
    * 例如用libtcc生成c再取得routine，這關係到驅動的單位要可以干涉指令到多深。因為interpreter通常無法直接干涉被轉譯的目標指令集。

可以把往常需要狀態機的設計改成類似VM的設計，用timer或eventloop來執行advance/visitInstruction。
