---
title: os_help（已更新）
date: 2017-03-04 00:09:52
categories:
  - Linux
tags:
  - os
  - help
comments: false
---

### Help on module OS

### MODULE REFERENCE
```
    https://docs.python.org/3.7/library/os
    
    The following documentation is automatically generated from the Python
    source files.  It may be incomplete, incorrect or include features that
    are considered implementation detail and may vary between Python
    implementations.  When in doubt, consult the module reference at the
    location listed above.
```

### DESCRIPTION
```
    This exports:
      - all functions from posix or nt, e.g. unlink, stat, etc.
      - os.path is either posixpath or ntpath
      - os.name is either 'posix' or 'nt'
      - os.curdir is a string representing the current directory (always '.')
      - os.pardir is a string representing the parent directory (always '..')
      - os.sep is the (or a most common) pathname separator ('/' or '\\')
      - os.extsep is the extension separator (always '.')
      - os.altsep is the alternate pathname separator (None or '/')
      - os.pathsep is the component separator used in $PATH etc
      - os.linesep is the line separator in text files ('\r' or '\n' or '\r\n')
      - os.defpath is the default search path for executables
      - os.devnull is the file path of the null device ('/dev/null', etc.)
    
    Programs that import and use 'os' stand a better chance of being
    portable between different platforms.  Of course, they must then
    only use functions that are defined by all platforms (e.g., unlink
    and opendir), and leave all pathname manipulation to os.path
    (e.g., split and join).
```

