---
title: "Diagnosticar problemas de conexão com o Skype para o Business Connector Online"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: "Solucionar problemas de criação de uma sessão PowerShell remota para se conectar ao Skype para negócios Online, incluindo Import-Module, shell simultânea, Live ID e erros de permissão."
ms.openlocfilehash: 779786e073cf4ac420d75780472f8d45d67b292a
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/27/2018
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnosticar problemas de conexão com o Skype para o Business Connector Online

Este tópico fornece informações que ajudarão você a diagnosticar e resolver problemas que podem ocorrer quando você tentar criar uma sessão remota do Microsoft PowerShell que se conecta ao Skype para negócios Online. Consulte as seções a seguir:
  
- [Erro de import-Module causado pela diretiva de execução do Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Erro de import-Module causado por uma versão incorreta do Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Falha na conexão com o Live ID Server](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Falha ao carregar o módulo do Live ID](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Falha para o usuário de logon](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [O usuário não tem permissão para gerenciar este locatário](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [Capacidade de se conectar ao locatário foi desabilitada no Skype para Business Online](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [O número máximo de shells simultâneos para este usuário no Skype para Business Online foi excedido](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKMaxNumberShellsUser)
    
- [O número máximo de shells simultâneos para este locatário do Skype para Business Online foi excedido](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Erro de import-Module causado pela diretiva de execução do Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

A diretiva de execução do PowerShell ajuda a determinar quais arquivos de configuração podem ser carregados no console do PowerShell e qual scripts que um usuário pode executar a partir desse console. No mínimo, o Skype para módulo Business Connector Online não pode ser importado, a menos que a diretiva de execução tiver sido definida como RemoteSigned. Se não tiver sido, então você receberá a seguinte mensagem de erro quando você tenta importar o módulo:
  
- **Erro**: *Import-Module: c: o arquivo\\Program Files\\arquivos comuns\\Microsoft Lync Server 2013\\módulos\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 não pode ser carregado, porque em execução scripts está desativado neste sistema. Para obter mais informações, consulte about_Execution_Policies em https://go.microsoft.com/fwlink/?LinkID=135170.*

- **Resolução** Para resolver esse problema, inicie o PowerShell como administrador e, em seguida, execute o seguinte comando:
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
    Para obter detalhes sobre a diretiva de execução, consulte [Sobre políticas de execução](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Erro de import-Module causado por uma versão incorreta do Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

O Skype para módulo Business Connector Online pode ser executado somente em Windows PowerShell 3.0. Se você tentar importar o módulo em uma versão anterior do PowerShell, o processo de importação falhará com uma mensagem de erro semelhante a esta:
  
  - **Erro**: *Import-Module: A versão do PowerShell carregado é '2.0'. O módulo ' D:\\Program Files\\arquivos comuns\\Microsoft Lync Server 2013\\módulos\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requer uma versão mínima do PowerShell do 3.0 para executar. Verifique se a instalação do PowerShell e tente novamente.*

- **Resolução**: A única maneira de corrigir o problema é instalar o Windows PowerShell 3.0, que está disponível no Microsoft Download Center em [https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595).
  
## <a name="failed-to-connect-to-live-id-server"></a>Falha na conexão com o Live ID Server
<a name="BKMKFailedConnect"> </a>

Geralmente, há três razões sua tentativa de conexão falhar com a seguinte mensagem de erro:

  - **Erro**: *Get-CsWebTicket: Falha ao conectar servidores live id. Certifique-se de proxy está habilitada ou máquina tem conexão de rede para servidores de id de live.*

- **Resolução**: frequentemente este erro indica que o Assistente de entrada do Microsoft Online Services não está funcionando. Você pode verificar o status deste serviço executando o seguinte comando no prompt do PowerShell: 
    ```
    Get-Service "msoidsvc"
    ```
    Se o serviço não estiver em execução, inicie o serviço usando este comando:
    ```
    Start-Service "msoidsvc"
    ```

    Se estiver executando o serviço, você pode ser encontrando problemas com a conexão de rede entre o computador e o servidor de autenticação do Microsoft Live ID. Para verificar isso, abra o Internet Explorer e navegue até [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Tente fazer logon no Office 365, a partir daí. Se isso falhar, você provavelmente está tendo problemas de conexão de rede.
  
    Menos comumente, é possível que o URI de Conexão para o servidor de autenticação do Microsoft Live ID foi configurado para o valor errado. Se você já tiver determinado que o Assistente de conexão está em execução e que você não estiver tendo problemas de conectividade de rede, mas isso pode ser o problema. Nesse caso, contate o suporte do Office 365.
  
## <a name="failed-to-load-live-id-module"></a>Falha ao carregar o módulo do Live ID
<a name="BKMKFailedLoad"> </a>

Um dos pré-requisitos para usar o PowerShell para gerenciar Skype para Business Online é instalar o Assistente de entrada do Microsoft Online Services. Se o Assistente de conexão não estiver instalado, você receberá a seguinte mensagem de erro ao tentar estabelecer uma sessão remota com Skype para Business Online:

- **Erro**: *Get-CsWebTicket: não é possível carregar o módulo do Live Id. Tornar claro que correto de versão do Live Id Assistente de entrada estiver instalada.*

- **Resolução**: Assistente de conexão do Microsoft Online Services está disponível no Microsoft Download Center em [Assistente Microsoft Online Services entrar para RTW de profissionais de TI](https://www.microsoft.com/en-us/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Falha para o usuário de logon
<a name="BKMKLogonFailed"> </a>

Quando você tenta fazer uma conexão remota Skype para Business Online, você deve fornecer o nome de usuário e a senha de um Skype válido para a conta de usuário Business Online. Se você não fizer isso, o logon falhará, juntamente com uma mensagem de erro semelhante a esta:

- **Erro**: *Get-CsWebTicket: falha no Logon do usuário 'kenmyer@litwareinc.com'. Crie um novo objeto PSCredential, certificando-se de que você usou o nome correto do usuário e a senha.*

- **Resolução**: se você acha que você está usando uma conta de usuário válido e que você tem a senha correta, tente fazer logon novamente. Se isso falhar, use as mesmas credenciais e tente fazer logon no [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Se você não conseguir fazer logon lá, contate o suporte do Office 365. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>O usuário não tem permissão para gerenciar este locatário
<a name="BKMKUserPermission"> </a>

Você não pode fazer uma toSkype de conexão do PowerShell remoto para Business Online, a menos que você é um membro do grupo Administradores de Inquilino. Se ainda não estiver, sua tentativa de conexão irá falhar e você receberá a seguinte mensagem de erro:

- **Erro**: *New-PSSession: [admin.vdomain.com] dados de processamento de servidor remoto admin.vdomain.com falhou com a seguinte mensagem de erro: O usuário 'user@foo.com' não tem permissão para gerenciar este locatário. Podem ser concedidas, atribuindo o usuário à função de RBAC apropriada. Para obter mais informações, consulte a [Solução de problemas remota](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Resolução**: se você achar que você está ou deveria para estar, um membro do grupo Administradores de Inquilino, você precisará contatar o suporte do Office 365.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>Capacidade de se conectar ao locatário foi desabilitada no Skype para Business Online
<a name="BKMKAbilityConnect"> </a>

Para usar o PowerShell para gerenciar Skype para Business Online, a propriedade de EnableRemotePowerShellAccess do seu locatário do PowerShell diretiva deve ser definida como `True`. Se não for, sua conexão irá falhar e você receberá a seguinte mensagem de erro:

- **Erro**: *New-PSSession: [admin.vdomain.com] dados de processamento de servidor remoto admin.vdomain.com falhou com a seguinte mensagem de erro: A capacidade de se conectar a este locatário usando uma sessão PowerShell remota tiver sido desativada. Entre em contato com a Ajuda do Lync para verificar a diretiva de locatário do Powershell deste locatário. Para obter mais informações, consulte a [Solução de problemas remota](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Resolução**: se você vir essa mensagem de erro, você precisará contatar o suporte do Office 365 e obtenha acesso remoto do PowerShell habilitado.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>O número máximo de shells simultâneos para este usuário no Skype para Business Online foi excedido
<a name="BKMKMaxNumberShellsUser"> </a>

Cada administrador é permitido um máximo de três conexões remotas simultâneas para Skype para negócios Online. Se você tem três conexões remotas do PowerShell para cima e funcionando, qualquer tentativa de fazer uma quarta simultâneas conexão falhará, com a seguinte mensagem de erro:

- **Erro**: *New-PSSession: [admin.vdomain.com] conectando-se ao servidor remoto admin.vdomain.com falhou com a seguinte mensagem de erro: serviço o WS-Management não pode processar a solicitação. O número máximo de shells simultâneos para esse usuário foi excedido. Feche shells existentes ou aumentar a cota para esse usuário. Para obter mais informações, consulte o [](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1* remoto de solução de problemas

- **Resolução**: A única maneira de solucionar esse problema é fechar uma ou mais das conexões anteriores. Quando você terminar com um Skype sessão Business Online, é recomendável que você use o cmdlet **Remove-PSSession** para encerrar a sessão. Isso ajudará você a evitar esse problema.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>O número máximo de shells simultâneos para este locatário do Skype para Business Online foi excedido
<a name="BKMKMaxNumberShellsTenant"> </a>

Embora cada administrador pode ter até três conexões simultâneas para um Skype para locatário Business Online, nenhuma inquilino único tem permissão para ter mais de nove conexões simultâneas. Por exemplo, três os administradores podem cada têm três sessões abertas. Se um quarto administrador tenta fazer uma conexão (resultando em um total de 10 conexões simultâneas), essa tentativa falhará, com a seguinte mensagem de erro:
  
- **Erro**: *New-PSSession: [admin.vdomain.com] conectando-se ao servidor remoto admin.vdomain.com falhou com a seguinte mensagem de erro: serviço o WS-Management não pode processar a solicitação. O número máximo de shells simultâneos para este locatário foi excedido. Feche shells existentes ou aumentar a cota para este locatário. Para obter mais informações, consulte o [](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1* remoto de solução de problemas

- **Resolução**: A única maneira de solucionar esse problema é fechar uma ou mais das conexões anteriores. Quando você terminar com um Skype sessão Business Online, é recomendável que você use o cmdlet **Remove-PSSession** para encerrar a sessão. Isso ajudará você a evitar esse problema.  
 
## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador e Skype para gerenciamento online de negócios usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

## <a name="feedback"></a>Comentários?
Para fornecer comentários sobre o produto ou para saber como estamos indo, consulte [Skype para comentários de negócios](https://www.skypefeedback.com).
