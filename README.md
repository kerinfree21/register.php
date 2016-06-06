<?php
  $con = mysqli_connect("mysql8.000webhost.com", "a5676971_chay21", "music7EEE", "a5676971_rateAPP");
  
  $name = $_POST("name");
  $username = $_POST("username");
  $email = $_POST("email");
  $age = $_POST("age");
  $password = $_POST("password");
  
  $statement = mysqli_prepare($con, "INSERT INTO user (name, username, email, age, password) VALUES (?, ?, ?, ?,?)");
  msqli_stmt_bind_param($statement, "sssis", $name, $username, $email, $age, $password);
  msqli_stmt_execute($statement);
  
  $response = array();
  $response["success"] = true;
    
  echo json_encode($response);
?>
   
