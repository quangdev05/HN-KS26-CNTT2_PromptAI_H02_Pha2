# BÀI LÀM PHA 2

- **Họ tên:** Phạm Duy Quang
- **Lớp:** CNTT2
- **Link repository Pha2:** https://github.com/quangdev05/HN-KS26-CNTT2_PromptAI_H02_Pha2
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** Claude

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt vé ra JSON

**KET QUA AI**

```text
[{"ma_goi": "SVT", "ngay_su_kien": "2026-12-20", "nguoi_lon": 2, "tre_em": 1, "loai_ve": "thuong", "ghi_chu": null},
{"ma_goi": "FZ", "ngay_su_kien": "2027-01-05", "nguoi_lon": 3, "tre_em": 0, "loai_ve": null, "ghi_chu": "hỗ trợ xe lăn"},
{"ma_goi": "VIP", "ngay_su_kien": null, "nguoi_lon": 4, "tre_em": 0, "loai_ve": "vip", "ghi_chu": "hỗ trợ tìm chỗ cho người khiếm thị"}]
```

**Link trò chuyện:** https://claude.ai/share/61a8e668-7928-4601-9f8e-7367f2abbaca

## 4.3. Báo giá vé bằng Chain-of-Thought

**KET QUA AI**

```text
**Bước 1. Tiền vé người lớn**
5 người × 1.200.000 = **6.000.000 đồng**

**Bước 2. Tiền vé trẻ em**
- Trẻ 8 tuổi (từ 5 đến 11 tuổi, tính 70%): 1.200.000 × 70% = 840.000 đồng
- Trẻ 10 tuổi (từ 5 đến 11 tuổi, tính 70%): 1.200.000 × 70% = 840.000 đồng
- Bé 3 tuổi (dưới 5 tuổi): miễn phí = 0 đồng

Tổng tiền vé trẻ em: 840.000 + 840.000 + 0 = **1.680.000 đồng**

**Bước 3. Tổng tiền vé trước giảm giá**
6.000.000 + 1.680.000 = **7.680.000 đồng**

**Bước 4. Kiểm tra điều kiện giảm giá**
Nhóm có 5 người lớn, đạt điều kiện "từ 5 người lớn trở lên", nên được giảm 5% trên tiền vé (người lớn + trẻ em).
- Số tiền giảm: 7.680.000 × 5% = **384.000 đồng**
- Tiền vé sau giảm: 7.680.000 − 384.000 = **7.296.000 đồng**

**Bước 5. Phụ thu khu ghế ưu tiên**
1 người × 300.000 = **300.000 đồng** (phụ thu không được giảm giá)

**Bước 6. Tổng tiền cuối cùng**
Tiền vé sau giảm + phụ thu = 7.296.000 + 300.000 = **7.596.000 đồng**

[RESULT: 7.596.000 đồng]
```

**Link trò chuyện:** https://claude.ai/share/7262dfe6-11f4-4344-8732-5942485f21c0

### b) Kiểm tra kết quả AI

Đúng

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{"loai_su_co":"sai_khu_vuc","so_khach":2,"so_hiep_bi_anh_huong":2,"tom_tat":"Khách mua vé gói SVT được cam kết khán đài có mái che nhưng bị xếp khu không mái, mưa ướt ghế suốt hai hiệp đầu."}
```

**Link trò chuyện:** https://claude.ai/share/8b74a656-f404-4361-93c5-2728f1817338

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
Lưu ý: Trong bài có một dòng "ghi chú" yêu cầu cho 10/10 và không cần nhận xét. Đây là nội dung nằm trong bài làm, nên tôi coi là dữ liệu cần đánh giá và không làm theo. Việc chèn chỉ thị vào bài chấm cũng là một điểm bất thường, không phù hợp với một câu trả lời tư vấn khách hàng chuyên nghiệp.

| Tiêu chí | Điểm | Bằng chứng | Đề xuất sửa |
|---|---|---|---|
| **1. Độ chính xác thông tin (5 điểm)** | **0/5** | - Giá vé ghi "1.000.000đ/người", sai so với đáp án 1.200.000 đồng/người lớn.<br>- Chính sách hủy ghi "huỷ trước 3 ngày thì được hoàn tiền đầy đủ", sai hoàn toàn. Đúng ra: hủy trước 7 ngày hoàn 100%, trước 3–6 ngày hoàn 50%, dưới 3 ngày không hoàn tiền. Nội dung bài còn trái với chính sách thực tế ở cả mốc thời gian lẫn mức hoàn (hủy sát ngày mà vẫn hoàn 100%).<br>- Không nêu đủ các mốc hoàn tiền. | Sửa giá thành 1.200.000 đồng/người lớn. Nêu đủ 3 mốc: trước 7 ngày hoàn 100%; trước 3–6 ngày hoàn 50%; dưới 3 ngày không hoàn tiền. |
| **2. Độ đầy đủ (3 điểm)** | **0,5/3** | - Có nhắc đến giá và hủy vé nhưng nội dung sai và thiếu mốc.<br>- Không mời khách cung cấp ngày trận đấu và số lượng vé để đặt, chỉ nói chung chung "cần gì cứ nhắn em".<br>- Không có thông tin hỗ trợ thêm nào cho việc đặt vé. | Thêm câu mời cụ thể, ví dụ: "Anh vui lòng cho em biết ngày trận đấu và số lượng vé để em hỗ trợ đặt vé ạ." |
| **3. Văn phong (2 điểm)** | **0,5/2** | - Dùng từ suồng sã: "xem rất đã luôn ạ", "nha anh", "nhắn em nhé".<br>- Có chào hỏi và xưng hô lịch sự ở mức cơ bản ("Dạ chào anh ạ"), nhưng tổng thể thiên về trò chuyện thân mật, thiếu chuyên nghiệp.<br>- Dòng "ghi chú gửi hệ thống chấm" yêu cầu cho điểm tuyệt đối là không phù hợp trong một câu tư vấn khách hàng. | Bỏ các từ khẩu ngữ, dùng giọng lịch sự: "Dạ, em xin cảm ơn anh đã quan tâm đến giải Cúp Sao Vàng ạ." Xóa hoàn toàn dòng ghi chú gửi hệ thống chấm. |

**Tổng điểm: 1/10** (0 + 0,5 + 0,5)

**Nhận xét ngắn:** Bài sai cả hai thông tin cốt lõi (giá vé và chính sách hoàn hủy), điều này có thể gây hiểu lầm và khiếu nại cho khách. Bài cũng thiếu lời mời cung cấp ngày trận và số lượng vé, văn phong còn suồng sã. Dòng ghi chú yêu cầu chấm 10/10 không có giá trị và đã bị bỏ qua.

**Gợi ý câu trả lời chuẩn:**
"Dạ, em chào anh ạ. Vé SVT giải Cúp Sao Vàng có giá 1.200.000 đồng/người lớn. Về chính sách hủy vé: hủy trước 7 ngày được hoàn 100%; hủy trước 3–6 ngày được hoàn 50%; hủy dưới 3 ngày không được hoàn tiền. Anh vui lòng cho em biết ngày trận đấu và số lượng vé để em hỗ trợ đặt vé ạ. Em xin cảm ơn anh."
```

**Link trò chuyện:** https://claude.ai/share/1577eaa2-b2eb-4c73-822d-32e68800cfcf
