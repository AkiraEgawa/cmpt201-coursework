#define _POSIX_C_SOURCE 200809L
#define GNU_SOURCE
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <sys/types.h>
#include <sys/wait.h>
#include <unistd.h>
int main() {
  while (1) {
    pid_t pid;
    pid = fork();
    int status;
    if (pid == 0) {
      // is child
      FILE *stream = stdin;
      char *arg = NULL;
      size_t len = 0;
      int nchar;
      printf("Enter program to run.\n");
      // Read line
      nchar = getline(&arg, &len, stream);
      // Need to cut off \n
      arg[nchar - 1] = '\0';
      // execute
      if (execlp(arg, arg, (char *)NULL) == -1) {
        printf("Exec failure\n");
      }
    } else {
      // is parent
      waitpid(pid, &status, 0);
    }
  }
}
