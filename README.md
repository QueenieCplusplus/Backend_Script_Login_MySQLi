# Backend_Script_Login_MySQLi

運作原理與傳送表單使用 http method 為 POST 的應用：

    // Processing form data when form is submitted
    if($_SERVER["REQUEST_METHOD"] == "POST"){
    
        //...

    }
    
在資料庫中增加使用者的密碼資訊，以及使用 prepared statement 包裝隱密資訊。

    // 新增 SID
    if($stmt = mysqli_prepare($link, $sql)){
    
      mysqli_stmt_bind_param($stmt, "si", $param_password, $param_id);
            
      // Set parameters
      $param_password = password_hash($new_password, PASSWORD_DEFAULT);
      $param_id = $_SESSION["id"];
      
     }

ref: https://www.tutorialrepublic.com/php-tutorial/php-mysql-login-system.php
