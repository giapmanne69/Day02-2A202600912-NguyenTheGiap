# 3. Reflection

## Đóng góp trong nhóm

| Hoạt động | Minh đã làm gì? | Kết quả |
|---|---|---|
| Scan cá nhân | Đưa ra 7 problems | Nhóm có nhiều candidate về reporting/workflow |
| Pitch | Dev Weekly Report | Bài được vào shortlist |
| Challenge | Đặt câu hỏi liệu vấn đề nằm ở AI hay ở quy trình quản lý thông tin | Nhóm bổ sung phương án non-AI như Single Source of Truth và checklist |
| Workflow | Vẽ current state và future state workflow cho quá trình hiểu assignment | Nhóm xác định được bottleneck nằm ở bước tổng hợp requirement |
| Research | Tìm Slack AI, Microsoft 365 Copilot, Single Source of Truth và Fellow AI Meeting Notes | Nhóm thấy thị trường đã có nhiều giải pháp tổng hợp thông tin nhưng còn khoảng trống cho bài toán sinh viên |
| Rule / Workflow / Agent | Phân tích và lập luận vì sao nên chọn Workflow thay vì Agent | Nhóm thống nhất AI chỉ tham gia bước tổng hợp requirement và tạo checklist |

## Bảng dùng AI trong reflection

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai/hời hợt ở đâu? | Tôi sửa gì |
|---|---|---|---|---|
| Scan | Brainstorm các pain point trong học tập và làm project | Giúp mở rộng danh sách candidate problem nhanh | Đề xuất một số problem quá rộng hoặc khó đo lường | Chỉ giữ các problem có actor và workflow rõ |
| Workflow | Chuyển mô tả thành current state và future state workflow | Giúp nhìn rõ bottleneck và human boundary | Có lúc gom nhiều bước thành một bước duy nhất | Tách riêng bước tổng hợp requirement vì đó là bottleneck chính |
| Research | Tìm các sản phẩm và pattern tương tự trên thị trường | Nhanh chóng tìm được Slack AI, Copilot và Single Source of Truth | Một số nhận định ban đầu chưa chỉ rõ phạm vi áp dụng của từng tool | Kiểm tra lại tài liệu chính thức và bổ sung giới hạn của từng giải pháp |
| Problem Statement | Nhờ AI phản biện actor, metric và boundary | Giúp làm rõ success metric và điểm AI can thiệp | Có xu hướng đề xuất Agent quá sớm | Hạ phạm vi xuống Workflow vì phù hợp hơn với bài toán |

## Bài học

- Problem tốt không phải problem có vẻ "AI-first" nhất, mà là problem có actor, workflow, bottleneck và metric rõ ràng.
- Nhiều pain point thực tế có thể được giải quyết một phần bằng quy trình hoặc rule trước khi cần đến AI.
- Vẽ workflow giúp xác định chính xác AI nên tham gia ở đâu thay vì cố gắng tự động hóa toàn bộ hệ thống.
- Agent không phải lựa chọn mặc định. Với workflow tuyến tính và có human review rõ ràng, Workflow thường đơn giản và an toàn hơn.
- Research thị trường giúp nhận ra khoảng trống thật sự thay vì xây lại những gì đã tồn tại.
- AI hữu ích trong việc tổng hợp và cấu trúc thông tin, nhưng các quyết định cuối cùng vẫn cần con người kiểm tra và xác nhận.

Nếu làm lại:

```text
Tôi sẽ validate với nhiều PM hơn trước khi chốt metric 90 phút → 55 phút, vì baseline hiện tại chủ yếu đến từ trải nghiệm của tôi.
```