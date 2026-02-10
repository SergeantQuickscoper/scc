# Working List of Patterns to Replace

## `libc` functions

Starter List:

open
openat
read
write
close
execve
fork
socket
connect
dlopen
dlsym
syscall
asm

## Catalog to pick and choose from

### `syscall` and assembly inline
syscall
__syscall
sysenter
int $0x80

### I/O
open
openat
creat
read
write
pread
pwrite
lseek
close

### Memory and IPC
pipe
pipe2
dup
dup2
dup3
shmget
shmat
shmdt
shmctl
shm_open
shm_unlink

### Perms and Privilege
setuid
setgid
seteuid
setegid
setreuid
setregid
setgroups


### Execs and Process Related
fork
vfork
clone
execve
execv
execvp
execvpe
system
popen
posix_spawn
kill
raise
signal
sigaction
sigprocmask
pthread_kill

### Dynamic
dlopen
dlmopen
dlsym
dlclose

### Network
socket
socketpair
connect
bind
listen
accept
accept4
send
sendto
sendmsg
recv
recvfrom
recvmsg
shutdown
getsockopt
setsockopt

**Note**: It seems to me that replacing these function chokepoints should prevent damage but also look
into if patterns exist at a code block level (highly doubt and probably would cross into non-determinism
territory)

