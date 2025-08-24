# Get Next Line
**Get Next Line** is a function that reads a text file one line at a time using repeated calls. This function is designed to be used with a file descriptor, returning each line of the file sequentially. This project demonstrates my understanding of static variables.

Function Prototype:
```
char *get_next_line(int fd);
```
## Prerequisites
- A C compiler (e.g., `gcc` or `clang`)  

## Usage Instructions
1. Clone the repository:
```
git clone git@github.com:k2matu/42-get_next_line.git get_next_line
````
2. Navigate into the directory:
```
cd get_next_line
```
3. Create a source file (my_program.c) and include the header:
#### e.g., my_program.c:
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
4. Ensure example.txt exists in the same directory as your compiled program.
#### e.g., example.txt:
```
Example content:
The names "John Doe" for males, "Jane Doe" or "Jane Roe" for females, or "Jonnie Doe" and "Janie Doe" for children, or just "Doe" non-gender-specifically are used as placeholder names for a party whose true identity is unknown or must be withheld in a legal action, case, or discussion.
The names are also used to refer to acorpse or hospital patient whose identity is unknown.
This practice is widely used in the United States and Canada, but is rarely used in other English-speaking countries including the United Kingdom itself, from where the use of "John Doe" in a legal context originates.
The names Joe Bloggs or John Smith are used in the UK instead, as well as in Australia and New Zealand.
```

5. To compile your code, use the following command, adjusting the BUFFER_SIZE as needed (e.g., 42). 
```
cc -Wall -Wextra -Werror -D BUFFER_SIZE=42 get_next_line.c get_next_line_utils.c my_program.c -o my_program
```
6. Run the program: 
```
./my_program
```
