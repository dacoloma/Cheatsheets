```C
// Get rid of the warning for write function
#include <unistd.h>

//Print characters 
void ft_putchar(char c)
{
  write(1, &c, 1);
}

//Print numbers
void ft_putnbr(int nb)
{
    if (nb<0)
    {
        ft_putchar('-');
        nb=-nb;
    }

    if(nb >= 10)
    {
        ft_putnbr(nb/10);
    }

    ft_putchar((nb%10)+48);
}


int main(void)
{
	//code
	return(0);
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY1MDg5MjU0MF19
-->