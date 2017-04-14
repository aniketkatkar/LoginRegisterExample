# LoginRegisterExample
Register and Login example for Android using fragments and PHP(database) with change password.

Android register and login code using php in database.

## Backend

Edit the following lines in the DBOperations.php with your credentials
```
    private $host = '<hostname>';
    private $user = '<database user name>';
    private $db = '<database name>';
    private $pass = '<database password>';
```
Also to use the sendPHPMail function, edit the following lines in Functions.php
```
public function sendPHPMail($email,$temp_password){
 
        $subject = 'Password Reset Request';
        $message = 'Hi, Your password reset code is '.$temp_password.' . This code expires in 5 minutes. Enter this code within 5 minutes to reset your password. ';
        $from = "<email through which you want the mail to be sent>";
        $headers = "From: <email through which you want people to receive email from>" . $from;
 
        return mail($email,$subject,$message,$headers);
 
    }
```

##Android App

In RequestInterface.java, insert your hostname and index.php file
```java
public interface RequestInterface {
 
    @POST("<hostname>/index.php")
    Call<ServerResponse> operation(@Body ServerRequest request);
 
}
```

Also in Constants.java, edit the following
```java
public static final String BASE_URL = "<your hostname>";
```
