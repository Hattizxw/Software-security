## Definition of Memory Forensics

> Memory forensics (sometimes referred to as memory analysis) refers to the analysis of volatile data in a computer’s memory dump. Information security professionals conduct memory forensics to investigate and identify attacks or malicious behaviors that do not leave easily detectable tracks on hard drive data.

内存取证（有时称为内存分析）是指对计算机内存转储中的**易失性数据的分析**。信息安全专业人员进行**内存取证**，以调查和识别不会在硬盘数据上留下不易检测到的痕迹的攻击或恶意行为。

# What is Volatile Data?

> Volatile data is the data stored in temporary memory on a computer while it is running. When a computer is powered off, volatile data is lost almost immediately. Volatile data resides in a computer’s short term memory storage and can include data like browsing history, chat messages, and clipboard contents. If, for example, you were working on a document in Word or Pages that you had not yet saved to your hard drive or another non-volatile memory source, then you would lose your work if your computer lost power before it was saved.

易失性数据是计算机运行时存储在**临时存储器中的数据**。当计算机断电时，易失性数据几乎立即丢失。易失性数据驻留在计算机的短期内存存储中，可以包括浏览历史、聊天消息和剪贴板内容等数据。例如，如果您正在处理Word或Pages中尚未保存到硬盘驱动器或其他非易失性内存源的文档，那么如果计算机在保存之前断电，您将失去工作。

# The Importance of Memory Forensics

> [Memory forensics](https://www.memoryanalysis.net/memory-forensics-training) can provide unique insights into runtime system activity, including open network connections and recently executed commands or processes. In many cases, critical data pertaining to attacks or threats will exist solely in system memory – examples include network connections, account credentials, chat messages, encryption keys, running processes, injected code fragments, and internet history which is non-cacheable. Any program – malicious or otherwise – must be loaded in memory in order to execute, making memory forensics critical for identifying otherwise obfuscated attacks.
>
> As attack methods become increasingly sophisticated, memory forensics tools and skills are in high demand for security professionals today. Many network-based security solutions like firewalls and antivirus tools are unable to detect malware written directly into a computer’s physical memory or RAM. Security teams should look to memory forensics tools and specialists to protect invaluable business intelligence and data from stealthy attacks such as fileless, [in-memory malware](https://arstechnica.com/security/2017/02/a-rash-of-invisible-fileless-malware-is-infecting-banks-around-the-globe/) or [RAM scrapers](https://www.wired.com/2014/09/ram-scrapers-how-they-work/).

内存取证可以提供对运行时系统活动的独特见解，包括开放的网络连接和最近执行的命令或进程。在许多情况下，与攻击或威胁相关的关键数据将仅存在于系统内存中，例如网络连接、帐户凭据、聊天消息、加密密钥、运行进程、注入的代码片段以及不可缓存的互联网历史。任何程序——无论是恶意程序还是其他程序——都必须加载到内存中才能执行，这使得内存取证对于识别其他混淆的攻击至关重要。

随着攻击方法越来越复杂，当今安全专业人员对内存取证工具和技能的需求越来越高。许多基于网络的安全解决方案，如防火墙和防病毒工具，都无法检测直接写入计算机物理内存或RAM的恶意软件。安全团队应寻求内存取证工具和专家，以保护宝贵的商业智能和数据免受诸如无文件、内存中恶意软件或RAM刮刀等秘密攻击。

Memory forensics是数字取证的一个重要分支，它关注在计算机系统的内存中发现和分析数字取证证据。相对于传统的磁盘取证，**内存取证具有以下几个优点：**

- 实时性：内存中的数据是瞬时存在的，一旦计算机关闭或重启，数据就会消失。因此，内存取证能够获取到最新的数据，而磁盘取证则可能无法获取最新的数据。
- 2 不易被篡改：内存中的数据难以被篡改，因为它们处于计算机的活动状态，而且常常是受到操作系统保护的。相比之下，磁盘上的数据可能会被修改、删除或覆盖。
- 3 宽泛的取证范围：内存中包含着计算机系统的所有数据和活动，比如进程、线程、网络连接、注册表键值、密码和加密密钥等，这些都是磁盘取证难以获取到的。

因此，内存取证已成为数字取证中不可或缺的一部分，可以帮助取证人员获取更全面和精确的证据，提高数字取证的效率和准确性。

# 内存取证工具主要有以下几个作用： 

内存取证工具主要有以下几个作用：
 1 内存提取：内存取证工具可以从运行中的计算机系统中提取内存映像，这个过程可以通过工具的命令行、图形界面或者脚本来完成。内存提取是内存取证的第一步，是获取内存数据的基础。
 2 内存分析：内存取证工具可以对内存映像进行分析，并提取出其中的进程、线程、网络连接、注册表键值、加密密钥等信息。内存分析需要使用工具的分析功能，通常需要提供一些参数和选项来确定分析的范围和目标。
 3 内存可视化：内存取证工具可以通过可视化的方式呈现内存数据，包括进程树、网络连接图、内存映像、数据结构等。可视化可以帮助取证人员更好地理解内存数据，并发现隐藏的信息。
 4 内存比对：内存取证工具可以对不同时间或不同系统的内存映像进行比对，以检测是否有数据被修改或篡改。比对是内存取证的重要手段之一，可以帮助取证人员发现不同版本的内存数据之间的差异。
 5 内存恢复：内存取证工具可以恢复被删除的进程、线程、文件等信息，以及恢复加密的数据和密码。内存恢复需要工具具备一定的逆向分析能力，以便能够恢复加密的数据和密码。
总之，内存取证工具是内存取证过程中不可或缺的工具，它们可以帮助取证人员获取证据、分析数据、恢复信息，并提高内存取证的效率和准确性。