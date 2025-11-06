PS C:\> mkdir commands


    디렉터리: C:\


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:48                commands


PS C:\> pwd

Path
----
C:\


PS C:\> cd .\commands\
PS C:\commands> mkdir test


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:49                test


PS C:\commands> ls


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:49                test


PS C:\commands> mkdir Notes


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:50                Notes


PS C:\commands> ls


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:50                Notes
d-----      2025-11-06   오후 5:49                test


PS C:\commands> mkdir Images, Videos, Docs


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:51                Images
d-----      2025-11-06   오후 5:51                Videos
d-----      2025-11-06   오후 5:51                Docs


PS C:\commands> ls


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:51                Docs
d-----      2025-11-06   오후 5:51                Images
d-----      2025-11-06   오후 5:50                Notes
d-----      2025-11-06   오후 5:49                test
d-----      2025-11-06   오후 5:51                Videos


PS C:\commands> cd .\Docs\
PS C:\commands\Docs> cd ../
PS C:\commands> ls


    디렉터리: C:\commands


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2025-11-06   오후 5:51                Docs
d-----      2025-11-06   오후 5:51                Images
d-----      2025-11-06   오후 5:50                Notes
d-----      2025-11-06   오후 5:49                test
d-----      2025-11-06   오후 5:51                Videos