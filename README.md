# PHP_Data_Insert_in_Database

<body style="text-align: center; margin: 100px; ">

   <form action="login.php" method="post">

        <input type="text" name="username" placeholder="username">
        <input type="email" name="email" placeholder="email">
        <input type="password" name="password" placeholder="password">
        <input type="submit" name="submit">
   </form>

   <?php 

    if(isset($_POST['submit'])){

        $username = $_REQUEST['username'];
        $email   =  $_REQUEST['email'];
        $password = $_REQUEST['password'];

        $con = mysqli_connect('localhost','root','','users');

        $query = "INSERT INTO user_info (username,email,password) VALUES('$username','$email','$password')";
        $result = mysqli_query($con,$query);

        if($result){
            echo "Insert Success";
        }else{
            echo "Insert Not Success";
        }

    }

  ?>

    
</body>

