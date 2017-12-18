---
title: "Diagnosticar problemas de conexão com o Skype para Business Connector Online"
ms.author: tonysmit
author: tonysmit
ms.date: 5/17/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
description: "Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors."
---

# Diagnosticar problemas de conexão com o Skype para Business Connector Online

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Este tópico fornece informações que ajudarão você a diagnosticar e resolver problemas que podem ocorrer quando você tentar criar uma sessão remota Microsoft PowerShell que se conecta ao Skype for Business Online. Consulte as seções a seguir:
  
- [Erro de importação módulo causado por política de execução do Windows PowerShell](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_PowerShellExecutionPolicy)
    
- [Erro de importação módulo causado por versão incorreta do Windows PowerShell](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_IncorrectVersion)
    
- [Falha ao se conectar ao servidor de ID do Live](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_FailedConnect)
    
- [Falha ao carregar o módulo do Live ID](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_FailedLoad)
    
- [Logon falhou para o usuário](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_LogonFailed)
    
- [O usuário não tem permissão para gerenciar este locatário](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_UserPermission)
    
- [Capacidade de se conectar ao locatário foi desabilitada no Skype for Business Online](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_AbilityConnect)
    
- [O número máximo de conchas simultâneos para este usuário no Skype for Business Online foi excedido](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_MaxNumberShellsUser)
    
- [O número máximo de conchas simultâneos para este site principal no Skype for Business Online foi excedido](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_MaxNumberShellsTenant)
    
## Erro de importação módulo causado por política de execução do Windows PowerShell
<a name="BKMK_PowerShellExecutionPolicy"> </a>

A política de execução PowerShell ajuda a determinar quais arquivos de configuração podem ser carregados no console de PowerShell e qual scripts um usuário pode executar a partir desse console. No mínimo, o Módulo Conector do Skype for Business Online não pode ser importado, a menos que a política de execução foi definida como RemoteSigned. Se não tiver, em seguida, você receberá a seguinte mensagem de erro quando você tentar importar o módulo:
  
```
Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.
```

Para resolver esse problema, iniciar PowerShell como administrador e, em seguida, execute o seguinte comando:
  
```
Set-ExecutionPolicy RemoteSigned
```

