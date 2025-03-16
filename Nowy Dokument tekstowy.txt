<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $name = htmlspecialchars($_POST['name']);
    $email = htmlspecialchars($_POST['email']);
    $message = htmlspecialchars($_POST['message']);

    $to = "hydro.spaw.zoo@gmail.com"; // Twój e-mail
    $subject = "Nowe zapytanie z formularza";
    $body = "Imię i Nazwisko: $name\nE-mail: $email\nWiadomość:\n$message";

    $headers = "From: no-reply@yourdomain.com"; // Zmienna do ustalenia, z jakiego adresu wysyłamy e-mail
    $headers .= "\r\nContent-Type: text/plain; charset=UTF-8\r\n";

    if (mail($to, $subject, $body, $headers)) {
        echo "Wiadomość została wysłana!";
    } else {
        echo "Wystąpił błąd przy wysyłaniu wiadomości.";
    }
}
?>
