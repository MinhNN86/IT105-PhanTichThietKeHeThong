```mermaid
stateDiagram-v2
    [*] --> TaoMoi: createOrder()

    TaoMoi --> ChoThanhToan: confirmOrder()
    ChoThanhToan --> DangGiao: submitPayment() [paymentSuccess]
    ChoThanhToan --> Huy: submitPayment() [paymentFailed]
    
    DangGiao --> HoanThanh: shipOrder()
    DangGiao --> Huy: cancelOrder()
    
    HoanThanh --> [*]: orderCompleted()
    Huy --> [*]: orderCanceled()

```