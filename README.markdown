# Memsess - A memcached backend for CodeIgniter sessions

***

## Usage

### Installation

Simply copy **libraries/Session.php** to the libraries/ directory in your application folder.
Copy **config/appconfig.php** to the config/ directory in your application folder.

### Configuration

In **config/appconfig.php** there are three settings for you to configure.

* $config['memsess_name'] - *The name of the session*
* $config['memsess_expire_time'] - *The expiration time for the session (in seconds)*
* $config['memsess_servers'] - *Array of associative arrays containing keys 'host' and 'port'.  Each associative array corresponts to a single host/port combo.  Put in as many of these as you'd like.*

### Initialization

Library doesn't take any initialization parameters.  Simply load it in a controller using:

`$this->load->library("session");`

Alternativly, you could autoload it in config/autoload.php

### Usage

Has the same styntax as CodeIgniters session library so no changes to your code should be required.

There are also a few additional commands (and aliases for the CodeIgniter ones).

In addition to **set_userdata()**, **userdata()**, **unset_userdata()**, **flashdata()**, **keep_flashdata()**, and **sess_destroy()**
this library also provides the following:

`$this->session->set($key, $value); //alias for set_userdata()`

`$this->session->get($key); //alias for userdata()`

`$this->session->delete($key); //alias for unset_userdata()`

`$this->session->destroy(); //alias for sess_destroy()`

`
/*
alias for keep_flashdata but provides an optional second parameter (defaults to 1) that lets you specify the number of requests to retain the data
*/
$this->session->extend_flashdata($key, $num_requests=1);
`
