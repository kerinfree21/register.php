<?php
  $con = mysqli_connect("mysql8.000webhost.com", "a5676971_chay21", "music7EEE", "a5676971_rateAPP");
  
  $name = $_POST("name");
  $age = $_POST("age");
  $username = $_POST("username");
  $password = $_POST("password");
  
  $statement = mysqli_prepare($con, "INSERT INTO user (name, age, username, password) VALUES (?, ?, ?, ?,)");
  msqli_stmt_bind_param($statement, "siss", $name, $age $username, $password);
  msqli_stmt_execute($statement);
  
  $response = array();
  $response["success"] = true;
    
  echo json_encode($response);
?>
   
