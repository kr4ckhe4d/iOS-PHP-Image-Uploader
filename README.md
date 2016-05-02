# iOS-PHP-Image-Uploader
##A demo file upload app to a PHP server

####Code for php file is given below.
```php
<?php
$uploaddir = 'uploads/';
$filepath = $_POST["param1-name"].'/';
if (!file_exists($filepath)) {
    mkdir($filepath, 0777, true);
}
$file = basename($_FILES['uploadedfile']['name']);
$uploadfile = $filepath . $file;
echo "file=".$file; //is empty, but shouldn't
// Read request parameters
//$title = $_POST['title'];
//$returnValue = array(“firstName”=>$firstName, “lastName”=>$lastName);
// Send back request in JSON format
 echo json_encode($_POST["param1-name"]);
if (move_uploaded_file($_FILES['uploadedfile']['tmp_name'], $uploadfile)) {
    echo $file;
    return $filepath;
}
else {
    echo "error";
}
?>
```