Para obter detalhes sobre a política de execução, consulte [Sobre políticas de execução](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## Erro de importação módulo causado por versão incorreta do Windows PowerShell
<a name="BKMK_IncorrectVersion"> </a>

O Módulo Conector do Skype for Business Online pode ser executado apenas em Windows PowerShell 3.0. Se você tentar importar o módulo em uma versão anterior do PowerShell, o processo de importação falhará com uma mensagem de erro semelhante a esta:
  
```
Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.
```

A única maneira de corrigir esse problema é instalar Windows PowerShell 3.0, que está disponível na Centro de Download da Microsoft em [http://www.microsoft.com/en-us/download/details.aspx?id=29939](http://www.microsoft.com/en-us/download/details.aspx?id=29939).
  
## Falha ao se conectar ao servidor de ID do Live
<a name="BKMK_FailedConnect"> </a>

Normalmente, há três razões a tentativa de conexão falhar com a seguinte mensagem de erro:
  
```
Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.
```

Geralmente este erro significa que o Assistente de Conexão do Microsoft Online Services não está executando. Você pode verificar o status do serviço executando o seguinte comando no prompt de PowerShell:
  
```
Get-Service "msoidsvc"
```

Se o serviço não estiver executando, inicie o serviço usando este comando:
  
```
Start-Service "msoidsvc"
```

Se o serviço está em execução, você pode estar encontrando problemas com a conexão de rede entre seu computador e o servidor de autenticação do Microsoft Live ID. Para verificar isso, abra o Internet Explorer e navegue até [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Tente fazer logon Office 365 de lá. Se isso falhar, você provavelmente está enfrentando problemas de conexão de rede.
  
Menos comum, é possível que o URI de Conexão para Microsoft Live ID de autenticação do servidor tiver sido configurado para o valor errado. Se você já tiver determinado que o Assistente de entrada está sendo executado e que você não estiver enfrentando problemas de conectividade de rede, isso pode ser o problema. Nesse caso, contate Office 365 suporte.
  
## Falha ao carregar o módulo do Live ID
<a name="BKMK_FailedLoad"> </a>

Um dos pré-requisitos para usar PowerShell para gerenciar Skype for Business Online é instalar o Assistente de Conexão do Microsoft Online Services. Se o Assistente de conexão não estiver instalado, você receberá a seguinte mensagem de erro quando você tenta estabelecer uma sessão remota com Skype for Business Online:
  
```
Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.
```

O Assistente de Conexão do Microsoft Online Services está disponível na Centro de Download da Microsoft no [Assistente Microsoft Online Services entrar para RTW de profissionais de TI](https://www.microsoft.com/en-us/download/details.aspx?id=28177).
  
## Logon falhou para o usuário
<a name="BKMK_LogonFailed"> </a>

Quando você tenta fazer uma conexão remota para Skype for Business Online, você deve fornecer o nome de usuário e senha de uma conta de usuário válida Skype for Business Online. Se você não fizer isso, o logon falhará juntamente com uma mensagem de erro semelhante a esta:
  
```
Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.
```

Se você acha que você está usando uma conta de usuário válida e que você tem a senha correta, tente fazer logon novamente. Se isso falhar, use as mesmas credenciais e tente fazer logon em [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Se você não consegue fazer logon lá, contate Office 365 suporte.
  
## O usuário não tem permissão para gerenciar este locatário
<a name="BKMK_UserPermission"> </a>

Você não pode fazer uma conexão remota PowerShell paraSkype for Business Online, a menos que você é membro do grupo Administradores de locatários. Se você não estiver, sua tentativa de conexão falhará e você receberá a seguinte mensagem de erro:
  
```
New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the about_Remote_Troubleshooting Help topic.
```

Se você acha que estão ou devem para ser membro do grupo Administradores de locatários, você precisará contatar Office 365 suporte.
  
## Capacidade de se conectar ao locatário foi desabilitada no Skype for Business Online
<a name="BKMK_AbilityConnect"> </a>

Para usar PowerShell para gerenciar Skype for Business Online, a propriedade de EnableRemotePowerShellAccess da sua política de PowerShell locatário deve ser definida como  `True`. Se não for, sua conexão falhará e você receberá a seguinte mensagem de erro:
  
```
New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the about_Remote_Troubleshooting Help topic.
```

Se você vir essa mensagem de erro, você precisará contatar Office 365 suporte e obter acesso remoto PowerShell habilitado.
  
## O número máximo de conchas simultâneos para este usuário no Skype for Business Online foi excedido
<a name="BKMK_MaxNumberShellsUser"> </a>

Cada administrador é permitido um máximo de três conexões remotas simultâneas ao Skype for Business Online. Se você tiver conexões de três remoto PowerShell para cima e em execução, qualquer tentativa de tornar uma quarta simultâneo conexão falhará, com a seguinte mensagem de erro:
  
```
New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the about_Remote_Troubleshooting Help topic.
```

A única maneira de resolver esse problema é fechar um ou mais das conexões anterior. Quando tiver terminado com uma sessão de Skype for Business Online, recomendamos que você use o cmdlet **Remove-PSSession** para finalizar a sessão. Isso ajudará você a evitar esse problema.
  
## O número máximo de conchas simultâneos para este site principal no Skype for Business Online foi excedido
<a name="BKMK_MaxNumberShellsTenant"> </a>

Embora cada administrador pode ter até três conexões simultâneas com um locatário Skype for Business Online, sem locatário único tem permissão para ter mais de nove conexões simultâneas. Por exemplo, três os administradores podem cada têm três sessões abertas. Se um administrador de quarto tentar fazer uma conexão (resultando em um total de 10 conexões simultâneas), essa tentativa falhará, com a seguinte mensagem de erro:
  
```
New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the about_Remote_Troubleshooting Help topic.
```

A única maneira de resolver esse problema é fechar um ou mais das conexões anterior. Quando tiver terminado com uma sessão de Skype for Business Online, recomendamos que você usar o cmdlet **Remove-PSSession** para encerrar a sessão. Isso ajudará você a evitar esse problema.
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

