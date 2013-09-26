secure-storage-js [![Build Status](https://travis-ci.org/bealearts/secure-storage-js.png?branch=master)](https://travis-ci.org/bealearts/secure-storage-js)
=================
Pure JS implementation of SecureStorage API as inspired by http://www.nczonline.net/blog/2010/04/13/towards-more-secure-client-side-data-storage/

> Allows the secure storage of client side data within the browser 

Example Usage
-------------

```js
/**
 *	Full format, using a Base64 encoded binary key
 */
openSecureStorage('myStore', AES_256, secureKey, function(store) {
	
	var counter = store.getItem('counter');

	if (counter)
		counter++;
	else
		counter = 1;

	store.setItem('counter', counter);
});

/**
 *	Simplified foramt, using a plain text password and AES_256 cypher
 */
openSecureStorage('myStore', 'MyP4ssw0rd', function(store) {
	
	var counter = store.getItem('counter');

	if (counter)
		counter++;
	else
		counter = 1;

	store.setItem('counter', counter);
});

/**
 * Removeing the store
 */
removeSecureStorage('myStore');
```

Installation
------------

```shell
bower install secure-storage-js --save
```    

