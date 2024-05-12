Tạo folder ban đầu
Cài đặt các module cần thiết
Chạy project bằng lệnh node app.js
#######
Thiết lập database:
Ở đây ta sẽ xài mongodb
B1: truy cập trang chủ của mongodb, sau đó tạo database theo hướng dẫn trên trang.
B2: Mở file app.js, nhập dòng lệnh
const connectDB = async () => {
  try {
    await mongoose.connect(
      `mongodb+srv://pphnam:${process.env.DB_PASSWORD}@ads-management.rxoh5xt.mongodb.net/?retryWrites=true&w=majority`,
      {
        useNewUrlParser: true,
        useUnifiedTopology: true,
      }
    );
    console.log(`connected to db successfully`);
  } catch (error) {
    console.log(error);
    console.log(`cannot connect to db`);
  }
};

connectDB();
Ở đây, ta thay cụm pphnam:${process.env.DB_PASSWORD} bằng username và password mà ta đã tạo ở trên.
#####
Sử dụng jsonwebtokken để Chuyển giao giữa 2 bên client và server.
#####
Folder View dùng để chứa các file hiển thị cho người dùng
Folder public dùng để hỗ trợ cho các tệp của folder View
Folder routes: dùng để tạo các api cần thiết cho đồ án
Folder Models: dùng để tạo các Schema cần thiết
Folder Controller: dùng để xử lý thao tác, và xử lý thông tin khi client và server tương tác.