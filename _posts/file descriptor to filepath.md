# file descriptor to filepath

```c
#include <unistd.h>
#include <limits.h>

char filePath[PATH_MAX];
char fdPath[PATH_MAX];
if (readlink(fdPath, filePath, sizeof(filePath) -1) != -1)
{
	// do something with the filePath

}
```

