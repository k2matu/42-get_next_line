# Get Next Line
Get Next Line is a function that reads a text file one line at a time using repeated calls. This function is designed to be used with a file descriptor, returning each line of the file sequentially. This project demonstrates my understanding of static variables.

Function Prototype:
```
char *get_next_line(int fd);
```
## Compilation
1. Clone the repository:
```
git clone git@github.com:k2matu/get_next_line.git
````
2. Navigate into the directory:
```
cd get_next_line
```
3. To compile your code, use the following command, adjusting the BUFFER_SIZE as needed (e.g., 42).

Replace <file> with the names of your source file.
```
cc -Wall -Wextra -Werror -D BUFFER_SIZE=42 get_next_line get_next_line_utils.c <file>.c
```

Ensure that you include the necessary header file in your source code where get_next_line is used.
### Example:
```
#include "get_next_line.h"
#include <fcntl.h>
#include <stdio.h>

int main(void)
{
    int fd = open("example.txt", O_RDONLY);
    char *line;

    if (fd < 0)
        return 1;

    while ((line = get_next_line(fd)) != NULL)
    {
        printf("%s", line);
        free(line);
    }

    close(fd);
    return 0;
}
```
