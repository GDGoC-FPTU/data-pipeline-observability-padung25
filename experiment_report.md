# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600251
**Name:** Phạm Anh Dũng
**Date:** 15/4/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9/10 | Kết quả hợp lý. Pipeline ETL đã lọc dữ liệu lỗi và chỉ giữ lại 3 bản ghi hợp lệ. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 1/10 | Kết quả sai lệch rõ ràng. Dữ liệu rác đã làm Agent ưu tiên một bản ghi bất thường, không thực tế và có giá trị ngoại lai rất lớn. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Với `garbage_data.csv`, dữ liệu đã bị “poisoned”, nghĩa là có các bản ghi bất thường chen vào tập dữ liệu. Bằng chứng rõ nhất trong terminal là Agent chọn **“Nuclear Reactor at $999999”**, cho thấy mô hình hoặc logic chọn lựa đã bị một **outlier** chi phối. 

Ngoài outlier, các vấn đề dữ liệu như **duplicate IDs**, **wrong data types**, hoặc **null values** cũng rất nguy hiểm nếu không được kiểm soát. Duplicate IDs có thể làm một thực thể bị đếm lặp; sai kiểu dữ liệu có thể làm hỏng bước so sánh hoặc sắp xếp; còn giá trị null có thể khiến logic suy luận thiếu ngữ cảnh.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Đồng ý

Prompt tốt chỉ giúp Agent diễn đạt hoặc suy luận trên dữ liệu đang có, nhưng không thể cứu được một đầu vào bị nhiễm bẩn nghiêm trọng. Trong thí nghiệm này, cùng một logic Agent nhưng chỉ cần đổi từ dữ liệu sạch sang dữ liệu rác thì kết quả chuyển từ hợp lý sang vô lý. Điều đó cho thấy chất lượng dữ liệu là nền tảng cốt lõi; nếu dữ liệu sai, kết quả AI rất dễ sai theo.