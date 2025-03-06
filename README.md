<h1 align="center"> EBOOK 
<p>Library Service</p>
</h1>

 <h1>About</h1>

 <br>
 
 
 <p>EBOOK là một dự án ứng dụng web thư viện trực tuyến được xây dựng bằng (<a href="https://getbootstrap.com/" target="_blank">Bootstrap 4.6</a>, <a href="https://laravel.com" target="_blank">Laravel 9</a>).. Mục tiêu chính của ứng dụng này là cung cấp dịch vụ thư viện trực tuyến cho phép người dùng mượn và đọc sách trực tuyến. Người dùng có thể mượn sách/trả sách. Người dùng cũng có thể tìm kiếm tác giả cụ thể để tìm kiếm sách. Ứng dụng web có chức năng người dùng Quản trị viên cho phép quản trị viên thêm/chỉnh sửa hoặc xóa sách/tác giả trong Cơ sở dữ liệu. Quản trị viên cũng có thể biến người dùng bình thường thành quản trị viên.
 Ebook hoạt động theo hệ thống tín dụng người dùng. Một người dùng có thể mua tín dụng bằng tiền (không tích hợp hệ thống thanh toán) và sử dụng tín dụng để mượn và đọc sách. Một cuốn sách có thể được mượn trong một tuần, người dùng cũng có thể gia hạn thời gian mượn sách thêm 7 ngày và sẽ mất tín dụng. Nếu người dùng không trả lại hoặc gia hạn sách trong thời gian quy định, phí trễ hạn sẽ được tính là 1/3 giá tín dụng của sách. Các tính năng nâng cao của ứng dụng bao gồm:
</p>

<br>

<h1>Features</h1>
<h2>User features</h2>

-   <p style="font-size:1.5rem">User/Admin functionality.</p>
      <p>Chức năng người dùng/Quản trị viên - Để có các chức năng người dùng và quản trị viên riêng biệt, tôi đã tạo các bảng điều khiển riêng cho người dùng và quản trị viên.<p>
      <p>Công nghệ: Tôi đã tạo một middleware tùy chỉnh để kiểm tra vai trò của người dùng và bảo vệ các tuyến đường quản trị như các thao tác CRUD trên Sách và Tác giả.<p>
-   <p style="font-size:1.5rem">Mượn và trả sách của người dùng</p>
      <p>- Một người dùng cụ thể có thể mượn một cuốn sách để đọc trong một tuần và sau đó người dùng cần trả lại sách để tránh phí trễ hạn.<p>
      <p>Công nghệ: Một bảng pivot nhiều-nhiều giữa sách và người dùng, cho phép nhiều người dùng mượn cùng một cuốn sách và tôi đã sử dụng phương thức attach() và detach() trên mối quan hệ belongsToMany.<p>
-   <p style="font-size:1.5rem">Gia hạn thời gian mượn sách</p>
      <p>- Một người dùng cụ thể có thể gia hạn thời gian mượn sách thêm một tuần. Người dùng sẽ bị tính phí 1/4 giá tín dụng của sách. Nếu sách quá hạn, người dùng không thể đọc cho đến khi trả lại và mượn lại hoặc gia hạn thời gian mượn. Người dùng sẽ bị tính phí trễ hạn khi trả lại/gia hạn sau ngày hết hạn. Phí trễ hạn là 1/3 giá tín dụng của sách.<p>
-   <p style="font-size:1.5rem">Tìm kiếm sách qua tác giả</p>
      <p>Một cuốn sách cụ thể được viết bởi một tác giả. Người dùng có thể tìm kiếm tác giả và kiểm tra tất cả các cuốn sách mà tác giả đó đã viết.<p>
      <p>Công nghệ: Một mối quan hệ một-nhiều giữa mô hình Sách và mô hình Tác giả, cho phép lấy tất cả các cuốn sách liên quan đến một tác giả cụ thể.<p>
