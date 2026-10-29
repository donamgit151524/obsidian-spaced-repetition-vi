# Spaced Repetition — bản tùy chỉnh tiếng Việt

Việt hóa và giữ nguyên các tùy chỉnh giao diện, trang cài đặt và nhập đáp án trong bản đang dùng.

Đây là bản tùy chỉnh cá nhân, không phải bản phát hành chính thức. Đóng gói ngày 2026-10-29.

## Nguồn và giấy phép

- Plugin gốc: https://github.com/st3v3nmw/obsidian-spaced-repetition
- Phiên bản nền: 1.15.4; tác giả: Stephen Mwangi.
- Giữ giấy phép gốc trong LICENSE. source/upstream.zip chứa mã nguồn gốc đúng bản; source/*.patch ghi lại thay đổi của bản cài hiện tại so với bản sao lưu. patch-tools/ chứa công cụ sửa/Việt hóa ban đầu, tham chiếu cấu trúc vault gốc; không chạy trực tiếp trong repository này.
- main.js và styles.css là bản đang dùng, đã đóng gói để cài; thay đổi phiên bản manifest thành 1.15.4-vi.1. Các tùy chỉnh bổ sung có thể không nằm hết trong công cụ Việt hóa; bản diff là tài liệu đầy đủ của các thay đổi bundle.

## Cài qua BRAT

1. Cài và bật BRAT.
2. Chọn Add a beta plugin, nhập URL repository này.
3. Chọn release 1.15.4-vi.1 nếu BRAT yêu cầu.

ID vẫn là obsidian-spaced-repetition để dùng được cấu hình hiện có. Trên vault đã cài plugin gốc, hãy sao lưu cấu hình trước khi chuyển sang bản này. Cập nhật từ danh mục Community plugins có thể ghi đè bản tùy chỉnh; dùng BRAT cho repository này. Không cài song song hai bản cùng ID.

## Phát hành

Tạo GitHub Release có tag khớp version trong manifest.json. Đính kèm main.js, manifest.json và styles.css (nếu có) trực tiếp vào release; không chỉ đính kèm ZIP. Khi cập nhật, tăng phiên bản và cập nhật versions.json.

Không chứa data.json, ghi chú, thông tin đăng nhập hoặc cấu hình cá nhân.

Mã nguồn và bản diff được đóng gói trong source-bundle.zip; giải nén để xem các thư mục source/ và patch-tools/.


## Công dụng

Spaced Repetition lên lịch ôn tập thẻ ghi nhớ và cả ghi chú dựa trên đánh giá của bạn. Thích hợp để học từ vựng, công thức, khái niệm hoặc câu hỏi môn học. Bản tùy chỉnh giữ phần Việt hóa cùng các thay đổi giao diện của bản đã đóng gói.

## Tạo bộ thẻ đầu tiên

1. Cài/bật plugin. Vào cài đặt Spaced Repetition và kiểm tra **thẻ đánh dấu bộ flashcard**. Ví dụ mặc định thường dùng `#flashcards`; hãy dùng đúng nhãn trong cấu hình của bạn.
2. Tạo ghi chú `Ôn STM32.md`:

```markdown
#flashcards/stm32

HSE là gì?::Bộ dao động tốc độ cao dùng nguồn bên ngoài.

HSI là gì?::Bộ dao động RC tốc độ cao bên trong vi điều khiển.

GPIO viết tắt của gì?::General-Purpose Input/Output.
```

3. Nếu cấu hình yêu cầu nhãn khác, đổi dòng đầu tương ứng. Dấu phân cách câu hỏi/đáp án một dòng mặc định là `::`; nếu đã đổi trong cài đặt, dùng dấu phân cách hiện tại.
4. Bấm biểu tượng ôn flashcard trên thanh công cụ hoặc mở khay lệnh (`Ctrl+P`), tìm lệnh của **Spaced Repetition** để ôn thẻ.
5. Chọn bộ `stm32`, tự trả lời trước rồi hiện đáp án.
6. Chọn mức đánh giá đúng với khả năng nhớ của bạn. Plugin tính lần ôn tiếp theo; ôn lại các thẻ đến hạn vào những ngày sau.

## Thẻ nhiều dòng

Với dấu phân cách mặc định, có thể viết:

```markdown
Nêu ba bước cấu hình GPIO.
?
1. Bật clock cho cổng GPIO.
2. Cấu hình chế độ chân.
3. Đọc hoặc ghi trạng thái chân.
```

Giữ dòng trống giữa các thẻ. Dấu phân cách tùy thuộc cấu hình; kiểm tra mục cú pháp flashcard nếu plugin không nhận thẻ.

## Ôn cả ghi chú

1. Kiểm tra nhãn dùng cho **ôn ghi chú**, ví dụ `#review` trong cấu hình của bạn.
2. Thêm nhãn đó vào ghi chú cần ôn, chẳng hạn một bài tổng hợp về Clock Tree.
3. Mở khung ôn ghi chú của plugin, chọn ghi chú đến hạn, đọc và tự kiểm tra kiến thức rồi đánh giá để lên lịch lần sau.

Ôn ghi chú và ôn từng flashcard có luồng riêng. Không phải cứ thêm `#review` là toàn bộ nội dung sẽ tự biến thành các câu hỏi.

## Sử dụng hằng ngày

- Mỗi ngày ưu tiên thẻ đến hạn, sau đó mới thêm thẻ mới.
- Mỗi thẻ nên hỏi một ý ngắn, đáp án rõ và có thể tự kiểm tra.
- Plugin có thể ghi thông tin lịch ôn vào Markdown hoặc dữ liệu plugin tùy chế độ. Sao lưu ghi chú cùng cấu hình nếu muốn giữ lịch học khi chuyển máy.
- Repository chỉ phân phối mã plugin, không chứa bộ thẻ hoặc tiến độ học cá nhân của bạn.

## Cài và cập nhật bản Việt hóa

Trong BRAT → **Add beta plugin**, nhập `donamgit151524/obsidian-spaced-repetition-vi`. ID giữ nguyên `obsidian-spaced-repetition`; không cài song song hai bản cùng ID. Dùng BRAT để nhận bản tùy chỉnh mới.

Tham khảo [tài liệu Spaced Repetition chính thức](https://www.stephenmwangi.com/obsidian-spaced-repetition/) để xem đầy đủ cú pháp và cách tính lịch ôn.