### CLASSES
```
    builtins.Exception(builtins.BaseException)
        builtins.OSError
    builtins.object
        posix.DirEntry
    builtins.tuple(builtins.object)
        stat_result
        statvfs_result
        terminal_size
        posix.times_result
        posix.uname_result
    
    class DirEntry(builtins.object)
     |  Methods defined here:
     |  
     |  __fspath__(self, /)
     |      Returns the path for the entry.
     |  
     |  __repr__(self, /)
     |      Return repr(self).
     |  
     |  inode(self, /)
     |      Return inode of the entry; cached per entry.
     |  
     |  is_dir(self, /, *, follow_symlinks=True)
     |      Return True if the entry is a directory; cached per entry.
     |  
     |  is_file(self, /, *, follow_symlinks=True)
     |      Return True if the entry is a file; cached per entry.
     |  
     |  is_symlink(self, /)
     |      Return True if the entry is a symbolic link; cached per entry.
     |  
     |  stat(self, /, *, follow_symlinks=True)
     |      Return stat_result object for the entry; cached per entry.
     |  
     |  ----------------------------------------------------------------------
     |  Data descriptors defined here:
     |  
     |  name
     |      the entry's base filename, relative to scandir() "path" argument
     |  
     |  path
     |      the entry's full path name; equivalent to os.path.join(scandir_path, entry.name)
    
    error = class OSError(Exception)
     |  Base class for I/O related errors.
     |  
     |  Method resolution order:
     |      OSError
     |      Exception
     |      BaseException
     |      object
     |  
     |  Methods defined here:
     |  
     |  __init__(self, /, *args, **kwargs)
     |      Initialize self.  See help(type(self)) for accurate signature.
     |  
     |  __reduce__(...)
     |      Helper for pickle.
     |  
     |  __str__(self, /)
     |      Return str(self).
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
     |  
     |  ----------------------------------------------------------------------
     |  Data descriptors defined here:
     |  
     |  characters_written
     |  
     |  errno
     |      POSIX exception code
     |  
     |  filename
     |      exception filename
     |  
     |  filename2
     |      second exception filename
     |  
     |  strerror
     |      exception strerror
     |  
     |  ----------------------------------------------------------------------
     |  Methods inherited from BaseException:
     |  
     |  __delattr__(self, name, /)
     |      Implement delattr(self, name).
     |  
     |  __getattribute__(self, name, /)
     |      Return getattr(self, name).
     |  
     |  __repr__(self, /)
     |      Return repr(self).
     |  
     |  __setattr__(self, name, value, /)
     |      Implement setattr(self, name, value).
     |  
     |  __setstate__(...)
     |  
     |  with_traceback(...)
     |      Exception.with_traceback(tb) --
     |      set self.__traceback__ to tb and return self.
     |  
     |  ----------------------------------------------------------------------
     |  Data descriptors inherited from BaseException:
     |  
     |  __cause__
     |      exception cause
     |  
     |  __context__
     |      exception context
     |  
     |  __dict__
     |  
     |  __suppress_context__
     |  
     |  __traceback__
     |  
     |  args
    
    class stat_result(builtins.tuple)
     |  stat_result(iterable=(), /)
     |  
     |  stat_result: Result from stat, fstat, or lstat.
     |  
     |  This object may be accessed either as a tuple of
     |    (mode, ino, dev, nlink, uid, gid, size, atime, mtime, ctime)
     |  or via the attributes st_mode, st_ino, st_dev, st_nlink, st_uid, and so on.
     |  
     |  Posix/windows: If your platform supports st_blksize, st_blocks, st_rdev,
     |  or st_flags, they are available as attributes only.
     |  
     |  See os.stat for more information.
     |  
     |  Method resolution order:
     |      stat_result
     |      builtins.tuple
     |      builtins.object
     |  
     |  Methods defined here:
     |  
     |  __reduce__(...)
     |      Helper for pickle.
     |  
     |  __repr__(self, /)
     |      Return repr(self).
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
     |  
     |  ----------------------------------------------------------------------
     |  Data descriptors defined here:
     |  
     |  st_atime
     |      time of last access
     |  
     |  st_atime_ns
     |      time of last access in nanoseconds
     |  
     |  st_birthtime
     |      time of creation
     |  
     |  st_blksize
     |      blocksize for filesystem I/O
     |  
     |  st_blocks
     |      number of blocks allocated
     |  
     |  st_ctime
     |      time of last change
     |  
     |  st_ctime_ns
     |      time of last change in nanoseconds
     |  
     |  st_dev
     |      device
     |  
     |  st_flags
     |      user defined flags for file
     |  
     |  st_gen
     |      generation number
     |  
     |  st_gid
     |      group ID of owner
     |  
     |  st_ino
     |      inode
     |  
     |  st_mode
     |      protection bits
     |  
     |  st_mtime
     |      time of last modification
     |  
     |  st_mtime_ns
     |      time of last modification in nanoseconds
     |  
     |  st_nlink
     |      number of hard links
     |  
     |  st_rdev
     |      device type (if inode device)
     |  
     |  st_size
     |      total size, in bytes
     |  
     |  st_uid
     |      user ID of owner
     |  
     |  ----------------------------------------------------------------------
     |  Data and other attributes defined here:
     |  
     |  n_fields = 22for NT or Posix depending on what system we're on.
     |  
     |  n_sequence_fields = 10
     |  s://docs.python.org/3.7/library/os
     |  n_unnamed_fields = 3
     |  following documentation is automatically generated from the Python
     |  ----------------------------------------------------------------------
     |  Methods inherited from builtins.tuple:ay vary between Python
     |  ementations.  When in doubt, consult the module reference at the
     |  __add__(self, value, /)
     |      Return self+value.
     |  ION
     |  __contains__(self, key, /)
     |      Return key in self.x or nt, e.g. unlink, stat, etc.
     |  os.path is either posixpath or ntpath
     |  __eq__(self, value, /)ix' or 'nt'
     |      Return self==value.epresenting the current directory (always '.')
     |  os.pardir is a string representing the parent directory (always '..')
     |  __ge__(self, value, /)st common) pathname separator ('/' or '\\')
     |      Return self>=value.ion separator (always '.')
     |  os.altsep is the alternate pathname separator (None or '/')
     |  __getattribute__(self, name, /)arator used in $PATH etc
     |      Return getattr(self, name).r in text files ('\r' or '\n' or '\r\n')
     |  os.defpath is the default search path for executables
     |  __getitem__(self, key, /)th of the null device ('/dev/null', etc.)
     |      Return self[key].
     |  rams that import and use 'os' stand a better chance of being
     |  __getnewargs__(self, /)platforms.  Of course, they must then
     |   use functions that are defined by all platforms (e.g., unlink
     |  __gt__(self, value, /)l pathname manipulation to os.path
     |      Return self>value.
     |  
     |  __hash__(self, /)
     |      Return hash(self).s.BaseException)
     |  builtins.OSError
     |  __iter__(self, /)
     |      Implement iter(self).
     |  tins.tuple(builtins.object)
     |  __le__(self, value, /)
     |      Return self<=value.
     |  terminal_size
     |  __len__(self, /)lt
     |      Return len(self).
     |  
     |  __lt__(self, value, /)ject)
     |      Return self<value.
     |  
     |  __mul__(self, value, /)
     |      Return self*value.or the entry.
     |  
     |  __ne__(self, value, /)
     |      Return self!=value.
     |  
     |  __rmul__(self, value, /)
     |      Return value*self.e entry; cached per entry.
     |  
     |  count(self, value, /)
     |      Return number of occurrences of value.
     |  
     |  index(self, value, start=0, stop=9223372036854775807, /)
     |      Return first index of value.
     |      
     |      Raises ValueError if the value is not present.
    
    class statvfs_result(builtins.tuple)
     |  statvfs_result(iterable=(), /)
     |  
     |  statvfs_result: Result from statvfs or fstatvfs.
     |  
     |  This object may be accessed either as a tuple of
     |    (bsize, frsize, blocks, bfree, bavail, files, ffree, favail, flag, namemax),
     |  or via the attributes f_bsize, f_frsize, f_blocks, f_bfree, and so on.
     |  
     |  See os.statvfs for more information.
     |  
     |  Method resolution order:
     |      statvfs_result
     |      builtins.tuple
     |      builtins.object
     |  
     |  Methods defined here:
     |  
     |  __reduce__(...)
     |      Helper for pickle.
     |  
     |  __repr__(self, /)
     |      Return repr(self).
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
     |  
     |  ----------------------------------------------------------------------
     |  Data descriptors defined here:
     |  
     |  f_bavail
     |  
     |  f_bfree
     |  
     |  f_blocks
     |  
     |  f_bsize
     |  
     |  f_favail
     |  
     |  f_ffree
     |  
     |  f_files
     |  
     |  f_flag
     |  
     |  f_frsize
     |  
     |  f_fsid
     |  
     |  f_namemax
     |  
     |  ----------------------------------------------------------------------
     |  Data and other attributes defined here:
     |  
     |  n_fields = 11
     |  
     |  n_sequence_fields = 10
     |  
     |  n_unnamed_fields = 0
     |  
     |  ----------------------------------------------------------------------
     |  Methods inherited from builtins.tuple:
     |  
     |  __add__(self, value, /)
     |      Return self+value.
     |  
     |  __contains__(self, key, /)
     |      Return key in self.
     |  
     |  __eq__(self, value, /)
     |      Return self==value.
     |  
     |  __ge__(self, value, /)
     |      Return self>=value.
     |  
     |  __getattribute__(self, name, /)
     |      Return getattr(self, name).
     |  
     |  __getitem__(self, key, /)
     |      Return self[key].
     |  
     |  __getnewargs__(self, /)
     |  
     |  __gt__(self, value, /)
     |      Return self>value.
     |  
     |  __hash__(self, /)
     |      Return hash(self).
     |  
     |  __iter__(self, /)
     |      Implement iter(self).
     |  
     |  __le__(self, value, /)
     |      Return self<=value.
     |  
     |  __len__(self, /)
     |      Return len(self).
     |  
     |  __lt__(self, value, /)
     |      Return self<value.
     |  
     |  __mul__(self, value, /)
     |      Return self*value.
     |  
     |  __ne__(self, value, /)
     |      Return self!=value.
     |  
     |  __rmul__(self, value, /)
     |      Return value*self.
     |  
     |  count(self, value, /)
     |      Return number of occurrences of value.
     |  
     |  index(self, value, start=0, stop=9223372036854775807, /)
     |      Return first index of value.
     |      
     |      Raises ValueError if the value is not present.
    
    class terminal_size(builtins.tuple)
     |  terminal_size(iterable=(), /)
     |  
     |  A tuple of (columns, lines) for holding terminal window size
     |  
     |  Method resolution order:
     |      terminal_size
     |      builtins.tuple
     |      builtins.object
     |  
     |  Methods defined here:
     |  
     |  __reduce__(...)
     |      Helper for pickle.
     |  
     |  __repr__(self, /)
     |      Return repr(self).
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
     |  
     |  ----------------------------------------------------------------------
     |  Data descriptors defined here:
     |  
     |  columns
     |      width of the terminal window in characters
     |  
     |  lines
     |      height of the terminal window in characters
     |  
     |  ----------------------------------------------------------------------
     |  Data and other attributes defined here:
     |  
     |  n_fields = 2
     |  
     |  n_sequence_fields = 2
     |  
     |  n_unnamed_fields = 0
     |  
     |  ----------------------------------------------------------------------
     |  Methods inherited from builtins.tuple:
     |  
     |  __add__(self, value, /)
     |      Return self+value.
     |  
     |  __contains__(self, key, /)
     |      Return key in self.
     |  
     |  __eq__(self, value, /)
     |      Return self==value.
     |  
     |  __ge__(self, value, /)
     |      Return self>=value.
     |  
     |  __getattribute__(self, name, /)
     |      Return getattr(self, name).
     |  
     |  __getitem__(self, key, /)
     |      Return self[key].
     |  
     |  __getnewargs__(self, /)
     |  
     |  __gt__(self, value, /)
     |      Return self>value.
     |  
     |  __hash__(self, /)
     |      Return hash(self).
     |  
     |  __iter__(self, /)
     |      Implement iter(self).
     |  
     |  __le__(self, value, /)
     |      Return self<=value.
     |  
     |  __len__(self, /)
     |      Return len(self).
     |  
     |  __lt__(self, value, /)
     |      Return self<value.
     |  
     |  __mul__(self, value, /)
     |      Return self*value.
     |  
     |  __ne__(self, value, /)
     |      Return self!=value.
     |  
     |  __rmul__(self, value, /)
     |      Return value*self.
     |  
     |  count(self, value, /)
     |      Return number of occurrences of value.
     |  
     |  index(self, value, start=0, stop=9223372036854775807, /)
     |      Return first index of value.
     |      
     |      Raises ValueError if the value is not present.
    
    class times_result(builtins.tuple)
     |  times_result(iterable=(), /)
     |  
     |  times_result: Result from os.times().
     |  
     |  This object may be accessed either as a tuple of
     |    (user, system, children_user, children_system, elapsed),
     |  or via the attributes user, system, children_user, children_system,
     |  and elapsed.
     |  
     |  See os.times for more information.
     |  
     |  Method resolution order:
     |      times_result
     |      builtins.tuple
     |      builtins.object
     |  
     |  Methods defined here:
     |  
     |  __reduce__(...)
     |      Helper for pickle.
     |  
     |  __repr__(self, /)
     |      Return repr(self).
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
     |  
     |  ----------------------------------------------------------------------
     |  Data descriptors defined here:
     |  
     |  children_system
     |      system time of children
     |  
     |  children_user
     |      user time of children
     |  
     |  elapsed
     |      elapsed time since an arbitrary point in the past
     |  
     |  system
     |      system time
     |  
     |  user
     |      user time
     |  
     |  ----------------------------------------------------------------------
     |  Data and other attributes defined here:
     |  
     |  n_fields = 5
     |  
     |  n_sequence_fields = 5
     |  
     |  n_unnamed_fields = 0
     |  
     |  ----------------------------------------------------------------------
     |  Methods inherited from builtins.tuple:
     |  
     |  __add__(self, value, /)
     |      Return self+value.
     |  
     |  __contains__(self, key, /)
     |      Return key in self.
     |  
     |  __eq__(self, value, /)
     |      Return self==value.
     |  
     |  __ge__(self, value, /)
     |      Return self>=value.
     |  
     |  __getattribute__(self, name, /)
     |      Return getattr(self, name).
     |  
     |  __getitem__(self, key, /)
     |      Return self[key].
     |  
     |  __getnewargs__(self, /)
     |  
     |  __gt__(self, value, /)
     |      Return self>value.
     |  
     |  __hash__(self, /)
     |      Return hash(self).
     |  
     |  __iter__(self, /)
     |      Implement iter(self).
     |  
     |  __le__(self, value, /)
     |      Return self<=value.
     |  
     |  __len__(self, /)
     |      Return len(self).
     |  
     |  __lt__(self, value, /)
     |      Return self<value.
     |  
     |  __mul__(self, value, /)
     |      Return self*value.
     |  
     |  __ne__(self, value, /)
     |      Return self!=value.
     |  
     |  __rmul__(self, value, /)
     |      Return value*self.
     |  
     |  count(self, value, /)
     |      Return number of occurrences of value.
     |  
     |  index(self, value, start=0, stop=9223372036854775807, /)
     |      Return first index of value.
     |      
     |      Raises ValueError if the value is not present.
    
    class uname_result(builtins.tuple)
     |  uname_result(iterable=(), /)
     |  
     |  uname_result: Result from os.uname().
     |  
     |  This object may be accessed either as a tuple of
     |    (sysname, nodename, release, version, machine),
     |  or via the attributes sysname, nodename, release, version, and machine.
     |  
     |  See os.uname for more information.
     |  
     |  Method resolution order:
     |      uname_result
     |      builtins.tuple
     |      builtins.object
     |  
     |  Methods defined here:
     |  
     |  __reduce__(...)
     |      Helper for pickle.
     |  
     |  __repr__(self, /)
     |      Return repr(self).
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
     |  
     |  ----------------------------------------------------------------------
     |  Data descriptors defined here:
     |  
     |  machine
     |      hardware identifier
     |  
     |  nodename
     |      name of machine on network (implementation-defined)
     |  
     |  release
     |      operating system release
     |  
     |  sysname
     |      operating system name
     |  
     |  version
     |      operating system version
     |  
     |  ----------------------------------------------------------------------
     |  Data and other attributes defined here:
     |  
     |  n_fields = 5
     |  
     |  n_sequence_fields = 5
     |  
     |  n_unnamed_fields = 0
     |  
     |  ----------------------------------------------------------------------
     |  Methods inherited from builtins.tuple:
     |  
     |  __add__(self, value, /)
     |      Return self+value.
     |  
     |  __contains__(self, key, /)
     |      Return key in self.
     |  
     |  __eq__(self, value, /)
     |      Return self==value.
     |  
     |  __ge__(self, value, /)
     |      Return self>=value.
     |  
     |  __getattribute__(self, name, /)
     |      Return getattr(self, name).
     |  
     |  __getitem__(self, key, /)
     |      Return self[key].
     |  
     |  __getnewargs__(self, /)
     |  
     |  __gt__(self, value, /)
     |      Return self>value.
     |  
     |  __hash__(self, /)
     |      Return hash(self).
     |  
     |  __iter__(self, /)
     |      Implement iter(self).
     |  
     |  __le__(self, value, /)
     |      Return self<=value.
     |  
     |  __len__(self, /)
     |      Return len(self).
     |  
     |  __lt__(self, value, /)
     |      Return self<value.
     |  
     |  __mul__(self, value, /)
     |      Return self*value.
     |  
     |  __ne__(self, value, /)
     |      Return self!=value.
     |  
     |  __rmul__(self, value, /)
     |      Return value*self.
     |  
     |  count(self, value, /)
     |      Return number of occurrences of value.
     |  
     |  index(self, value, start=0, stop=9223372036854775807, /)
     |      Return first index of value.
     |      
     |      Raises ValueError if the value is not present.

FUNCTIONS
    WCOREDUMP(status, /)
        Return True if the process returning status was dumped to a core file.
    
    WEXITSTATUS(status)
        Return the process return code from status.
    
    WIFCONTINUED(status)
        Return True if a particular process was continued from a job control stop.
        
        Return True if the process returning status was continued from a
        job control stop.
    
    WIFEXITED(status)
        Return True if the process returning status exited via the exit() system call.
    
    WIFSIGNALED(status)
        Return True if the process returning status was terminated by a signal.
    
    WIFSTOPPED(status)
        Return True if the process returning status was stopped.
    
    WSTOPSIG(status)
        Return the signal that stopped the process that provided the status value.
    
    WTERMSIG(status)
        Return the signal that terminated the process that provided the status value.
    
    _exit(status)
        Exit to the system with specified status, without normal exit processing.
    
    abort()
        Abort the interpreter immediately.
        
        This function 'dumps core' or otherwise fails in the hardest way possible
        on the hosting operating system.  This function never returns.
    
    access(path, mode, *, dir_fd=None, effective_ids=False, follow_symlinks=True)
        Use the real uid/gid to test for access to a path.
        
          path
            Path to be tested; can be string, bytes, or a path-like object.
          mode
            Operating-system mode bitfield.  Can be F_OK to test existence,
            or the inclusive-OR of R_OK, W_OK, and X_OK.
          dir_fd
            If not None, it should be a file descriptor open to a directory,
            and path should be relative; path will then be relative to that
            directory.
          effective_ids
            If True, access will use the effective uid/gid instead of
            the real uid/gid.
          follow_symlinks
            If False, and the last element of the path is a symbolic link,
            access will examine the symbolic link itself instead of the file
            the link points to.
        
        dir_fd, effective_ids, and follow_symlinks may not be implemented
          on your platform.  If they are unavailable, using them will raise a
          NotImplementedError.
        
        Note that most operations will use the effective uid/gid, therefore this
          routine can be used in a suid/sgid environment to test if the invoking user
          has the specified access to the path.
    
    chdir(path)
        Change the current working directory to the specified path.
        
        path may always be specified as a string.
        On some platforms, path may also be specified as an open file descriptor.
          If this functionality is unavailable, using it raises an exception.
    
    chflags(path, flags, follow_symlinks=True)
        Set file flags.
        
        If follow_symlinks is False, and the last element of the path is a symbolic
          link, chflags will change flags on the symbolic link itself instead of the
          file the link points to.
        follow_symlinks may not be implemented on your platform.  If it is
        unavailable, using it will raise a NotImplementedError.
    
    chmod(path, mode, *, dir_fd=None, follow_symlinks=True)
        Change the access permissions of a file.
        
          path
            Path to be modified.  May always be specified as a str, bytes, or a path-like object.
            On some platforms, path may also be specified as an open file descriptor.
            If this functionality is unavailable, using it raises an exception.
          mode
            Operating-system mode bitfield.
          dir_fd
            If not None, it should be a file descriptor open to a directory,
            and path should be relative; path will then be relative to that
            directory.
          follow_symlinks
            If False, and the last element of the path is a symbolic link,
            chmod will modify the symbolic link itself instead of the file
            the link points to.
        
        It is an error to use dir_fd or follow_symlinks when specifying path as
          an open file descriptor.
        dir_fd and follow_symlinks may not be implemented on your platform.
          If they are unavailable, using them will raise a NotImplementedError.
    
    chown(path, uid, gid, *, dir_fd=None, follow_symlinks=True)
        Change the owner and group id of path to the numeric uid and gid.\
        
          path
            Path to be examined; can be string, bytes, a path-like object, or open-file-descriptor int.
          dir_fd
            If not None, it should be a file descriptor open to a directory,
            and path should be relative; path will then be relative to that
            directory.
          follow_symlinks
            If False, and the last element of the path is a symbolic link,
            stat will examine the symbolic link itself instead of the file
            the link points to.
        
        path may always be specified as a string.
        On some platforms, path may also be specified as an open file descriptor.
          If this functionality is unavailable, using it raises an exception.
        If dir_fd is not None, it should be a file descriptor open to a directory,
          and path should be relative; path will then be relative to that directory.
        If follow_symlinks is False, and the last element of the path is a symbolic
          link, chown will modify the symbolic link itself instead of the file the
          link points to.
        It is an error to use dir_fd or follow_symlinks when specifying path as
          an open file descriptor.
        dir_fd and follow_symlinks may not be implemented on your platform.
          If they are unavailable, using them will raise a NotImplementedError.
    
    chroot(path)
        Change root directory to path.
    
    close(fd)
        Close a file descriptor.
    
    closerange(fd_low, fd_high, /)
        Closes all file descriptors in [fd_low, fd_high), ignoring errors.
    
    confstr(name, /)
        Return a string-valued system configuration variable.
    
    cpu_count()
        Return the number of CPUs in the system; return None if indeterminable.
        
        This number is not equivalent to the number of CPUs the current process can
        use.  The number of usable CPUs can be obtained with
        ``len(os.sched_getaffinity(0))``
    
    ctermid()
        Return the name of the controlling terminal for this process.
    
    device_encoding(fd)
        Return a string describing the encoding of a terminal's file descriptor.
        
        The file descriptor must be attached to a terminal.
        If the device is not a terminal, return None.
    
    dup(fd, /)
        Return a duplicate of a file descriptor.
    
    dup2(fd, fd2, inheritable=True)
        Duplicate file descriptor.
    
    execl(file, *args)
        execl(file, *args)
        
        Execute the executable file with argument list args, replacing the
        current process.
    
    execle(file, *args)
        execle(file, *args, env)
        
        Execute the executable file with argument list args and
        environment env, replacing the current process.
    
    execlp(file, *args)
        execlp(file, *args)
        
        Execute the executable file (which is searched for along $PATH)
        with argument list args, replacing the current process.
    
    execlpe(file, *args)
        execlpe(file, *args, env)
        
        Execute the executable file (which is searched for along $PATH)
        with argument list args and environment env, replacing the current
        process.
    
    execv(path, argv, /)
        Execute an executable path with arguments, replacing current process.
        
        path
          Path of executable file.
        argv
          Tuple or list of strings.
    
    execve(path, argv, env)
        Execute an executable path with arguments, replacing current process.
        
        path
          Path of executable file.
        argv
          Tuple or list of strings.
        env
          Dictionary of strings mapping to strings.
    
    execvp(file, args)
        execvp(file, args)
        
        Execute the executable file (which is searched for along $PATH)
        with argument list args, replacing the current process.
        args may be a list or tuple of strings.
    
    execvpe(file, args, env)
        execvpe(file, args, env)
        
        Execute the executable file (which is searched for along $PATH)
        with argument list args and environment env , replacing the
        current process.
        args may be a list or tuple of strings.
    
    fchdir(fd)
        Change to the directory of the given file descriptor.
        
        fd must be opened on a directory, not a file.
        Equivalent to os.chdir(fd).
    
    fchmod(fd, mode)
        Change the access permissions of the file given by file descriptor fd.
        
        Equivalent to os.chmod(fd, mode).
    
    fchown(fd, uid, gid)
        Change the owner and group id of the file specified by file descriptor.
        
        Equivalent to os.chown(fd, uid, gid).
    
    fdopen(fd, *args, **kwargs)
        # Supply os.fdopen()
    
    fork()
        Fork a child process.
        
        Return 0 to child process and PID of child to parent process.
    
    forkpty()
        Fork a new process with a new pseudo-terminal as controlling tty.
        
        Returns a tuple of (pid, master_fd).
        Like fork(), return pid of 0 to the child process,
        and pid of child to the parent process.
        To both, return fd of newly opened pseudo-terminal.
    
    fpathconf(fd, name, /)
        Return the configuration limit name for the file descriptor fd.
        
        If there is no limit, return -1.
    
    fsdecode(filename)
        Decode filename (an os.PathLike, bytes, or str) from the filesystem
        encoding with 'surrogateescape' error handler, return str unchanged. On
        Windows, use 'strict' error handler if the file system encoding is
        'mbcs' (which is the default encoding).
    
    fsencode(filename)
        Encode filename (an os.PathLike, bytes, or str) to the filesystem
        encoding with 'surrogateescape' error handler, return bytes unchanged.
        On Windows, use 'strict' error handler if the file system encoding is
        'mbcs' (which is the default encoding).
    
    fspath(path)
        Return the file system path representation of the object.
        
        If the object is str or bytes, then allow it to pass through as-is. If the
        object defines __fspath__(), then return the result of that method. All other
        types raise a TypeError.
    
    fstat(fd)
        Perform a stat system call on the given file descriptor.
        
        Like stat(), but for an open file descriptor.
        Equivalent to os.stat(fd).
    
    fstatvfs(fd, /)
        Perform an fstatvfs system call on the given fd.
        
        Equivalent to statvfs(fd).
    
    fsync(fd)
        Force write of fd to disk.
    
    ftruncate(fd, length, /)
        Truncate a file, specified by file descriptor, to a specific length.
    
    fwalk(top='.', topdown=True, onerror=None, *, follow_symlinks=False, dir_fd=None)
        Directory tree generator.
        
        This behaves exactly like walk(), except that it yields a 4-tuple
        
            dirpath, dirnames, filenames, dirfd
        
        `dirpath`, `dirnames` and `filenames` are identical to walk() output,
        and `dirfd` is a file descriptor referring to the directory `dirpath`.
        
        The advantage of fwalk() over walk() is that it's safe against symlink
        races (when follow_symlinks is False).
        
        If dir_fd is not None, it should be a file descriptor open to a directory,
          and top should be relative; top will then be relative to that directory.
          (dir_fd is always supported for fwalk.)
        
        Caution:
        Since fwalk() yields file descriptors, those are only valid until the
        next iteration step, so you should dup() them if you want to keep them
        for a longer period.
        
        Example:
        
        import os
        for root, dirs, files, rootfd in os.fwalk('python/Lib/email'):
            print(root, "consumes", end="")
            print(sum([os.stat(name, dir_fd=rootfd).st_size for name in files]),
                  end="")
            print("bytes in", len(files), "non-directory files")
            if 'CVS' in dirs:
                dirs.remove('CVS')  # don't visit CVS directories
    
    get_blocking(...)
        get_blocking(fd) -> bool
        
        Get the blocking mode of the file descriptor:
        False if the O_NONBLOCK flag is set, True if the flag is cleared.
    
    get_exec_path(env=None)
        Returns the sequence of directories that will be searched for the
        named executable (similar to a shell) when launching a process.
        
        *env* must be an environment variable dict or None.  If *env* is None,
        os.environ will be used.
    
    get_inheritable(fd, /)
        Get the close-on-exe flag of the specified file descriptor.
    
    get_terminal_size(...)
        Return the size of the terminal window as (columns, lines).
        
        The optional argument fd (default standard output) specifies
        which file descriptor should be queried.
        
        If the file descriptor is not connected to a terminal, an OSError
        is thrown.
        
        This function will only be defined if an implementation is
        available for this system.
        
        shutil.get_terminal_size is the high-level function which should 
        normally be used, os.get_terminal_size is the low-level implementation.
    
    getcwd()
        Return a unicode string representing the current working directory.
    
    getcwdb()
        Return a bytes string representing the current working directory.
    
    getegid()
        Return the current process's effective group id.
    
    getenv(key, default=None)
        Get an environment variable, return None if it doesn't exist.
        The optional second argument can specify an alternate default.
        key, default and the result are str.
    
    getenvb(key, default=None)
        Get an environment variable, return None if it doesn't exist.
        The optional second argument can specify an alternate default.
        key, default and the result are bytes.
    
    geteuid()
        Return the current process's effective user id.
    
    getgid()
        Return the current process's group id.
    
    getgrouplist(...)
        getgrouplist(user, group) -> list of groups to which a user belongs
        
        Returns a list of groups to which a user belongs.
        
            user: username to lookup
            group: base group id of the user
    
    getgroups()
        Return list of supplemental group IDs for the process.
    
    getloadavg()
        Return average recent system load information.
        
        Return the number of processes in the system run queue averaged over
        the last 1, 5, and 15 minutes as a tuple of three floats.
        Raises OSError if the load average was unobtainable.
    
    getlogin()
        Return the actual login name.
    
    getpgid(pid)
        Call the system call getpgid(), and return the result.
    
    getpgrp()
        Return the current process group id.
    
    getpid()
        Return the current process id.
    
    getppid()
        Return the parent's process id.
        
        If the parent process has already exited, Windows machines will still
        return its id; others systems will return the id of the 'init' process (1).
    
    getpriority(which, who)
        Return program scheduling priority.
    
    getsid(pid, /)
        Call the system call getsid(pid) and return the result.
    
    getuid()
        Return the current process's user id.
    
    initgroups(...)
        initgroups(username, gid) -> None
        
        Call the system initgroups() to initialize the group access list with all of
        the groups of which the specified username is a member, plus the specified
        group id.
    
    isatty(fd, /)
        Return True if the fd is connected to a terminal.
        
        Return True if the file descriptor is an open file descriptor
        connected to the slave end of a terminal.
    
    kill(pid, signal, /)
        Kill a process with a signal.
    
    killpg(pgid, signal, /)
        Kill a process group with a signal.
    
    lchflags(path, flags)
        Set file flags.
        
        This function will not follow symbolic links.
        Equivalent to chflags(path, flags, follow_symlinks=False).
    
    lchmod(path, mode)
        Change the access permissions of a file, without following symbolic links.
        
        If path is a symlink, this affects the link itself rather than the target.
        Equivalent to chmod(path, mode, follow_symlinks=False)."
    
    lchown(path, uid, gid)
        Change the owner and group id of path to the numeric uid and gid.
        
        This function will not follow symbolic links.
        Equivalent to os.chown(path, uid, gid, follow_symlinks=False).
    
    link(src, dst, *, src_dir_fd=None, dst_dir_fd=None, follow_symlinks=True)
        Create a hard link to a file.
        
        If either src_dir_fd or dst_dir_fd is not None, it should be a file
          descriptor open to a directory, and the respective path string (src or dst)
          should be relative; the path will then be relative to that directory.
        If follow_symlinks is False, and the last element of src is a symbolic
          link, link will create a link to the symbolic link itself instead of the
          file the link points to.
        src_dir_fd, dst_dir_fd, and follow_symlinks may not be implemented on your
          platform.  If they are unavailable, using them will raise a
          NotImplementedError.
    
    listdir(path=None)
        Return a list containing the names of the files in the directory.
        
        path can be specified as either str, bytes, or a path-like object.  If path is bytes,
          the filenames returned will also be bytes; in all other circumstances
          the filenames returned will be str.
        If path is None, uses the path='.'.
        On some platforms, path may also be specified as an open file descriptor;\
          the file descriptor must refer to a directory.
          If this functionality is unavailable, using it raises NotImplementedError.
        
        The list is in arbitrary order.  It does not include the special
        entries '.' and '..' even if they are present in the directory.
    
    lockf(fd, command, length, /)
        Apply, test or remove a POSIX lock on an open file descriptor.
        
        fd
          An open file descriptor.
        command
          One of F_LOCK, F_TLOCK, F_ULOCK or F_TEST.
        length
          The number of bytes to lock, starting at the current position.
    
    lseek(fd, position, how, /)
        Set the position of a file descriptor.  Return the new position.
        
        Return the new cursor position in number of bytes
        relative to the beginning of the file.
    
    lstat(path, *, dir_fd=None)
        Perform a stat system call on the given path, without following symbolic links.
        
        Like stat(), but do not follow symbolic links.
        Equivalent to stat(path, follow_symlinks=False).
    
    major(device, /)
        Extracts a device major number from a raw device number.
    
    makedev(major, minor, /)
        Composes a raw device number from the major and minor device numbers.
    
    makedirs(name, mode=511, exist_ok=False)
        makedirs(name [, mode=0o777][, exist_ok=False])
        
        Super-mkdir; create a leaf directory and all intermediate ones.  Works like
        mkdir, except that any intermediate path segment (not just the rightmost)
        will be created if it does not exist. If the target directory already
        exists, raise an OSError if exist_ok is False. Otherwise no exception is
        raised.  This is recursive.
    
    minor(device, /)
        Extracts a device minor number from a raw device number.
    
    mkdir(path, mode=511, *, dir_fd=None)
        Create a directory.
        
        If dir_fd is not None, it should be a file descriptor open to a directory,
          and path should be relative; path will then be relative to that directory.
        dir_fd may not be implemented on your platform.
          If it is unavailable, using it will raise a NotImplementedError.
        
        The mode argument is ignored on Windows.
    
    mkfifo(path, mode=438, *, dir_fd=None)
        Create a "fifo" (a POSIX named pipe).
        
        If dir_fd is not None, it should be a file descriptor open to a directory,
          and path should be relative; path will then be relative to that directory.
        dir_fd may not be implemented on your platform.
          If it is unavailable, using it will raise a NotImplementedError.
    
    mknod(path, mode=384, device=0, *, dir_fd=None)
        Create a node in the file system.
        
        Create a node in the file system (file, device special file or named pipe)
        at path.  mode specifies both the permissions to use and the
        type of node to be created, being combined (bitwise OR) with one of
        S_IFREG, S_IFCHR, S_IFBLK, and S_IFIFO.  If S_IFCHR or S_IFBLK is set on mode,
        device defines the newly created device special file (probably using
        os.makedev()).  Otherwise device is ignored.
        
        If dir_fd is not None, it should be a file descriptor open to a directory,
          and path should be relative; path will then be relative to that directory.
        dir_fd may not be implemented on your platform.
          If it is unavailable, using it will raise a NotImplementedError.
    
    nice(increment, /)
        Add increment to the priority of process and return the new priority.
    
    open(path, flags, mode=511, *, dir_fd=None)
        Open a file for low level IO.  Returns a file descriptor (integer).
        
        If dir_fd is not None, it should be a file descriptor open to a directory,
          and path should be relative; path will then be relative to that directory.
        dir_fd may not be implemented on your platform.
          If it is unavailable, using it will raise a NotImplementedError.
    
    openpty()
        Open a pseudo-terminal.
        
        Return a tuple of (master_fd, slave_fd) containing open file descriptors
        for both the master and slave ends.
    
    pathconf(path, name)
        Return the configuration limit name for the file or directory path.
        
        If there is no limit, return -1.
        On some platforms, path may also be specified as an open file descriptor.
          If this functionality is unavailable, using it raises an exception.
    
    pipe()
        Create a pipe.
        
        Returns a tuple of two file descriptors:
          (read_fd, write_fd)
    
    popen(cmd, mode='r', buffering=-1)
        # Supply os.popen()
    
    pread(fd, length, offset, /)
        Read a number of bytes from a file descriptor starting at a particular offset.
        
        Read length bytes from file descriptor fd, starting at offset bytes from
        the beginning of the file.  The file offset remains unchanged.
    
    putenv(name, value, /)
        Change or add an environment variable.
    
    pwrite(fd, buffer, offset, /)
        Write bytes to a file descriptor starting at a particular offset.
        
        Write buffer to fd, starting at offset bytes from the beginning of
        the file.  Returns the number of bytes writte.  Does not change the
        current file offset.
    
    read(fd, length, /)
        Read from a file descriptor.  Returns a bytes object.
    
    readlink(...)
        readlink(path, *, dir_fd=None) -> path
        
        Return a string representing the path to which the symbolic link points.
        
        If dir_fd is not None, it should be a file descriptor open to a directory,
          and path should be relative; path will then be relative to that directory.
        dir_fd may not be implemented on your platform.
          If it is unavailable, using it will raise a NotImplementedError.
    
    readv(fd, buffers, /)
        Read from a file descriptor fd into an iterable of buffers.
        
        The buffers should be mutable buffers accepting bytes.
        readv will transfer data into each buffer until it is full
        and then move on to the next buffer in the sequence to hold
        the rest of the data.
        
        readv returns the total number of bytes read,
        which may be less than the total capacity of all the buffers.
    
    register_at_fork(*, before=None, after_in_child=None, after_in_parent=None)
        Register callables to be called when forking a new process.
        
          before
            A callable to be called in the parent before the fork() syscall.
          after_in_child
            A callable to be called in the child after fork().
          after_in_parent
            A callable to be called in the parent after fork().
        
        'before' callbacks are called in reverse order.
        'after_in_child' and 'after_in_parent' callbacks are called in order.
    
    remove(path, *, dir_fd=None)
        Remove a file (same as unlink()).
        
        If dir_fd is not None, it should be a file descriptor open to a directory,
          and path should be relative; path will then be relative to that directory.
        dir_fd may not be implemented on your platform.
          If it is unavailable, using it will raise a NotImplementedError.
    
    removedirs(name)
        removedirs(name)
        
        Super-rmdir; remove a leaf directory and all empty intermediate
        ones.  Works like rmdir except that, if the leaf directory is
        successfully removed, directories corresponding to rightmost path
        segments will be pruned away until either the whole path is
        consumed or an error occurs.  Errors during this latter phase are
        ignored -- they generally mean that a directory was not empty.
    
    rename(src, dst, *, src_dir_fd=None, dst_dir_fd=None)
        Rename a file or directory.
        
        If either src_dir_fd or dst_dir_fd is not None, it should be a file
          descriptor open to a directory, and the respective path string (src or dst)
          should be relative; the path will then be relative to that directory.
        src_dir_fd and dst_dir_fd, may not be implemented on your platform.
          If they are unavailable, using them will raise a NotImplementedError.
    
    renames(old, new)
        renames(old, new)
        
        Super-rename; create directories as necessary and delete any left
        empty.  Works like rename, except creation of any intermediate
        directories needed to make the new pathname good is attempted
        first.  After the rename, directories corresponding to rightmost
        path segments of the old name will be pruned until either the
        whole path is consumed or a nonempty directory is found.
        
        Note: this function can fail with the new directory structure made
        if you lack permissions needed to unlink the leaf directory or
        file.
    
    replace(src, dst, *, src_dir_fd=None, dst_dir_fd=None)
        Rename a file or directory, overwriting the destination.
        
        If either src_dir_fd or dst_dir_fd is not None, it should be a file
          descriptor open to a directory, and the respective path string (src or dst)
          should be relative; the path will then be relative to that directory.
        src_dir_fd and dst_dir_fd, may not be implemented on your platform.
          If they are unavailable, using them will raise a NotImplementedError.
    
    rmdir(path, *, dir_fd=None)
        Remove a directory.
        
        If dir_fd is not None, it should be a file descriptor open to a directory,
          and path should be relative; path will then be relative to that directory.
        dir_fd may not be implemented on your platform.
          If it is unavailable, using it will raise a NotImplementedError.
    
    scandir(path=None)
        Return an iterator of DirEntry objects for given path.
        
        path can be specified as either str, bytes, or a path-like object.  If path
        is bytes, the names of yielded DirEntry objects will also be bytes; in
        all other circumstances they will be str.
        
        If path is None, uses the path='.'.
    
    sched_get_priority_max(policy)
        Get the maximum scheduling priority for policy.
    
    sched_get_priority_min(policy)
        Get the minimum scheduling priority for policy.
    
    sched_yield()
        Voluntarily relinquish the CPU.
    
    sendfile(...)
        sendfile(out, in, offset, count) -> byteswritten
        sendfile(out, in, offset, count[, headers][, trailers], flags=0)
                    -> byteswritten
        Copy count bytes from file descriptor in to file descriptor out.
    
    set_blocking(...)
        set_blocking(fd, blocking)
        
        Set the blocking mode of the specified file descriptor.
        Set the O_NONBLOCK flag if blocking is False,
        clear the O_NONBLOCK flag otherwise.
    
    set_inheritable(fd, inheritable, /)
        Set the inheritable flag of the specified file descriptor.
    
    setegid(egid, /)
        Set the current process's effective group id.
    
    seteuid(euid, /)
        Set the current process's effective user id.
    
    setgid(gid, /)
        Set the current process's group id.
    
    setgroups(groups, /)
        Set the groups of the current process to list.
    
    setpgid(pid, pgrp, /)
        Call the system call setpgid(pid, pgrp).
    
    setpgrp()
        Make the current process the leader of its process group.
    
    setpriority(which, who, priority)
        Set program scheduling priority.
    
    setregid(rgid, egid, /)
        Set the current process's real and effective group ids.
    
    setreuid(ruid, euid, /)
        Set the current process's real and effective user ids.
    
    setsid()
        Call the system call setsid().
    
    setuid(uid, /)
        Set the current process's user id.
    
    spawnl(mode, file, *args)
        spawnl(mode, file, *args) -> integer
        
        Execute file with arguments from args in a subprocess.
        If mode == P_NOWAIT return the pid of the process.
        If mode == P_WAIT return the process's exit code if it exits normally;
        otherwise return -SIG, where SIG is the signal that killed it.
    
    spawnle(mode, file, *args)
        spawnle(mode, file, *args, env) -> integer
        
        Execute file with arguments from args in a subprocess with the
        supplied environment.
        If mode == P_NOWAIT return the pid of the process.
        If mode == P_WAIT return the process's exit code if it exits normally;
        otherwise return -SIG, where SIG is the signal that killed it.
    
    spawnlp(mode, file, *args)
        spawnlp(mode, file, *args) -> integer
        
        Execute file (which is looked for along $PATH) with arguments from
        args in a subprocess with the supplied environment.
        If mode == P_NOWAIT return the pid of the process.
        If mode == P_WAIT return the process's exit code if it exits normally;
        otherwise return -SIG, where SIG is the signal that killed it.
    
    spawnlpe(mode, file, *args)
        spawnlpe(mode, file, *args, env) -> integer
        
        Execute file (which is looked for along $PATH) with arguments from
        args in a subprocess with the supplied environment.
        If mode == P_NOWAIT return the pid of the process.
        If mode == P_WAIT return the process's exit code if it exits normally;
        otherwise return -SIG, where SIG is the signal that killed it.
    
    spawnv(mode, file, args)
        spawnv(mode, file, args) -> integer
        
        Execute file with arguments from args in a subprocess.
        If mode == P_NOWAIT return the pid of the process.
        If mode == P_WAIT return the process's exit code if it exits normally;
        otherwise return -SIG, where SIG is the signal that killed it.
    
    spawnve(mode, file, args, env)
        spawnve(mode, file, args, env) -> integer
        
        Execute file with arguments from args in a subprocess with the
        specified environment.
        If mode == P_NOWAIT return the pid of the process.
        If mode == P_WAIT return the process's exit code if it exits normally;
        otherwise return -SIG, where SIG is the signal that killed it.
    
    spawnvp(mode, file, args)
        spawnvp(mode, file, args) -> integer
        
        Execute file (which is looked for along $PATH) with arguments from
        args in a subprocess.
        If mode == P_NOWAIT return the pid of the process.
        If mode == P_WAIT return the process's exit code if it exits normally;
        otherwise return -SIG, where SIG is the signal that killed it.
    
    spawnvpe(mode, file, args, env)
        spawnvpe(mode, file, args, env) -> integer
        
        Execute file (which is looked for along $PATH) with arguments from
        args in a subprocess with the supplied environment.
        If mode == P_NOWAIT return the pid of the process.
        If mode == P_WAIT return the process's exit code if it exits normally;
        otherwise return -SIG, where SIG is the signal that killed it.
    
    stat(path, *, dir_fd=None, follow_symlinks=True)
        Perform a stat system call on the given path.
        
          path
            Path to be examined; can be string, bytes, a path-like object or
            open-file-descriptor int.
          dir_fd
            If not None, it should be a file descriptor open to a directory,
            and path should be a relative string; path will then be relative to
            that directory.
          follow_symlinks
            If False, and the last element of the path is a symbolic link,
            stat will examine the symbolic link itself instead of the file
            the link points to.
        
        dir_fd and follow_symlinks may not be implemented
          on your platform.  If they are unavailable, using them will raise a
          NotImplementedError.
        
        It's an error to use dir_fd or follow_symlinks when specifying path as
          an open file descriptor.
    
    statvfs(path)
        Perform a statvfs system call on the given path.
        
        path may always be specified as a string.
        On some platforms, path may also be specified as an open file descriptor.
          If this functionality is unavailable, using it raises an exception.
    
    strerror(code, /)
        Translate an error code to a message string.
    
    symlink(src, dst, target_is_directory=False, *, dir_fd=None)
        Create a symbolic link pointing to src named dst.
        
        target_is_directory is required on Windows if the target is to be
          interpreted as a directory.  (On Windows, symlink requires
          Windows 6.0 or greater, and raises a NotImplementedError otherwise.)
          target_is_directory is ignored on non-Windows platforms.
        
        If dir_fd is not None, it should be a file descriptor open to a directory,
          and path should be relative; path will then be relative to that directory.
        dir_fd may not be implemented on your platform.
          If it is unavailable, using it will raise a NotImplementedError.
    
    sync()
        Force write of everything to disk.
    
    sysconf(name, /)
        Return an integer-valued system configuration variable.
    
    system(command)
        Execute the command in a subshell.
    
    tcgetpgrp(fd, /)
        Return the process group associated with the terminal specified by fd.
    
    tcsetpgrp(fd, pgid, /)
        Set the process group associated with the terminal specified by fd.
    
    times()
        Return a collection containing process timing information.
        
        The object returned behaves like a named tuple with these fields:
          (utime, stime, cutime, cstime, elapsed_time)
        All fields are floating point numbers.
    
    truncate(path, length)
        Truncate a file, specified by path, to a specific length.
        
        On some platforms, path may also be specified as an open file descriptor.
          If this functionality is unavailable, using it raises an exception.
    
    ttyname(fd, /)
        Return the name of the terminal device connected to 'fd'.
        
        fd
          Integer file descriptor handle.
    
    umask(mask, /)
        Set the current numeric umask and return the previous umask.
    
    uname()
        Return an object identifying the current operating system.
        
        The object behaves like a named tuple with the following fields:
          (sysname, nodename, release, version, machine)
    
    unlink(path, *, dir_fd=None)
        Remove a file (same as remove()).
        
        If dir_fd is not None, it should be a file descriptor open to a directory,
          and path should be relative; path will then be relative to that directory.
        dir_fd may not be implemented on your platform.
          If it is unavailable, using it will raise a NotImplementedError.
    
    unsetenv(name, /)
        Delete an environment variable.
    
    urandom(size, /)
        Return a bytes object containing random bytes suitable for cryptographic use.
    
    utime(path, times=None, *, ns=None, dir_fd=None, follow_symlinks=True)
        Set the access and modified time of path.
        
        path may always be specified as a string.
        On some platforms, path may also be specified as an open file descriptor.
          If this functionality is unavailable, using it raises an exception.
        
        If times is not None, it must be a tuple (atime, mtime);
            atime and mtime should be expressed as float seconds since the epoch.
        If ns is specified, it must be a tuple (atime_ns, mtime_ns);
            atime_ns and mtime_ns should be expressed as integer nanoseconds
            since the epoch.
        If times is None and ns is unspecified, utime uses the current time.
        Specifying tuples for both times and ns is an error.
        
        If dir_fd is not None, it should be a file descriptor open to a directory,
          and path should be relative; path will then be relative to that directory.
        If follow_symlinks is False, and the last element of the path is a symbolic
          link, utime will modify the symbolic link itself instead of the file the
          link points to.
        It is an error to use dir_fd or follow_symlinks when specifying path
          as an open file descriptor.
        dir_fd and follow_symlinks may not be available on your platform.
          If they are unavailable, using them will raise a NotImplementedError.
    
    wait()
        Wait for completion of a child process.
        
        Returns a tuple of information about the child process:
            (pid, status)
    
    wait3(options)
        Wait for completion of a child process.
        
        Returns a tuple of information about the child process:
          (pid, status, rusage)
    
    wait4(pid, options)
        Wait for completion of a specific child process.
        
        Returns a tuple of information about the child process:
          (pid, status, rusage)
    
    waitpid(pid, options, /)
        Wait for completion of a given child process.
        
        Returns a tuple of information regarding the child process:
            (pid, status)
        
        The options argument is ignored on Windows.
    
    walk(top, topdown=True, onerror=None, followlinks=False)
    
    sched_get_priority_min(policy)
        Get the minimum scheduling priority for policy.
    
    sched_yield()
        Voluntarily relinquish the CPU.
    
    sendfile(...)
        sendfile(out, in, offset, count) -> byteswritten
        sendfile(out, in, offset, count[, headers][, trailers], flags=0)
                    -> byteswritten
        Copy count bytes from file descriptor in to file descriptor out.
    
    set_blocking(...)
        set_blocking(fd, blocking)
        
        Set the blocking mode of the specified file descriptor.
        Set the O_NONBLOCK flag if blocking is False,
        clear the O_NONBLOCK flag otherwise.
    
    set_inheritable(fd, inheritable, /)
        Set the inheritable flag of the specified file descriptor.
    
    setegid(egid, /)
        Set the current process's effective group id.
    
    seteuid(euid, /)
        Set the current process's effective user id.
    
    setgid(gid, /)
        Set the current process's group id.
    
    setgroups(groups, /)
        Set the groups of the current process to list.
    
    setpgid(pid, pgrp, /)
        Call the system call setpgid(pid, pgrp).
    
    setpgrp()
        Make the current process the leader of its process group.
    
    setpriority(which, who, priority)
        Set program scheduling priority.
    
    setregid(rgid, egid, /)
        Set the current process's real and effective group ids.
    
    setreuid(ruid, euid, /)
        Set the current process's real and effective user ids.
    
    setsid()
        Call the system call setsid().
    
    setuid(uid, /)
        Set the current process's user id.
    
    spawnl(mode, file, *args)
        spawnl(mode, file, *args) -> integer
        
        Execute file with arguments from args in a subprocess.
        If mode == P_NOWAIT return the pid of the process.
        If mode == P_WAIT return the process's exit code if it exits normally;
        otherwise return -SIG, where SIG is the signal that killed it.
    
    spawnle(mode, file, *args)
        spawnle(mode, file, *args, env) -> integer
        
        Execute file with arguments from args in a subprocess with the
        supplied environment.
        If mode == P_NOWAIT return the pid of the process.
        If mode == P_WAIT return the process's exit code if it exits normally;
        otherwise return -SIG, where SIG is the signal that killed it.
    
    spawnlp(mode, file, *args)
        spawnlp(mode, file, *args) -> integer
        
        Execute file (which is looked for along $PATH) with arguments from
        args in a subprocess with the supplied environment.
        If mode == P_NOWAIT return the pid of the process.
        If mode == P_WAIT return the process's exit code if it exits normally;
        otherwise return -SIG, where SIG is the signal that killed it.
    
    spawnlpe(mode, file, *args)
        spawnlpe(mode, file, *args, env) -> integer
        
        Execute file (which is looked for along $PATH) with arguments from
        args in a subprocess with the supplied environment.
        If mode == P_NOWAIT return the pid of the process.
        If mode == P_WAIT return the process's exit code if it exits normally;
        otherwise return -SIG, where SIG is the signal that killed it.
    
    spawnv(mode, file, args)
        spawnv(mode, file, args) -> integer
        
        Execute file with arguments from args in a subprocess.
        If mode == P_NOWAIT return the pid of the process.
        If mode == P_WAIT return the process's exit code if it exits normally;
        otherwise return -SIG, where SIG is the signal that killed it.
    
    spawnve(mode, file, args, env)
        spawnve(mode, file, args, env) -> integer
        
        Execute file with arguments from args in a subprocess with the
        specified environment.
        If mode == P_NOWAIT return the pid of the process.
        If mode == P_WAIT return the process's exit code if it exits normally;
        otherwise return -SIG, where SIG is the signal that killed it.
    
    spawnvp(mode, file, args)
        spawnvp(mode, file, args) -> integer
        
        Execute file (which is looked for along $PATH) with arguments from
        args in a subprocess.
        If mode == P_NOWAIT return the pid of the process.
        If mode == P_WAIT return the process's exit code if it exits normally;
        otherwise return -SIG, where SIG is the signal that killed it.
    
    spawnvpe(mode, file, args, env)
        spawnvpe(mode, file, args, env) -> integer
        
        Execute file (which is looked for along $PATH) with arguments from
        args in a subprocess with the supplied environment.
        If mode == P_NOWAIT return the pid of the process.
        If mode == P_WAIT return the process's exit code if it exits normally;
        otherwise return -SIG, where SIG is the signal that killed it.
    
    stat(path, *, dir_fd=None, follow_symlinks=True)
        Perform a stat system call on the given path.
        
          path
            Path to be examined; can be string, bytes, a path-like object or
            open-file-descriptor int.
          dir_fd
            If not None, it should be a file descriptor open to a directory,
            and path should be a relative string; path will then be relative to
            that directory.
          follow_symlinks
            If False, and the last element of the path is a symbolic link,
            stat will examine the symbolic link itself instead of the file
            the link points to.
        
        dir_fd and follow_symlinks may not be implemented
          on your platform.  If they are unavailable, using them will raise a
          NotImplementedError.
        
        It's an error to use dir_fd or follow_symlinks when specifying path as
          an open file descriptor.
    
    statvfs(path)
        Perform a statvfs system call on the given path.
        
        path may always be specified as a string.
        On some platforms, path may also be specified as an open file descriptor.
          If this functionality is unavailable, using it raises an exception.
    
    strerror(code, /)
        Translate an error code to a message string.
    
    symlink(src, dst, target_is_directory=False, *, dir_fd=None)
        Create a symbolic link pointing to src named dst.
        
        target_is_directory is required on Windows if the target is to be
          interpreted as a directory.  (On Windows, symlink requires
          Windows 6.0 or greater, and raises a NotImplementedError otherwise.)
          target_is_directory is ignored on non-Windows platforms.
        
        If dir_fd is not None, it should be a file descriptor open to a directory,
          and path should be relative; path will then be relative to that directory.
        dir_fd may not be implemented on your platform.
          If it is unavailable, using it will raise a NotImplementedError.
    
    sync()
        Force write of everything to disk.
    
    sysconf(name, /)
        Return an integer-valued system configuration variable.
    
    system(command)
        Execute the command in a subshell.
    
    tcgetpgrp(fd, /)
        Return the process group associated with the terminal specified by fd.
    
    tcsetpgrp(fd, pgid, /)
        Set the process group associated with the terminal specified by fd.
    
    times()
        Return a collection containing process timing information.
        
        The object returned behaves like a named tuple with these fields:
          (utime, stime, cutime, cstime, elapsed_time)
        All fields are floating point numbers.
    
    truncate(path, length)
        Truncate a file, specified by path, to a specific length.
        
        On some platforms, path may also be specified as an open file descriptor.
          If this functionality is unavailable, using it raises an exception.
    
    ttyname(fd, /)
        Return the name of the terminal device connected to 'fd'.
        
        fd
          Integer file descriptor handle.
    
    umask(mask, /)
        Set the current numeric umask and return the previous umask.
    
    uname()
        Return an object identifying the current operating system.
        
        The object behaves like a named tuple with the following fields:
          (sysname, nodename, release, version, machine)
    
    unlink(path, *, dir_fd=None)
        Remove a file (same as remove()).
        
        If dir_fd is not None, it should be a file descriptor open to a directory,
          and path should be relative; path will then be relative to that directory.
        dir_fd may not be implemented on your platform.
          If it is unavailable, using it will raise a NotImplementedError.
    
    unsetenv(name, /)
        Delete an environment variable.
    
    urandom(size, /)
        Return a bytes object containing random bytes suitable for cryptographic use.
    
    utime(path, times=None, *, ns=None, dir_fd=None, follow_symlinks=True)
        Set the access and modified time of path.
        
        path may always be specified as a string.
        On some platforms, path may also be specified as an open file descriptor.
          If this functionality is unavailable, using it raises an exception.
        
        If times is not None, it must be a tuple (atime, mtime);
            atime and mtime should be expressed as float seconds since the epoch.
        If ns is specified, it must be a tuple (atime_ns, mtime_ns);
            atime_ns and mtime_ns should be expressed as integer nanoseconds
            since the epoch.
        If times is None and ns is unspecified, utime uses the current time.
        Specifying tuples for both times and ns is an error.
        
        If dir_fd is not None, it should be a file descriptor open to a directory,
          and path should be relative; path will then be relative to that directory.
        If follow_symlinks is False, and the last element of the path is a symbolic
          link, utime will modify the symbolic link itself instead of the file the
          link points to.
        It is an error to use dir_fd or follow_symlinks when specifying path
          as an open file descriptor.
        dir_fd and follow_symlinks may not be available on your platform.
          If they are unavailable, using them will raise a NotImplementedError.
    
    wait()
        Wait for completion of a child process.
        
        Returns a tuple of information about the child process:
            (pid, status)
    
    wait3(options)
        Wait for completion of a child process.
        
        Returns a tuple of information about the child process:
          (pid, status, rusage)
    
    wait4(pid, options)
        Wait for completion of a specific child process.
        
        Returns a tuple of information about the child process:
          (pid, status, rusage)
    
    waitpid(pid, options, /)
        Wait for completion of a given child process.
        
        Returns a tuple of information regarding the child process:
            (pid, status)
        
        The options argument is ignored on Windows.
    
    walk(top, topdown=True, onerror=None, followlinks=False)
        Directory tree generator.
        
        For each directory in the directory tree rooted at top (including top
        itself, but excluding '.' and '..'), yields a 3-tuple
        
            dirpath, dirnames, filenames
        
        dirpath is a string, the path to the directory.  dirnames is a list of
        the names of the subdirectories in dirpath (excluding '.' and '..').
        filenames is a list of the names of the non-directory files in dirpath.
        Note that the names in the lists are just names, with no path components.
        To get a full path (which begins with top) to a file or directory in
        dirpath, do os.path.join(dirpath, name).
        
        If optional arg 'topdown' is true or not specified, the triple for a
        directory is generated before the triples for any of its subdirectories
        (directories are generated top down).  If topdown is false, the triple
        for a directory is generated after the triples for all of its
        subdirectories (directories are generated bottom up).
        
        When topdown is true, the caller can modify the dirnames list in-place
        (e.g., via del or slice assignment), and walk will only recurse into the
        subdirectories whose names remain in dirnames; this can be used to prune the
        search, or to impose a specific order of visiting.  Modifying dirnames when
        topdown is false is ineffective, since the directories in dirnames have
        already been generated by the time dirnames itself is generated. No matter
        the value of topdown, the list of subdirectories is retrieved before the
        tuples for the directory and its subdirectories are generated.
        
        By default errors from the os.scandir() call are ignored.  If
        optional arg 'onerror' is specified, it should be a function; it
        will be called with one argument, an OSError instance.  It can
        report the error to continue with the walk, or raise the exception
        to abort the walk.  Note that the filename is available as the
        filename attribute of the exception object.
        
        By default, os.walk does not follow symbolic links to subdirectories on
        systems that support them.  In order to get this functionality, set the
        optional argument 'followlinks' to true.
        
        Caution:  if you pass a relative pathname for top, don't change the
        current working directory between resumptions of walk.  walk never
        changes the current directory, and assumes that the client doesn't
        either.
        
        Example:
        
        import os
        from os.path import join, getsize
        for root, dirs, files in os.walk('python/Lib/email'):
            print(root, "consumes", end="")
            print(sum([getsize(join(root, name)) for name in files]), end="")
            print("bytes in", len(files), "non-directory files")
            if 'CVS' in dirs:
                dirs.remove('CVS')  # don't visit CVS directories
    
    write(fd, data, /)
        Write a bytes object to a file descriptor.
    
    writev(fd, buffers, /)
        Iterate over buffers, and write the contents of each to a file descriptor.
        
        Returns the total number of bytes written.
        buffers must be a sequence of bytes-like objects.
```

