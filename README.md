# BlodyX-
BlodyX Rootkit is an LD_PRELOAD-based rootkit that hides files, establishes a reverse shell, and prevents debugging. It intercepts system calls to hide the rootkit from detection tools like ls, stat, and open



![3](https://github.com/user-attachments/assets/5377d57c-e2fe-404b-b920-95b4ae20742d)


Functions of these rootkit:

Anti-Debugging: Detects debugging attempts using ptrace. If debugging is detected, the rootkit terminates with a custom message, making it difficult to debug or analyze.

Reverse Shell: When bash or sh is executed, the rootkit establishes a connection to a remote server (here you should put ur ip) and creates a reverse shell, providing remote access to the attacker.

File Hiding: Prevents access to files such as /etc/ld.so.preload, making it harder to detect by blocking read, open, and stat system calls. Files with the rootkit's name (BlodyX.so) are hidden from directory listings.

Stealth: Filters out the rootkit from being listed in directories (via readdir) and prevents file access through open, stat, lstat, etc. This ensures it remains hidden from regular system operations.

Prevent lsof Detection: A future update will add protection against being listed by lsof, making the rootkit harder to detect by commonly used tools.
