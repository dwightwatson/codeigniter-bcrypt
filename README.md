# codeigniter-bcrypt
## Bcrypt (PHPPass) for CodeIgniter

Adaption of PHPPass (0.3) for use as a CodeIgniter Bcrypt library.

Still in development, planning to add:

* Config file compatibility
* Documentation and examples

## Installation

* Place Bcrypt.php in your ``application/libraries`` folder.
* Change ``$iteration_count_log2`` in the object constructor if you wish for a different default value.
* Change ``$portable_hashes`` in the object constructure if you want your hashes to be portable. 

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