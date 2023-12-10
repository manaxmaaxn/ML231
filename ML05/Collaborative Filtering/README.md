Hệ thống lọc cộng tác (CF) và đề xuất dựa trên máy tính thường liên quan đến nguồn gốc của hệ thống có tên Tapestry.

Một trong những thuộc tính chính của hệ thống này là nó cho phép tạo ra các đề xuất dựa trên sự kết hợp các ý tưởng đầu vào từ nhiều người dùng khác. Thay vì lọc các mục dựa trên nội dung, việc đưa ra đề xuất dựa trên ý kiến của những người dùng có cùng quan điểm đã trở nên phổ biến được gọi là lọc cộng tác. 

Về cơ bản thì hệ thống này nó có hai loại: 
  
  + Lọc dựa trên người dùng (User – User): Các hệ thống này giới thiệu sản phẩm cho người dùng mà những người dùng tương tự đã thích. Để đo lường sự giống nhau giữa hai người dùng, chúng ta có thể sử dụng tương quan Pearson hoặc độ tương tự cosine. Kỹ thuật lọc này có thể được minh họa bằng một ví dụ.
    
    ![image](https://github.com/manaxmaaxn/ML231/assets/127325509/a7ec42b0-ca42-49a8-8b85-a7abeebe0102)

    Vì người dùng A và F không chia sẻ bất kỳ xếp hạng phim nào chung với người dùng E nên điểm tương đồng của họ với người dùng E không được xác định trong Pearson Correlation. Do đó, chúng ta chỉ cần xét người dùng B, C và D. Dựa trên Tương quan Cosine Similatiry, chúng ta có thể tính toán độ tương tự sau.

    ![image](https://github.com/manaxmaaxn/ML231/assets/127325509/414e5912-b1f2-4c52-b473-ddb0cfa29ee1)

  Trong đó: 

  A: ma trận vecto A tương đương profile của người dùng, nói chung là đầu vào dùng để xác định xem là người xem đang thích phim như thế nào
  
  B: ma trận vecto B của các feature i, ma trận này sẽ được dùng để so sánh với các vecto x để tìm ra sự tương đồng giữa người dùng và phim sẽ được đề xuất

  θ: là khoảng cách giữa 2 vecto A và B, θ càng nhỏ cho thấy rằng độ tương đồng giữa phim đề xuất dựa trên mong muốn của người dùng càng lớn

  + Lọc cộng tác dựa trên mặt hàng (items- items) - Thay vì đo lường mức độ tương tự giữa những người dùng, CF dựa trên mặt hàng sẽ đề xuất các mặt hàng dựa trên mức độ tương đồng của chúng với các mặt hàng mà người dùng mục tiêu đã xếp hạng. Tương tự, độ tương tự có thể được tính toán bằng Pearson Correlation hoặc Cosine.

    ![image](https://github.com/manaxmaaxn/ML231/assets/127325509/eda0e319-5a2f-43a8-a6d2-6771c8dd70c7)

  Việc sử dụng lọc cộng tác dựa trên item basedtránh thành công vấn đề do sở thích động của người dùng gây ra vì CF dựa trên vật phẩm tĩnh hơn. Tuy nhiên, một số vấn đề vẫn tồn tại đối với phương pháp này. Đầu tiên, vấn đề chính là khả năng mở rộng. Việc tính toán tăng lên theo cả khách hàng và sản phẩm. Trường hợp xấu nhất độ phức tạp là O(mn) với m người dùng và n mục. Ngoài ra, độ thưa thớt là một mối quan tâm khác.
  
  Ưu điểm lớn nhất của kỹ thuật cộng tác là chúng hoàn toàn độc lập với bất kỳ cách trình bày nào mà máy có thể đọc được về những thứ được đề xuất và hoạt động tốt đối với những thứ phức tạp như âm nhạc và phim ảnh, nơi các biến thể về khẩu vị có thể tin cậy được đối với phần lớn sự thay đổi về sở thích
