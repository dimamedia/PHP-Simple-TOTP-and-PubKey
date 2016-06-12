# class.tfa.php
Simple php class for generating public key and one-time password (**TOTP**) for two factor authentication

## How to?

```php
require("class.tfa.php");
$tfa = new tfa();
```

### Get public key:

```php
$pubkey = $tfa->getPubKey();

print $pubkey; // Example: RADV RKNM KOV3 Q22A

```
Store public key on the server with the user account and use it in TOTP generators like Google Authenticator or Pebble's QuickAuth.

### Generate TOTP - time-based one-time password:

```php
$pubkey = 'RADV RKNM KOV3 Q22A'; // Saved or given public key

$otp = $tfa->getOtp($pubkey);

print $otp; // Example: 194074
```
Use it to compare with TOTP generated on the other device.
