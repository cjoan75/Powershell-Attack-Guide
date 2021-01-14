# Powershell-Attack-Guide
Powershell Attack guide-the way to penetrate after hackers

## Foreword
> After a long time, I will update the previous articles and re-understand and record some of the knowledge points. (2020-4-13) In addition, a more readable gitbook has been re-updated: https://rootclay.gitbook.io/powershell-attack-guide/

> This article first appeared on the security guest, the original topic page:https://www.anquanke.com/subject/id/90541

> I have been studying Powershell for a period of time. Later, in response to my friends' needs for Powershell, I asked me to write an article on the introduction or introduction of Powershell security, so this article appeared. But it was delayed due to various things, and at the same time the author's writing was not good, and the article may have some irregularities. Please excuse me. Here are some summaries to let newcomers have a general understanding of this, and have a better understanding of Powershell or intranet.

> So before we start, let's think about a common problem of powershell. Then we know that the suffix of powershell is ps1. Why is it ps1 instead of ps2, ps3? So to understand this problem, we can look at the characteristics of powershell, powershell is fully compatible with the next, that is to say you use powershell 5.x version to execute powershell v1.0 code is also completely no problem. Well, I personally understand why it is ps1. It can be said that when we see the suffix of ps2, powershell is undergoing a major update, that is, when it is not compatible with the next, so the suffix of ps1 is always used here.


> So what version do we use for our security personnel? There is no doubt that it is v2. Why? It should be that v2 is installed by default in win7, and the later versions are compatible with v2. All the functions of v1 version can not hide many of our needs, so v2 has become our current For a unique choice, we can see the version of our powershell and some detailed information in the following way. Most of our code behind is discussed in v2.0. (After the latest modification, some functions may use the latest Powershell7.0)



The current PS version information can be obtained through the command `Get-Host`

```powershell
Name             : ConsoleHost
Version          : 2.0
InstanceId       : 388599a6-35cd-4bba-bedb-cf00d2a39389
UI               : System.Management.Automation.Internal.Host.InternalHostUserInterface
CurrentCulture   : zh-CN
CurrentUICulture : en-US
PrivateData      : Microsoft.PowerShell.ConsoleHost+ConsoleColorProxy
IsRunspacePushed : False
Runspace         : System.Management.Automation.Runspaces.LocalRunspace
``` 
There are mainly the following two scenarios for security personnel to learn ps:

1. In the first type, we need to obtain anti-kill or better covertly attack the opponent's win machine, and we can directly execute commands through phishing and other methods.
2. The second type is that we have already reached the other party's network, and no matter how bad it is, it is also a DMZ win-server, so what we use ps to do naturally is to continue to deepen the intranet.

Then this powershell series mainly involves content related to security testing, so the readers are mainly security or operation and maintenance personnel. No matter what role you play in the network world, you should be able to get what you want here. The article mainly contains the following content:

1. Powershell basic syntax
2. Powershell script writing and call execution
3. Powershell Socket programming
4. Powershell port scanning and service blasting
5. Powershell multithreading
6. Powershell operation wmi and .net
7. Powershell operation win32API
8. Powershell operation Dll injection & shellcode injection & exe injection
9. Powershell confusion
10. powershell event log
11. Powershell instance usage scenarios
12. Powershell penetration tool set
