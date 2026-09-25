# get_next_line

Projet de l'école 42 Paris : lire une ligne depuis un descripteur de fichier, un appel à la fois, quelle que soit la taille du buffer (`BUFFER_SIZE`).

La fonction `get_next_line(int fd)` renvoie la ligne suivante (saut de ligne inclus), ou `NULL` en fin de fichier. Elle conserve son état entre les appels via une variable statique.

## Usage

```c
char *line;
int fd = open("fichier.txt", O_RDONLY);
while ((line = get_next_line(fd)))
{
    printf("%s", line);
    free(line);
}
```

Compilation avec `-D BUFFER_SIZE=n` pour choisir la taille de lecture.
