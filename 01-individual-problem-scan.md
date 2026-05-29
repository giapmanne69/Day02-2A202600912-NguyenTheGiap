# 1. Problem Scan

Case: Thực hiện dự án phần mềm. Nhân vật: Giáp, Project Manager của 1 dự án phần mềm quản lý giám sát thi cử cho học sinh cấp 2 gồm có 15 người. Hàng tuần, A cần báo cáo tiến độ dự án lên cho nhà đầu tư, nhận thông tin mới từ phía BA về yêu cầu của khách hàng và giao công việc lại cho team Developer.

# Scan rộng

| # | Lăng kính | Problem quan sát được | Ai đang đau? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Mất thời gian | Đọc, tóm tắt key point nội dung các báo cáo hàng tuần của team Dev | PM | Mất 90 phút/Tuần |
| 2 | Lặp lại | Tạo lịch họp hàng tuần cho team trên Google Calendar | PM | Mất 15 phút/tuần |
| 3 | Mất thời gian | Viết tài liệu báo cáo tiến độ dự án mỗi 2 tuần/lần cho stakeholder | PM | Mất 60 phút/2 tuần |
| 4 | Pain từ người khác | Designer phải hỏi lại vì yêu cầu thiết kế giao diện PM gửi chưa rõ ràng | PM, Designer | Mất 3,4 lần hỏi |
| 5 | Pain từ người khác | Stakeholder hỏi tiến độ dự án nhưng report chưa hoàn thành | PM, Stakeholder | Bị hỏi 4-6 lần/ngày bắt đầu từ hạn nộp báo cáo tiến độ |
| 6 | AI có thể làm tốt hơn | Sắp xếp thứ tự chức năng ưu tiên cho team Dev | Team Dev, PM | Mất 60 phút/tuần |
| 7 | Mất thời gian | Kiểm soát các rủi ro của các chức năng hiện tại | Team Dev, PM | Mất 30 phút/ngày |

# Top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Dev Weekly Report | Workflow rõ, mất nhiều thời gian, cần cập nhật liên tục | Chọn key point thế nào |
| 2 | Priority Order | Quan trọng, quyết định các yếu tố về thời gian và chi phí | Khó để xác định nếu không nắm rõ ưu tiên yêu cầu của khách hàng |
| 3 | Meeting Calendar | AI có thể tham gia sắp xếp | Lịch trình có thể thay đổi do đột xuất |

## Problem Card #1 — Dev Weekly Report

**Problem 1 câu:**  
Mỗi thứ Bảy PM mất khoảng 90 phút tổng hợp báo cáo từ nhiều nguồn của team Dev, trong đó bước tổng hợp chi phí và tiến độ chức năng là mất thời gian nhất.

**Actor:**  
PM chịu trách nhiệm gửi báo cáo tiến độ cho stakeholder, nhận yêu cầu của stakeholder từ BA, giao nhiệm vụ cho team Dev.

**Thời điểm / bối cảnh:**  
Thứ bảy hàng tuần, trước buổi họp team.

**Current workflow:**

```text
1. Export Google Sheets tổng hợp chi phí.
2. Trích xuất báo cáo tiến độ dự án từ team Dev trên MS Team.
3. Kiểm tra thông báo yêu cầu từ BA trong Zalo.
4. Tự kiểm tra báo cáo tiến độ và chi phí, tóm tắt các ý chính. So sánh với yêu cầu đã đưa ra. 
5. Viết: insight, pros/cons, next action.
6. Self-review, format.
```

**Bottleneck:**  
Bước 4 - Tóm tắt ý chính trong 2 báo cáo tiến độ và chi phí thường mất đến 30 phút, so sánh với yêu cầu đưa ra mất 15 phút nữa.

**Impact:**  
90 phút/Tuần cho PM. Tổng hợp trễ khiến việc brainstorming đưa ra giải pháp gặp hạn chế về thời gian.

**Success metric:**  
Giảm tổng thời gian từ 90 phút xuống dưới 60 phút mà không thiếu sót ý chính nào.

**Non-AI alternative:**  
Template Report + Google Sheets + Zalo + MS Teams cung cấp đủ dữ liệu, nhưng chưa tóm tắt và không trực quan.

**AI hypothesis:**  
AI hỗ trợ tóm tắt ý chính, tổng hợp chi phí.

**Quick gut:**  
Workflow.

### Draft current workflow

```text
CURRENT STATE — 120 phút

[1 Google Sheets chi phí: 10']
→ [2 Lấy báo cáo tiến độ: 5']
→ [3 Lấy thông tin từ BA: 5']
→ [4 Kiểm tra, tóm tắt ý chính, so sánh 45']  <-- bottleneck
→ [5 Viết: 15']
→ [6 Review + format: 10']
```

### Draft future workflow

```text
FUTURE STATE — 21 phút

[1 Auto-pull tổng hợp chi phí: 5']
→ [2 AI lấy báo cáo tiến độ, tóm tắt ý chính: 15']
→ [3 AI tổng hợp thông tin BA: 3']
→ [4 PM review, so sánh và viết tài liệu: 30']  <-- human boundary
→ [5 AI review, format: 2']

Fallback: AI tổng hợp thiếu ý -> PM bổ sung tại bước 4 trước khi so sánh
```