-   <p style="font-size:1.5rem">Chức năng gửi email nhắc nhở tự động</p>
     <p>Một cuốn sách khi được mượn bởi người dùng có ngày trả lại, tính năng này gửi email nhắc nhở tự động cho người dùng vào ngày hết hạn thời gian mượn.<p>
     <p>Công nghệ: Tạo một lệnh tùy chỉnh ExpriyReminder để kiểm tra ngày trả lại của tất cả các cuốn sách đã mượn. Sử dụng "schedular" để định nghĩa lịch trình cho lệnh và tạo một lớp Mail để gửi email nhắc nhở.<p>
-   <p style="font-size:1.5rem">Google Login/Registration</p>
     <p>Một cách đăng ký hoặc đăng nhập ứng dụng đơn giản và tiện lợi.<p>
     <p>Công nghệ: Laravel Socialite và Google Apps API.<p>


<h2>Tính năng Quản trị viên:</h2>

-   <p style="font-size:1.5rem">Thay đổi vai trò người dùng</p>
      <p>Biến người dùng bình thường thành quản trị viên..<p>
      <p>Công nghệ: Một chức năng makeAdmin() trên UserController để kiểm tra vai trò của người dùng và cập nhật vai trò đó thông qua yêu cầu post.<p>
-   <p style="font-size:1.5rem">CRUD tác giả và thêm sách vào mô hình Tác giả - Quản trị viên có thể tạo tác giả và thêm sách mới vào đó.</p>
    <p>Purpose: Quản trị viên có thể tạo tác giả và thêm sách mới vào đó.<p>
    <p>Công nghệ: Tạo chức năng CRUD cho tác giả và cũng bao gồm một phương thức để thêm sách vào tác giả.t<p>
-   <p style="font-size:1.5rem">Thay đổi trạng thái của sách</p>
       <p>Quản trị viên không thể xóa sách cho đến khi sách được người dùng mượn. Để xóa một cuốn sách, quản trị viên có thể thay đổi trạng thái của sách thành không có sẵn và sau khi chờ đợi thời gian quy định, có thể xóa sách.<p>
       <p>Technologies: An update method using a post request<p>
-   <p style="font-size:1.5rem">Uploading Book content pdf </p>
       <p>Công nghệ: Một phương thức update sử dụng yêu cầu post.<p>

<h1>Installation</h1>
* <p>Sao chép kho lưu trữ Github:</p>
  <p>Trong thư mục gốc của môi trường phát triển web cục bộ của bạn, mở một cửa sổ terminal mới và sao chép kho lưu trữ Github bằng lệnh và thay đổi thư mục trong thư mục dự án mới tạo.</p>
  <p style="background-color:white; color:black;padding:5px; "> git clone </p>
  <br>

-   <p>Cài đặt các phụ thuộc Composer:</p>
    <p>Enter the Command</p>
    <br>
    <p style="background-color:white; color:black;padding:5px;"> composer install </p>

<br>

-   <p>Cài đặt các phụ thuộc NPM:</p>
    <p>Enter the Commands: </p>
    <br>
    <p style="background-color:white; color:black;padding:5px; "> npm install <br> npm run dev </p>

<br>

-   <p>Sao chép tệp .env:</p>
    <p>Tạo khóa mã hóa ứng dụng: </p>
    <br>
    <p style="background-color:white; color:black; padding:5px;"> cp .env.example .env  </p>

<br>

-   <p>Tạo khóa mã hóa ứng dụng:</p>
    <p>Enter the Command: </p>
    <br>
    <p style="background-color:white; color:black; padding:5px;"> php artisan key:generate  </p>

<br>

-   <p>Tạo cơ sở dữ liệu trống cho ứng dụng:</p>
    <p> Sử dụng công cụ quản lý cơ sở dữ liệu yêu thích của bạn để tạo cơ sở dữ liệu trống và cấu hình tên người dùng và mật khẩu. </p>
    <br>

