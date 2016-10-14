# kpcli-xclip
For some reason, I wasn't able to get kpcli to work with my clipboard.  
After reading [this answer on StackOverflow](http://stackoverflow.com/a/39580039) I changed the original kpcli script to use XClip::copy2 instead of Clipboard->copy. I had to download [XClip](https://www.av8n.com/security/Xclip.pm) and place the script in /usr/lib/perl5/site_perl/

Hope it helps.

## Here's the diff between the original kpcli file and the one available here

```
44a45,46
> use Xclip;
> 
1702c1704
<     Clipboard->copy('');
---
>     Xclip::copy2('');
1734c1736
<     Clipboard->copy($to_copy);
---
>     Xclip::copy2($to_copy);
```