## Problem Card #2 — Priority Order

**Problem 1 câu:**  
Khi họp team, PM và team Dev mất 60 phút để sắp xếp thứ tự ưu tiên chức năng.

**Actor:**  
PM và team Dev chịu trách nhiệm bàn luận về thứ tự ưu tiên hoàn thiện chức năng.

**Thời điểm / bối cảnh:**  
Chủ nhật hàng tuần, trong buổi họp team.

**Current workflow:**

```text
1. PM trình chiếu Google Sheets tổng hợp tiến độ dự án.
2. PM đưa ra các chức năng chưa hoàn thiện.
3. PM và team Dev bàn luận về độ quan trọng, chi phí, quản lý rủi ro và thời gian thực hiện các chức năng, từ đó thống nhất thư tự thực hiện.
4. PM note lại, gửi note cho team Dev.
```

**Bottleneck:**  
Bước 3 - Việc bàn luận về các yếu tố ưu tiên thực hiện chức năng thường mất nhiều thời gian nhất và sự tranh luận cũng gay gắt nhất, thường phải 45 phút.

**Success metric:**  
Giảm tổng thời gian từ 60 phút xuống 40 phút, dự toán đầy đủ các yếu tố liên quan và sắp xếp thứ tự nhanh chóng.

**Non-AI alternative:**  
Google Sheets chỉ tổng hợp tiến độ dự án, không đưa ra gợi ý nào.

**AI hypothesis:**  
AI phân tích danh sách các chức năng chưa hoàn thiện, đưa ra gợi ý về thứ tự ưu tiên để PM cùng team Dev chỉ tập trung vào các trường hợp đặc biệt.

**Quick gut:**  
Workflow.

### Draft current workflow

```text
CURRENT STATE — 60 phút

[1 PM trình chiếu: 5']
→ [2 PM chỉ chức năng chưa hoàn thiện: 5']
→ [3 PM và team Dev bàn bạc: 45']  <-- bottleneck
→ [4 PM note, gửi team Dev: 5']  
```

### Draft future workflow

```text
FUTURE STATE — 40 phút

[1 PM trình chiếu: 5']
→ [2 PM chỉ chức năng chưa hoàn thiện: 5']
→ [3 AI phân tích backlog và đưa ra gợi ý: 10']
→ [4 PM và team Dev bàn bạc có sự góp ý của AI: 15'] 
→ [5 PM note, gửi team Dev: 5']  

Fallback: AI gợi ý sai --> Mất thời gian tranh luận cho cái sai
```

## Problem Card #3 - Meeting Calendar

**Problem 1 câu:**  
Mỗi thứ 6 hàng tuần, PM cần check thông báo liên quan đến lịch làm việc và sắp xếp lịch cho team trong khoảng 15 phút.

**Actor:**  
PM chịu trách nhiệm quản lý thời gian.

**Thời điểm / bối cảnh:**  
Thứ 6 hàng tuần.

**Current workflow:**

```text
1. PM check MS Teams, tổng hợp các yêu cầu xin nghỉ/đến muộn nếu có.
2. PM trích lịch làm việc thường nhật trong Google Sheets.
3. PM tạo lịch làm việc cho từng thành viên.
4. PM gửi thông báo đến nhóm chung.
```

**Bottleneck:**  
Bước 3 - Việc tạo lịch làm việc thường mất đến 10 phút. Thực hiện trễ có thể ảnh hưởng tiến độ thực hiện công việc khác.

**Success metric:**  
Giảm tổng thời gian từ 15 phút xuống 7 phút, đảm bảo lịch đáp ứng yêu cầu từ team.

**Non-AI alternative:**  
Google Sheets đưa ra lịch làm việc thường nhật, MS Teams lưu lại tin nhắn. 

**AI hypothesis:**  
AI tạo lịch làm việc dựa trên lịch thường nhật và các yêu cầu xin nghỉ/đến muộn.

**Quick gut:**  
Workflow.

### Draft current workflow

```text
CURRENT STATE — 15 phút

[1 PM kiểm tra MS Teams: 3']
→ [2 PM lấy lịch làm việc chuẩn từ Google Sheets: 2']
→ [3 PM điều chỉnh lịch theo yêu cầu nghỉ/đến muộn: 10']  <-- bottleneck
→ [4 PM gửi thông báo cho team: 1'] 
```

### Draft future workflow

```text
FUTURE STATE — 7 phút

[1 PM kiểm tra yêu cầu nghỉ/đến muộn: 1']
→ [2 AI đọc lịch chuẩn và các yêu cầu thay đổi: 1']
→ [3 AI tạo lịch làm việc đề xuất: 1']
→ [4 PM rà soát và phê duyệt: 3']
→ [5 AI hoặc PM gửi lịch cho team: 1']

Fallback:
- AI hiểu sai yêu cầu nghỉ phép.
- AI tạo lịch có xung đột nhân sự.
- PM cần chỉnh sửa thủ công trước khi gửi.
```