*   <p>Configure the .env file</p>
    <p style="background-color:white; color:black; padding:5px;"> DB_CONNECTION=mysql<br>
    DB_HOST=127.0.0.1 <br>
    DB_PORT=3306<br>
    DB_DATABASE=laravel<br>
    DB_USERNAME=root<br>
    DB_PASSWORD=******** </p>
    <p>Điều chỉnh DB_HOST, DB_PORT, DB_DATABASE, DB_USERNAME và DB_PASSWORD theo cơ sở dữ liệu của bạn.</p>

<br>

-   <p>Di chuyển cơ sở dữ liệu:</p>
    <p style="background-color:white; color:black; padding:5px;"> php artisan migrate  </p>
    <br>

*   <p>Gieo dữ liệu vào cơ sở dữ liệu:</p>
    <p style="background-color:white; color:black; padding:5px;"> php artisan db:seed </p>
    <br>

*   <p>Chạy các tác vụ theo lịch trình:</p>
    <p style="background-color:white; color:black; padding:5px;"> php artisan schedule:work </p>
    <br>

*   <p>Mở ứng dụng:</h2>
    <p>Open the browser and go to your url</p>
    <br>

<br>

<h1>Usage(User)</h2>

<p style="font-size:1.2rem" >Cách sử dụng (Người dùng): Tôi đã triển khai một hệ thống tín dụng trong ứng dụng của mình. Người dùng có thể mượn sách trong một tuần bằng cách sử dụng các tín dụng đã mua. Mỗi cuốn sách có một giá/tín dụng để mượn. Khi sách hết hạn và người dùng muốn tiếp tục đọc, người dùng có thể gia hạn thêm một tuần với một lượng tín dụng nhỏ. Tuy nhiên, nếu sách quá hạn và đã qua ngày trả lại, người dùng không thể đọc cho đến khi gia hạn, điều này yêu cầu phải trả thêm phí cùng với giá gia hạn thông thường.</p>

<h2>Seperated Login routes<h2>
<p style="font-size:1.5rem">Logging in User<p>

-   Login page
    ![My Image](/public/images/user-login.png)

*   User Accounts page and User Books page

    ![My Image 2](/public/images/user-dashboard.png)
    ![My Image 2](/public/images/user-books.png)

*   Borrowing books

    ![My Image 2](/public/images/book-borrow-2.png)
    ![My Image 2](/public/images/book-borrow-3.png)

*   Returning Books

    ![My Image 2](/public/images/return-book-1.png)
    ![My Image 2](/public/images/return-book-2.png)

*   Extending Books

    ![My Image 2](/public/images/extend1.png)
    ![My Image 2](/public/images/extend2.png)
    ![My Image 2](/public/images/extend3.png)

*   Extending Overdue books

    ![My Image 2](/public/images/extend-1.png)
    ![My Image 2](/public/images/extend2.png)
    ![My Image 2](/public/images/extend-3.png)

*   Reading a book

    ![My Image 2](/public/images/read1.png)
    ![My Image 2](/public/images/read2.png)

*   Searching via Authors

    ![My Image 2](/public/images/author-1.png)
    ![My Image 2](/public/images/author-2.png)

*   Google Registration

    ![My Image 2](/public/images/google-register-1.png)
    ![My Image 2](/public/images/google-registration-2.png)
    ![My Image 2](/public/images/google-registration-4.png)

*   Buying credits

    ![My Image 2](/public/images/credits.png)
    ![My Image 2](/public/images/credits2.png)

<h2>Usage(Admin)<h2>

-   Seperate account page.
    ![My Image](/public/images/admin-accountpng.png)

*   <h3>Admin actions<h3>

-   Creating a new author.
    ![My Image](/public/images/author-create-1.png)
    ![My Image](/public/images/author-create-2.png)

