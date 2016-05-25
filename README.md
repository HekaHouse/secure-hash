# secure-hash

`<secure-hash>` A Polymer element for generating cryptographic hashes.

[API Docs and Demo](https://heka-house-polymer-demos.firebaseapp.com/secure-hash)

[Source](http://github.com/hekahouse/secure-hash/)

## Adapted from

[jsSHA](https://github.com/Caligatio/jsSHA)

## Install

    bower install --save HekaHouse/secure-hash

## Example

    <secure-hash
      id="keyed"
      sha-variant="SHA-512"
      input-format="TEXT"
      incoming-msg="<MESSAGE-TO-HASH>"
      outgoing-hash='{{digest}}'></secure-hash>

In the example {{digest}} is a bound variable to recieve the generated hash,
<MESSAGE-TO-HASH> is the text used to generate the hash.

## HMAC Example
      <secure-hash sha-variant="SHA-512" input-format="TEXT"></secure-hash>
      <secure-hmac enc="TEXT"></secure-hmac>
      <script>
        var hmac = document.querySelector('secure-hmac');
        hash = document.querySelector('secure-hash');
        hmac.Hash = hash;
        hmac._init(<HMAC-KEY>);
        hmac.update(hmacMessage.value.replace(/^\s+|\s+$/g, ''));
        var hmacHash = hmac.getHMAC('HEX');
      </script>

In the example <HMAC-KEY> is the secret key to generate HMAC hash,
hmacHash is set to contain the HMAC hash.


## Dependencies

Element dependencies are managed via [Bower](http://bower.io/). You can
install that via:

    npm install -g bower

Then, go ahead and download the element's dependencies:

    bower install


## Related

[secure-random](http://github.com/hekahouse/secure-random/)
