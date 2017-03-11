# codeigniter-bcrypt

## DEPRECATION WARNING

This library is not maintained, and it is suggested that you don't use it. It was simply a CodeIgniter wrapper around the PHPPass library. Please look into using [PHP's native password hasing functions instead](https://secure.php.net/manual/en/function.password-hash.php).


## Bcrypt (PHPPass) for CodeIgniter

Adaption of PHPPass (0.3) for use as a CodeIgniter Bcrypt library.

Allowed for the use of a separate config file, adjusted for some CodeIgniter configurability, added the scope of functions, changed hashing and checking functions to meet CodeIgniter standards for function names.

## Installation

* Place ``Bcrypt.php`` in your ``application/libraries`` folder.
* Place ``bcrypt.php`` in your ``application/config`` folder.
* Adjust options in the config file as neccessary.

## Usage
First, load the Bcrypt library or autoload it in ``config/autoload.php``.

    $this->load->library('bcrypt');

### Hashing
To hash a password, simply pass the string to ``hash_password()``.

    $password = 'hunter2';
    $hash = $this->bcrypt->hash_password($password);

The function will return the hashed password or ``*`` on error.

### Checking
To check a hash password, simply pass the string and stored password to ``check_password()``.

    $password = 'hunter2';
    
    if ($this->bcrypt->check_password($password, $stored_hash))
    {
    	// Password does match stored password.
    }
    else
    {
    	// Password does not match stored password.
    }
    
The function will return ``TRUE`` or ``FALSE`` dependant on success.