-   Adding new books to an existing author.
    ![My Image](/public/images/author-add-1.png)
    ![My Image](/public/images/author-add-2.png)

-   Adding new books without an author.
    ![My Image](/public/images/without-author-1.png)

-   Make an a user account admin.
    ![My Image](/public/images/make-admin-1.png)
    ![My Image](/public/images/make-admin-2.png)

-   Change the status of the a Book to make it unable to borrow.
    ![My Image](/public/images/change-status-1.png)
    ![My Image](/public/images/change-status-2.png)
-   Borrow button disbaled for a user.
    ![My Image](/public/images/status-3.png)

<h1>Reflective Analysis</h2>
<h2>Automated Reminder Email Feature</h2>

<h3>Description</h3>
<p>Tính năng gửi email tự động là một trong những tính năng quan trọng nhất của ứng dụng này. Người dùng có thể mượn sách mà họ thích trong một khoảng thời gian nhất định, sau đó phải trả lại sách hoặc gia hạn thời gian mượn để tránh phí phụ trội bằng cách mượn lại. Ứng dụng kiểm tra các sách mà mỗi người dùng đã mượn và kiểm tra ngày trả sách bằng phương thức getExpiryDate() của mô hình người dùng và gửi email nhắc nhở tự động cho người dùng vào ngày hết hạn. </p>

<h3>Why this feature?</h3>
<p>Động lực chính cho việc phát triển tính năng này là hiển nhiên, để giảm bớt nỗ lực của con người. Trong một miền người dùng lớn, việc gửi email nhắc nhở cho từng người dùng là không khả thi đối với một quản trị viên, hơn nữa, nó giúp người dùng gia hạn thời gian mượn sách để họ không phải mượn lại sách, vì điều đó yêu cầu thêm phí. Nếu một người dùng đã mượn nhiều sách, tính năng này trở nên hữu ích.
</p>

</p>

<h3>Development & Technologies used</h3>

-   Tạo lệnh artisan tùy chỉnh: Sử dụng php Artisan make, tôi đã tạo lệnh tùy chỉnh gọi là ExpiryReminder. Trong phương thức handle(), logic của lệnh sẽ được thực hiện. Lệnh này lặp qua danh sách các sách đã mượn của từng người dùng và so sánh ngày hiện tại với Ngày trả/ngày hết hạn của sách, nếu trùng khớp, lệnh sẽ gửi email cho người mượn sách/người dùng.
-   getExpiryDateFunction($id): Hàm này thuộc về mô hình người dùng, nhận tham số là book-id và lấy ngày mượn sách của người dùng, cộng thêm 10 ngày vào đó làm thời gian mượn và trả về ngày này.
-   Thiết lập lịch trình: Chúng tôi cần thiết lập lệnh mà chúng tôi muốn lên lịch (trong trường hợp này là ExpiryReminder), trong tệp kernel.phpcủa thư mục console. Để lệnh này hoạt động hiệu quả, nó nên được lên lịch hàng ngày vào nửa đêm.
-   Gửi email: Tạo một lớp mailable ExpiryReminderMail.phpvà xem liên quan, cũng thiết lập cấu hình người gửi trong tệp .env, email chứa tên sách cùng với ngày trả cho sách và được kích hoạt bất cứ khi nào ngày hết hạn trùng khớp với ngày hiện tại.
<h3>Usage & Demonstration<h3>
<p>Tôi sẽ trình diễn tính năng này sử dụng mailtrap.io.Chúng tôi có một người dùng tên là Mohammad Khan và đây là những cuốn sách đã mượn. Tôi đã thay đổi lịch trình trong kernel để lên lịch mỗi phút để trình diễn lệnh. </p>

![My Image](/public/images/dm1.png)

<p>In command line run this command: 
 <p style="background-color:white; color:black;padding:5px;"> php artisan schedular:work </p>

 <p>Reminder Email on mailtrap</p>

![My Image](/public/images/dm2.png)

