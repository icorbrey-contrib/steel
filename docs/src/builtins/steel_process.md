# steel/process

### **child-stderr**

Streams the child process's stderr.

```scheme
(child-stderr (spawn-process
  (command "cargo" '("insta" "review"))))
```

### **child-stdin**

Streams the child process's stdin.

```scheme
(child-stdin (spawn-process
  (command "cargo" '("insta" "review"))))
```

### **child-stdout**

Streams the child process's stdout.

```scheme
(child-stdout (spawn-process
  (command "cargo" '("insta" "review"))))
```

### **command**

Creates a command builder that references the given command and arguments.

```scheme
> (command "cargo" '("insta" "review")) ;; => CommandBuilder
```

### **kill**

Kills the given child process.

```scheme
(kill (spawn-process
  (command "cargo" '("insta" "review"))))
```

### **set-current-dir!**

Sets the working directory for the given command builder.

```scheme
(set-current-dir!
  (command "cargo" '("insta" "review"))
  "/home/user/dev/steel")
```

### **set-env-var!**

Configures an environment variable for the given command builder.

```scheme
(set-env-var!
  (command "git" '("rebase" "-i"))
  "EDITOR" "hx")
```

### **set-piped-stdout!**

Pipe the command builder's stdin, stdout, and stderr through the parent process.

```scheme
(set-piped-stdout
  (command "cargo" '("insta" "review")))
```

### **spawn-process**

Spawn the given command builder as a child process.

```scheme
(spawn-process
  (command "fsck" '()))
```

### **wait**

Blocks until the given child process is complete.

```scheme
(wait (spawn-process
  (command "fsck" '())))
```

### **wait->stdout**

Blocks until the given child process is complete, returning the process's
stdout.

```scheme
(wait->stdout (spawn-process
  (command "fsck" '())))
```

### **which**

Returns the path to the given binary by name, if it exists on `$PATH`.

```scheme
> (which "rustc") ;; => Ok("/usr/bin/rustc")
> (which "fake") ;; => None
```
