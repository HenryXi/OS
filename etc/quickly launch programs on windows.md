# Quick launch programs(start service) on windows

When you want launch a programs on windows open directory and find the ``exe`` file then double click it.
It is too slow. Today I will show you how to open programs or start service on windows quickly. You do not 
need open deep directory to find ``exe`` file. 

1. Add a shortcut directory in your environment.

    Let's make a directory(like D:\shortcut) as shortcut. Right click ``My computer`` -> ``Property`` -> 
    ``Advanced system settings`` -> ``Environment variables``. Find ``Path`` in ``System variables`` add your
     shortcut directory in the end. In my computer like following
     ```
     .\;C:\Program Files (x86)\NVIDIA Corporation\PhysX\Common;%SystemRoot%\system32;%SystemRoot%;%SystemRoot%\System32\Wbem;%SYSTEMROOT%\System32\WindowsPowerShell\v1.0\;%JAVA_HOME%\bin;D:\shortcut
     ```
     
2. Create shortcut for your programs.

    If you want quickly launch a program(like IDEA) find the ``IDEA.exe`` in the install directory. Create a shortcut for it 
    and rename it what you like(I rename it as ``idea``). Move this shortcut to your shortcut directory(D:\shortcut).
 
3. Quickly launch the program.

    Press Windows+R, you can see ``Run`` windows then press ``idea`` -> Enter. Now the ``IDEA`` will start.
    
4. Quickly start(stop) a service.

    Let's make ``PostgreSQL`` as example. Find the service name in ``Service``(the name of ``PostgreSQL`` service in my computer
    is ``postgresql-x64-9.3``). Create a text file and add following.
    ```
    net stop "postgresql-x64-9.3" && net start "postgresql-x64-9.3"
    ```
    Save this file as ``pg.bat`` and move it to your shortcut directory. Now you can ``toggle`` this service as step 3. 
    Windows + R -> press ``pg`` -> Enter. Now the ``PostgreSQL`` service run. If you do this(Windows + R -> press ``pg`` 
    -> Enter) a second time the service will stop.
    