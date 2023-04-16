# Transformer-Decoder-Text-Generation là một bài tự sinh văn bản sử dụng cấu trúc decode của mô hình transformer với dữ liệu <a href='https://github.com/NTT123/viwik18/tree/viwik19'>wiki-vi19</a>
## Giới thiệu
- Đây là bài toán tự sinh văn bản khi cho 1 chuỗi văn bản đầu vào và nó sẽ sinh ra n các từ tiếp theo
- Về dữ liệu: mình lấy dữ liệu wiki-vi19 - là bộ dữ liệu được crawl về từ wikipedia, đây cũng là bộ data dành cho việc sinh từ trong tiếng Việt
- Về model: Đây là model làm theo hướng nghiên cứu để biết được cách tạo model, cách model hoạt dộng với đầu vào và đầu ra của các lớp là như thế nào
## Xử lý dữ liệu
- Khi tải file zip từ link trên về và giải nén ta sẽ có một thư mục dataset, trong thư mục dataset sẽ có những thư mục con chứa các đoạn văn bản
dataset:
  wiki1  
  wiki2  
- Từ các file dữ liệu text đó mình sẽ đọc hết tất cả (có thể xử lý sạch sẽ ở đây để khi đọc ra ta không cần xử lý nhiều nữa) và gom lại thành 1 file lớn duy nhất để khi train mình chỉ cần đọc 1 file
- Sau khi đọc và gom dữ liệu mình ghi nó vào file data.txt  
LƯU Ý: trong bài này dữ liệu mình gần như không làm sạch (như viết thường, bỏ ký tự đặc biệt,...)
## Chi tiết model
- Đây là decoder của model transformer gần như là tự định nghĩa các lớp
- Decoder sử dụng tốt cho việc sinh từ và chatbot giống như GPT
- Mình train với 200 epochs thì kết quả sinh từ cho ra khá khả quan, và chúng ta hoàn toàn có thể train lâu thêm cũng như nhiều dữ liệu hơn nhưng phạm vi bài này mình sẽ dừng lại ở mức nghiên cứu cách dùng ít dữ liệu và 200 epochs
