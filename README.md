# EasyMonoeci-PHP
By Francois (aka Yoyae) Gineste
https://github.com/Yoyae/EasyMonoeci-PHP

Tips appreciated: MLw8i2VzsyhbnZ529LRLoynkwaG3YkHsn7

A simple class for making calls to Monoeci's RPC API using PHP.

## Getting Started:
1. Include easymonoeci.php into your PHP script:

	`require_once('easymonoeci.php');`
2. Initialize Monoeci connection/object:

	`$monoeci = new \elbereth\EasyMonoeci('username','password');`

	Optionally, you can specify a host, port. Default is HTTP on localhost port 24157.

	`$monoeci = new \elbereth\EasyMonoeci('username','password','localhost','24157');`

	If you wish to make an SSL connection you can set an optional CA certificate or leave blank
	`$monoeci->setSSL('/full/path/to/mycertificate.cert');`

3. Make calls to monoecid as methods for your object. Examples:

	`$monoeci->getinfo();`
	`$monoeci->getrawtransaction('c780a21541f163d22f53661f592399fb658d12dc55ef9a7d3e937c4c9705f01a',1);`
	`$monoeci->getblock('0000000000000124e15bb02d9fa8b5a0cd3e642b148f76aa0c386710d0112cf0');`
	`$monoeci->mnbudget('show');`

## Additional Info:
* When a call fails for any reason, it will return false and put the error message in $monoeci->error

* The HTTP status code can be found in $monoeci->status and will either be a valid HTTP status code or will be 0 if cURL was unable to connect.

* The full response (not usually needed) is stored in $monoeci->response while the raw JSON is stored in $monoeci->raw_response

## Contribution Info

This is forked from EasyDash-PHP by Alexandre (aka elbereth) Devilliers (https://github.com/elbereth/EasyDash-PHP ).
Original code is licenced under MIT.
