# wofi-pass
Since `wofi` isn't a drop-in replacement for `rofi`, I couldn't use 
[rofi-pass](https://github.com/carnager/rofi-pass) anymore. So, I just made a 
version of `passmenu` that accomplishes everything I needed from `rofi-pass`. 

## What does it do?
This script uses [wofi](https://hg.sr.ht/~scoopta/wofi) and 
[ydotool](https://github.com/ReimuNotMoe/ydotool) to provide a completely 
Wayland-native way to conveniently use [pass](https://www.passwordstore.org/). 
It provides the same search that `passmenu` does, but shows a second dialogue 
that lets the user choose which field to copy/print.

It also assumes that [pass-otp](https://github.com/tadfisher/pass-otp) is 
installed if an `otpauth://...` string is present in a password file.

The script assumes several things:
1. The password is on the first line;
2. The rest of the lines are formatted as key:value pairs.

See the following example:

```
Th3Gr3at3stPassw0rd
username: JohnDoe
email: john@example.com
otpauth://totp/example?secret=ABCDCBABCDCBABCD
pin: 1234
```

I know this script needs some work; it was mostly hacked together in an 
afternoon to get the minimum functionality I needed.
