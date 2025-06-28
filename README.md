<?php
$update = json_decode(file_get_contents('php://input'), TRUE);
$chatId = $update["message"]["chat"]["id"];
$message = $update["message"]["text"];

file_put_contents("log.txt", print_r($update, true)); // log untuk debug

$response = "Halo, kamu berkata: $message";

file_get_contents("https://api.telegram.org/7658902176:AAGkinaM8uxnse7ye_QdYaOFtWEF7SlLAjY/sendMessage?chat_id=$chatId&text=" . urlencode($response));
?>