### DATA
```
    CLD_CONTINUED = 6
    CLD_DUMPED = 3
    CLD_EXITED = 1
    CLD_TRAPPED = 4
    EX_CANTCREAT = 73
    EX_CONFIG = 78
    EX_DATAERR = 65
    EX_IOERR = 74
    EX_NOHOST = 68
    EX_NOINPUT = 66
    EX_NOPERM = 77
    EX_NOUSER = 67
    EX_OK = 0
    EX_OSERR = 71
    EX_OSFILE = 72
    EX_PROTOCOL = 76
    EX_SOFTWARE = 70
    EX_TEMPFAIL = 75
    EX_UNAVAILABLE = 69
    EX_USAGE = 64
    F_LOCK = 1
    F_OK = 0
    F_TEST = 3
    F_TLOCK = 2
    F_ULOCK = 0
    NGROUPS_MAX = 16
    O_ACCMODE = 3
    O_APPEND = 8
    O_ASYNC = 64
    O_CLOEXEC = 16777216
    O_CREAT = 512
    O_DIRECTORY = 1048576
    O_DSYNC = 4194304
    O_EXCL = 2048
    O_EXLOCK = 32
    O_NDELAY = 4
    O_NOCTTY = 131072
    O_NOFOLLOW = 256
    O_NONBLOCK = 4
    O_RDONLY = 0
    O_RDWR = 2
    O_SHLOCK = 16
    O_SYNC = 128
    O_TRUNC = 1024
    O_WRONLY = 1
    PRIO_PGRP = 1
    PRIO_PROCESS = 0
    PRIO_USER = 2
    P_ALL = 0
    P_NOWAIT = 1
    P_NOWAITO = 1
    P_PGID = 2
    P_PID = 1
    P_WAIT = 0
    RTLD_GLOBAL = 8
    RTLD_LAZY = 1
    RTLD_LOCAL = 4
    RTLD_NODELETE = 128
    RTLD_NOLOAD = 16
    RTLD_NOW = 2
    R_OK = 4
    SCHED_FIFO = 4
    SCHED_OTHER = 1
    SCHED_RR = 2
    SEEK_CUR = 1
    SEEK_END = 2
    SEEK_SET = 0
    ST_NOSUID = 2
    ST_RDONLY = 1
    TMP_MAX = 308915776
    WCONTINUED = 16
    WEXITED = 4
    WNOHANG = 1
    WNOWAIT = 32
    WSTOPPED = 8
    WUNTRACED = 2
    W_OK = 2
    X_OK = 1
    __all__ = ['altsep', 'curdir', 'pardir', 'sep', 'pathsep', 'linesep', ...
    altsep = None
    confstr_names = {'CS_PATH': 1, 'CS_XBS5_ILP32_OFF32_CFLAGS': 20, 'CS_X...
    curdir = '.'
    defpath = ':/bin:/usr/bin'
    devnull = '/dev/null'
    environ = environ({'TERM_PROGRAM': 'Apple_Terminal', 'SHEL...e', '_': ...
    environb = environ({b'TERM_PROGRAM': b'Apple_Terminal', b'S..., b'_': ...
    extsep = '.'
    linesep = '\n'
    name = 'posix'
    pardir = '..'
    pathconf_names = {'PC_ALLOC_SIZE_MIN': 16, 'PC_ASYNC_IO': 17, 'PC_CHOW...
    pathsep = ':'
    sep = '/'
    supports_bytes_environ = True
    sysconf_names = {'SC_2_CHAR_TERM': 20, 'SC_2_C_BIND': 18, 'SC_2_C_DEV'...
```