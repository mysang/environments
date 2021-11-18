### Hướng dẫn Active theme Porto WordPress
- Sau khi cài đặt theme, mở file `inc\plugins\importer\importer-api.php`
- Tìm đoạn `public function is_localhost`
- Thêm domain vào whitelist, sửa return thành true

### Hướng dẫn Active theme Solidad Wordpress
- Sau khi cài đ theme, mở file `inc/dashboard/inc/require-activation.php`
- Tìm đoạn `function do_check_envato_code()`
- Tìm trong function đoạn `if (!empty($res) && $res->status === 'success') {`
- Lấy đoạn trả về trong `if` này thay vào đoạn trả về trong `else`
