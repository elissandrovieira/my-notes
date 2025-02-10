MiniLibX is a min library in C developed for 42 staff that allow the development of graphical programs. Is based in the X11 - the functions that manipulate the X Windows System.

Is used in [[Rank2]] at the graphical project, that could be:
- Fract-ol
- FDF
- So long

# Using the MiniLibX

## Start
To start it, use `mxl_init`, it return a structure. 
In the end use `mlx_destroy_display`.

```C
int main(void)  
{  
void *mlx;  
  
mlx = mlx_init();  
if (!mlx)  
{  
// Handle the error.  
return (1);  
}  
// Do some cool graphical stuff here…  
// Clean up before exiting. The Display struct and the xvar struct  
mlx_destroy_display(mlx);  
free(mlx);  
return (0);  
}
```

## The interaction
To create a new window, use `mlx_new_window`.
To look if a key is pressed or mouse is moved, use `mlx_key_hook`.

