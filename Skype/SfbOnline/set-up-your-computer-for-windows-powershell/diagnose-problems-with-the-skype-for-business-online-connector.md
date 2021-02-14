---
title: Diagnosticar problemas de conexão com o Conector do Skype for Business Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Solucionar problemas de criação de uma sessão remota do PowerShell para se conectar ao Skype for Business Online, incluindo o Módulo de Importação, o shell simultâneo, o Live ID e os erros de permissão.
ms.openlocfilehash: 019ef023b325227be046aae1e855573449453864
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "44204872"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnosticar problemas de conexão com o Conector do Skype for Business Online

Este tópico fornece informações que ajudarão você a diagnosticar e resolver problemas que podem ocorrer quando você tenta criar uma sessão remota do Microsoft PowerShell que se conecta ao Skype for Business Online. Confira as seções a seguir:
  
- [Erro de Módulo de Importação causado pela política de execução do Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Erro de Módulo de Importação causado pela versão incorreta do Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [A autenticação moderna falha quando a autenticação do WinRM Basic foi desabilitada](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [Falha ao se conectar ao Live ID Server](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Falha ao carregar o módulo Live ID](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Falha de logon para o usuário](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [O usuário não tem permissão para gerenciar este locatário](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [A capacidade de se conectar ao locatário foi desabilitada no Skype for Business Online](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [O número máximo de shells simultâneos para este usuário no Skype for Business Online foi excedido](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [O número máximo de shells simultâneos para este locatário no Skype for Business Online foi excedido](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> Por padrão, as sessões do PowerShell duram após 60 minutos. Para se reconectar, você precisa fechar a sessão e iniciar uma nova sessão do PowerShell. Uma nova versão do Skype for Business Online, módulo do [Windows PowerShell (2046.123 – Publicado em 02/10/2019)](https://www.microsoft.com/download/details.aspx?id=39366), foi lançada recentemente, que inclui um novo cmdlet chamado **Enable-CsOnlineSessionForReconnection** que reduz o problema de tempo de 60 minutos.
> A sessão do PowerShell se reconecta e autentica, permitindo que ela seja reativada sem precisar iniciar uma nova instância para se reconectar.



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Import-Module erro causado pela política de execução do Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

A política de execução do PowerShell ajuda a determinar quais arquivos de configuração podem ser carregados no console do PowerShell e quais scripts um usuário pode executar a partir desse console. No mínimo, o módulo Conector do Skype for Business Online não pode ser importado, a menos que a política de execução tenha sido definida como RemoteSigned. Caso não tenha, você receberá a seguinte mensagem de erro ao tentar importar o módulo:
  
- **Erro**: Módulo de Importação: Arquivo C: Arquivos de Programas Arquivos Comuns <em>do Microsoft \\ \\ \\ Lync Server 2013 \\ Modules \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1 não podem ser carregados porque a execução de scripts está desabilitada nesse sistema. Para obter mais informações, consulte about_Execution_Policies em https://go.microsoft.com/fwlink/?LinkID=135170 .</em>

- **Resolução** Para resolver esse problema, inicie o PowerShell como administrador e execute o seguinte comando:
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Para obter detalhes sobre a política de execução, consulte [Sobre Políticas de Execução.](https://go.microsoft.com/fwlink/?LinkID=135170)
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Import-Module erro causado pela versão incorreta do Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

O módulo Skype for Business Online Connector só pode ser executado no Windows PowerShell 3.0. Se você tentar importar o módulo em uma versão anterior do PowerShell, o processo de importação falhará com uma mensagem de erro semelhante a esta:
  
  - **Erro**: *Import-Module: A versão do PowerShell carregado é '2.0'. O módulo 'D: Arquivos comuns de programas Módulos do \\ \\ Microsoft \\ Lync Server 2013 \\ \\ LyncOnlineConnectorLyncOnlineConnector.psd1' requer uma versão mínima do \\ PowerShell de '3.0' para ser executada. Verifique a instalação do PowerShell e tente novamente.*

- **Resolução:** a única maneira de corrigir esse problema é instalar o Windows PowerShell 3.0, que está disponível no Centro de Download da Microsoft em [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) .
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>A autenticação moderna falha quando a autenticação do WinRM Basic foi desabilitada
<a name="BKMKWinRMBasicAuth"> </a>

A versão mais recente do módulo Skype for Business Online Connector usa autenticação moderna, mas o cliente windows remote management (WinRM) subjacente deve ser configurado para permitir a autenticação básica.  A autenticação moderna usa tokens de portador que geralmente são passados no *título Autorização:* Portador. O Windows PowerShell, no qual o PowerShell do Skype for Business foi criado, não permite a manipulação desse header.  Em vez disso, o PowerShell do Skype for Business usa a *Autorização:* o título básico para passar o token de portador.

Confira [Baixar e instalar o Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) para obter instruções sobre como habilitar o WinRM para autenticação básica.

## <a name="failed-to-connect-to-live-id-server"></a>Falha ao se conectar ao Live ID Server
<a name="BKMKFailedConnect"> </a>

Normalmente, há três motivos pelos quais a tentativa de conexão pode falhar com a seguinte mensagem de erro:

  - **Erro**: *Get-CsWebTicket: Falha ao conectar servidores live id. Certifique-se de que o proxy está habilitado ou se o computador tem conexão de rede com servidores live id.*

- **Resolução:** geralmente, esse erro significa que o Assistente de Acesso do Microsoft Online Services não está em execução. Você pode verificar o status deste serviço executando o seguinte comando no prompt do PowerShell: 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Se o serviço não estiver em execução, inicie o serviço usando este comando:
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Se o serviço estiver em execução, talvez você tenha problemas com a conexão de rede entre o computador e o Servidor de Autenticação do Microsoft Live ID. Para verificar isso, abra o Internet Explorer e navegue até [ https://login.microsoftonline.com/ .](https://login.microsoftonline.com/.) Tente entrar no Microsoft 365 ou no Office 365 a partir daí. Se isso falhar, você provavelmente está enfrentando problemas de conexão de rede.
  
    Menos comumente, é possível que o URI de conexão do Servidor de Autenticação do Microsoft Live ID tenha sido configurado para o valor errado. Se você já determinou que o Assistente de Sign-In está em execução e que não está enfrentando problemas de conectividade de rede, esse pode ser o problema. Nesse caso, entre em contato com o Suporte da Microsoft.
  
## <a name="failed-to-load-live-id-module"></a>Falha ao carregar o módulo Live ID
<a name="BKMKFailedLoad"> </a>

Um dos pré-requisitos para usar o PowerShell para gerenciar o Skype for Business Online é instalar o Assistente de Conexão do Microsoft Online Services. Se o Assistente de Logon não estiver instalado, você receberá a seguinte mensagem de erro quando tentar estabelecer uma sessão remota com o Skype for Business Online:

- **Erro:** *Get-CsWebTicket: não é possível carregar o módulo Live Id. Certifique-se de que a versão correta do assistente de entrada do Live Id está instalada.*

- **Resolução:** o Assistente de Acesso do Microsoft Online Services está disponível no Centro de Download da Microsoft no Assistente de Sign-In do Microsoft Online Services para Profissionais de TI [RTW](https://www.microsoft.com/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Falha de logon para o usuário
<a name="BKMKLogonFailed"> </a>

Ao tentar fazer uma conexão remota com o Skype for Business Online, você deve fornecer o nome de usuário e a senha de uma conta de usuário válida do Skype for Business Online. Caso não faça isso, o logon falhará juntamente com uma mensagem de erro semelhante a esta:

- **Erro**: *Get-CsWebTicket: falha na logon para o usuário "kenmyer@litwareinc.com". Crie um novo objeto PSCredential,* verifique se você usou o nome de usuário e a senha corretos.

- **Resolução:** se você acha que está usando uma conta de usuário válida e que tem a senha correta, tente fazer logo on novamente. Se isso falhar, use as mesmas credenciais e tente fazer logoff em [https://login.microsoftonline.com/](https://login.microsoftonline.com/) . Se você não conseguir fazer logoff, entre em contato com o Suporte da Microsoft. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>O usuário não tem permissão para gerenciar este locatário
<a name="BKMKUserPermission"> </a>

Não é possível fazer uma conexão remota do PowerShell com oSkype for Business Online, a menos que você seja membro do grupo Administradores de Locatários. Se não estiver, sua tentativa de conexão falhará e você receberá a seguinte mensagem de erro:

- **Erro**: New-PSSession : [admin.vdomain.com] O processamento de dados do servidor remoto admin.vdomain.com falhou com a seguinte mensagem de erro: O usuário "user@foo.com" não tem permissão para gerenciar esse *locatário. As permissões podem ser concedidas atribuindo ao usuário a função RBAC apropriada. Para obter mais informações, consulte a [Solução de Problemas Remota.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*

- **Resolução:** se você acha que é ou deveria ser um membro do grupo Administradores de Locatários, precisará entrar em contato com o Suporte da Microsoft.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>A capacidade de se conectar ao locatário foi desabilitada no Skype for Business Online
<a name="BKMKAbilityConnect"> </a>

Para usar o PowerShell para gerenciar o Skype for Business Online, a propriedade EnableRemotePowerShellAccess da política do PowerShell de locatário deve ser definida como  `True` . Se não estiver, sua conexão falhará e você receberá a seguinte mensagem de erro:

- **Erro**: New-PSSession : [admin.vdomain.com] O processamento de dados do servidor remoto admin.vdomain.com falhou com a seguinte mensagem de erro: A capacidade de se conectar a esse locatário usando uma sessão remota do PowerShell foi *desabilitada. Entre em contato com a Ajuda do Lync para verificar a Política do PowerShell do Locatário deste locatário. Para obter mais informações, consulte a [Solução de Problemas Remota.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*

- **Resolução:** se você vir essa mensagem de erro, precisará entrar em contato com o Suporte da Microsoft e habilitar o acesso remoto do PowerShell.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>O número máximo de shells simultâneos para este usuário no Skype for Business Online foi excedido
<a name="BKMKMaxNumberShellsUser"> </a>

Cada administrador tem permissão para no máximo três conexões remotas simultâneas com o Skype for Business Online. Se você tiver três conexões remotas do PowerShell em funcionamento, qualquer tentativa de fazer uma quarta conexão simultânea falhará, com a seguinte mensagem de erro:

- **Erro**: *New-PSSession : [admin.vdomain.com] A conexão com o servidor remoto admin.vdomain.com falhou com a seguinte mensagem de erro: O serviço WS-Management não pode processar a solicitação. O número máximo de shells simultâneos para esse usuário foi excedido. Feche os shells existentes ou eleva a cota para este usuário. Para obter mais informações, consulte a https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 [Solução de Problemas Remota](*

- **Resolução:** a única maneira de resolver esse problema é fechar uma ou mais das conexões anteriores. Quando terminar uma sessão do Skype for Business Online, recomendamos que você use o cmdlet **Remove-PSSession** para encerrar a sessão. Isso ajudará você a evitar esse problema.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>O número máximo de shells simultâneos para este locatário no Skype for Business Online foi excedido
<a name="BKMKMaxNumberShellsTenant"> </a>

Embora cada administrador tenha permissão para ter até três conexões simultâneas com um locatário do Skype for Business Online, nenhum único locatário tem permissão para ter mais de 20 conexões simultâneas. Por exemplo, seis administradores podem ter três sessões abertas. Se um quarto administrador tentar fazer mais de 2 conexões (resultando em um total de 21 conexões simultâneas), essa tentativa falhará, com a seguinte mensagem de erro:
  
- **Erro**: *New-PSSession : [admin.vdomain.com] A conexão com o servidor remoto admin.vdomain.com falhou com a seguinte mensagem de erro: O serviço WS-Management não pode processar a solicitação. O número máximo de shells simultâneos para esse locatário foi excedido. Feche os shells existentes ou eleva a cota para este locatário. Para obter mais informações, consulte a https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 [Solução de Problemas Remota](*

- **Resolução:** a única maneira de resolver esse problema é fechar uma ou mais das conexões anteriores. Quando terminar uma sessão do Skype for Business Online, recomendamos que você use o cmdlet **Remove-PSSession** para encerrar essa sessão. Isso ajudará você a evitar esse problema.  
 
## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador para gerenciamento do Skype for Business Online usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
