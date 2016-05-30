<?php
  $con = mysqli_collect ("my_host", "my_user", "my_password", "my_db");
  
  $name = $_POST("name");
  $age = $_POST("age");
  $username = $_POST("username");
  $password = $_POST("password");
  
  $statement = mysqli_prepare($con, "INSERT INTO user (name, age, username, password) VALUES (?, ?, ?, ?,)");
  msqli_stmt_bind_param($statement, "siss", $name, $age $username, $password);
  msqli_stmt_execute(statement);
  
  $response = array();
  $response["success"] = true;
    
  echo json_encode($response);
?>
   
