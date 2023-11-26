# TOTP

## what is a one time password (OTP)
## what is Hash-based Message Authentication Code (HMAC) 
## HTOP: 
### algo require from RFC for HOTP:
   - The algorithm MUST be sequence- or counter-based
   - The algorithm SHOULD be economical
   - The algorithm MUST work with tokens that do not support any
   numeric input, but MAY also be used with more sophisticated devices
   such as secure PIN-pads
   - The value displayed on the token MUST be easily read and entered
   by the user, HOTP value must be at least a 6-digit value.  It is also
   desirable that the HOTP value be 'numeric only'
   -  There MUST be user-friendly mechanisms available to
   resynchronize the counter
   - The algorithm MUST use a strong shared secret.  The length of
   the shared secret MUST be at least 128 bits.  This document
   RECOMMENDs a shared secret length of 160 bits.
### notes:
   - s for binary string representation: StToNum(110) = 6
   - C       8-byte counter value, the moving factor
   - K       shared secret between client and server
   - T       throttling parameter
   - s       resynchronization parameter
   - Digit   number of digits in an HOTP value

### descriptio:
   - HOTP Algo: HOTP(K,C) = Truncate(HMAC-SHA-1(K,C))