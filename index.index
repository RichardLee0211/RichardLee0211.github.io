initial note

Log
================================================================================

about some SUSv3 Code, need to group C library, C++ library and SUSv3 library individually
```cpp
/* C library */
#include <errno.h>

/* SUSv3 */
#include <sys/mman.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <fcntl.h> // file control options
#include <sys/time.h>
#include <sys/resource.h>

/* get file metadata */
struct stat sb;
int rv = fstat(fd, &sb); assert(rv == 0);

// TODO:
#include <stdexcept>
```

1'000'000 integer liberature would be allowed in c++14

MAP_POPULATE macro doesn't exist in macOS for mmap()

read in binary:
xxd file | more
or:
hexdump -C file.bin

jump between empty lines, } and { in vim

how to do paralle: only parallel query

#pragma once

// Use placement new.
Node *n = new (nodes + i) Node{array[i]};

about binary file:
using C library fopen, etc
using SUSv3 system call, open, read, write

```cpp
    // way 1: for each attributes, call read once, but system call is expensive
    numRead = read(fd, &trainfileID, sizeof(trainfileID));

    // way 2, preseve data in  char buf[] first and then pass data to data structure
    char buf[TFH_SZ];
    int numRead = read(fd, buf, TFH_SZ);

    // way 3, create a struct, then read and wirte it as a whole
    // potencial allignment problem
    struct TrainingFileHeader{
        char filetype[8]; /* TRAINING */
        uint64_t trainingFileID;
        uint64_t numPoints;
        uint64_t numDims;
    };
    fd = open(argv[1], O_RDONLY);
    read(fd, &tfd2, sizeof(tfd2));
```

```cpp
    // don't using assert because it checks training file,
    // which doesn't necessary come from me
    assert(numRead == TFH_SZ);
```

trick format of cstring
from: https://stackoverflow.com/questions/15376765/how-to-print-string-first-n-bytes-when-the-strings-length-is-greater-than-n
```cpp
    printf("%.*s", len, str);
```

BoundedPQueue is a good example to use ctor()=delete; As author would wanna
disable default constructor.

and explicit key word would be useful to force client use the function as required.
No implicit type convertion is allowed.

TODO:
- [x] time measure
- [x] parallel
- [x] writing data
- [ ]

TODO in mail:
- [ ] ssh wli100@spiedie.binghamton.edu
- [ ] prof from /home/kchiu/packages/linux-x86_64/bin
- [ ] std::atomic
- [ ]
- [ ]

ESR, structure padding:
http://www.catb.org/esr/structure-packing/
```cpp
#include <cstdint> // Use stdint.h if using C.
    struct TrainingHdr {
        char type_string[8];
        uint64_t id;
        uint64_t n_points;
        uint64_t n_dims;
    } __attribute__((packed));
```

Define these preprocessor symbols:

-D_GLIBCXX_CONCEPT_CHECKS
-D_GLIBCXX_DEBUG
-D_GLIBCXX_DEBUG_PEDANTIC

In particular, std::vector indexing with [] is now range checked. (Indexing with .at() is always range-checked.)

a good reading about copy elision and std::move: https://source.coveo.com/2018/11/07/interaction-between-move-semantic-and-copy-elision-in-c++/

something about shell history
history | tail -50 | grep "something"
!numofCommand

manage python library
--------------------------------------------------------------------------------
this is time to master python Anaconda

from: https://www.tldp.org/LDP/Linux-Filesystem-Hierarchy/html/usr.html
/usr is for "User System Resource" not original user

as I would use command line like 4 arguments, it would be nice to have a key map
that do move cursor forward a word, delete a word, move to begin(<C-a>), move to end(<C-e>)
TODO: learn ZSH and oh-my-shell

great the correctness is proved

"the linux programming interface",
================================================================================

Single UNIX Specification version 3 (SUSv3)
portable operating system interface (POSIX)

chapter 4 File I/O: the Universal I/O Model
--------------------------------------------------------------------------------

chapter 5 File I/O: Further Details
--------------------------------------------------------------------------------

chapter 15 File Attributes
--------------------------------------------------------------------------------

!! 15.4.2 Permissions on Directory, page.297

chapter 36 Process Resource
--------------------------------------------------------------------------------

chapter 49 memory mappings
--------------------------------------------------------------------------------

Appendix A Tracing system call
--------------------------------------------------------------------------------

macOS doesn't have strace tool

Appendix B parsing command-line options
--------------------------------------------------------------------------------
