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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Solução de problemas na criação de uma sessão remota do PowerShell para se conectar ao Skype for Business Online, incluindo Erros de importação e módulo, shell simultâneo, ID ao vivo e permissão.
ms.openlocfilehash: b585a1d4e830fdd692c85f48fbc3d4ae7b65ab57
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013315"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnosticar problemas de conexão com o Conector do Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Este tópico fornece informações que ajudarão você a diagnosticar e resolver problemas que podem ocorrer quando você tentar criar uma sessão remota do Microsoft PowerShell que se conecta ao Skype for Business Online. Consulte as seguintes seções:
  
- [Erro de módulo de importação causado pela Windows PowerShell de execução](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Import-Module Error caused by incorrect version of Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [A autenticação moderna falha quando a autenticação do WinRM Basic foi desabilitada](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [Falha ao se conectar ao Live ID Server](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Falha ao carregar o módulo live ID](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Falha ao entrar para o usuário](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [O usuário não tem permissão para gerenciar esse locatário](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [A capacidade de se conectar ao locatário foi desabilitada no Skype for Business Online](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [O número máximo de shells simultâneos para esse usuário no Skype for Business Online foi excedido](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [O número máximo de shells simultâneos para esse locatário no Skype for Business Online foi excedido](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Import-Module erro causado pela Windows PowerShell de execução
<a name="BKMKPowerShellExecutionPolicy"> </a>

A política de execução do PowerShell ajuda a determinar quais arquivos de configuração podem ser carregados no console do PowerShell e quais scripts um usuário pode executar a partir desse console. No mínimo, o módulo conector do Skype for Business Online não pode ser importado, a menos que a política de execução tenha sido definida como RemoteSigned. Se não tiver, você receberá a seguinte mensagem de erro ao tentar importar o módulo:
  
- **Erro**: Import-Module : Arquivo C: Arquivos de Programas Arquivos Comuns <em> \\ Microsoft \\ \\ Lync Server 2013 \\ Módulos \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1 não podem ser carregados porque a execução de scripts está desabilitada neste sistema. Para obter mais informações, consulte about_Execution_Policies em https://go.microsoft.com/fwlink/?LinkID=135170 .</em>

- **Resolução** Para resolver esse problema, inicie o PowerShell como administrador e execute o seguinte comando:
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Para obter detalhes sobre a política de execução, consulte [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Import-Module erro causado pela versão incorreta do Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

O módulo conector do Skype for Business Online só pode ser executado em Windows PowerShell 3.0. Se você tentar importar o módulo em uma versão anterior do PowerShell, o processo de importação falhará com uma mensagem de erro semelhante a esta mensagem:
  
  - **Erro**: *Import-Module : A versão do PowerShell carregado é '2.0'. O módulo 'D: Arquivos de Programas Arquivos Comuns \\ \\ Microsoft \\ Lync Server 2013 \\ Módulos \\ LyncOnlineConnector \\ LyncOnlineConnector.psd1' requer uma versão mínima do PowerShell de '3.0' para ser executada. Verifique a instalação do PowerShell e tente novamente.*

- **Resolução**: A única maneira de corrigir esse problema é instalar o Windows PowerShell 3.0, que está disponível no Centro de Download da Microsoft em [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) .
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>A autenticação moderna falha quando a autenticação do WinRM Basic foi desabilitada
<a name="BKMKWinRMBasicAuth"> </a>

A versão mais recente do módulo conector do Skype for Business Online usa autenticação moderna, mas o cliente subjacente do Gerenciamento Remoto do Windows (WinRM) deve ser configurado para permitir a autenticação básica.  A autenticação moderna usa tokens de portador, que geralmente são passados no *header Autorização:* Portador. Windows PowerShell, sobre o qual o PowerShell do Skype for Business foi criado, não permite a manipulação desse header.  Em vez disso, o Skype for Business PowerShell usa o header *Autorização: Básico* para passar o token do portador.

Consulte [Baixar e instalar Windows PowerShell](./download-and-install-windows-powershell-5-1.md) para obter instruções sobre como habilitar o WinRM para autenticação básica.

## <a name="failed-to-connect-to-live-id-server"></a>Falha ao se conectar ao Live ID Server
<a name="BKMKFailedConnect"> </a>

> [!WARNING] 
> A autenticação de ID ao vivo foi preterida para o Skype For Business Online Connector. Use o Módulo do Teams PowerShell para gerenciar o locatário online. Ao gerenciar ambientes híbridos, atualize para a atualização cumulativa mais recente ou use a autenticação oAuth.

Normalmente, há três motivos pelos quais a tentativa de conexão pode falhar com a seguinte mensagem de erro:

  - **Erro**: *Get-CsWebTicket : Falha ao conectar servidores de ID ao vivo. Certifique-se de que o proxy está habilitado ou se* o computador tem conexão de rede com servidores de ID ao vivo.

- **Resolução**: geralmente, esse erro significa que o assistente de Microsoft Online Services de login não está sendo executado. Você pode verificar o status desse serviço executando o seguinte comando no prompt do PowerShell: 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Se o serviço não estiver em execução, inicie o serviço usando este comando:
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Se o serviço estiver em execução, talvez você tenha problemas com a conexão de rede entre seu computador e o Servidor de Autenticação de ID do Microsoft Live. Para verificar isso, abra o Internet Explorer e navegue até [ https://login.microsoftonline.com/ .](https://login.microsoftonline.com/.) Tente fazer logor no Microsoft 365 ou Office 365 a partir daí. Se isso falhar, provavelmente você está enfrentando problemas de conexão de rede.
  
    Menos comumente, é possível que o URI de conexão para o Microsoft Live ID Authentication Server tenha sido configurado com o valor errado. Se você já determinou que o assistente de Sign-In está em execução e que você não está enfrentando problemas de conectividade de rede, esse pode ser o problema. Nesse caso, entre em contato com o Suporte da Microsoft.
  
## <a name="failed-to-load-live-id-module"></a>Falha ao carregar o módulo live ID
<a name="BKMKFailedLoad"> </a>

Um dos pré-requisitos para usar o PowerShell para gerenciar o Skype for Business Online é instalar o assistente de Microsoft Online Services de login. Se o Assistente de Logon não estiver instalado, você receberá a seguinte mensagem de erro ao tentar estabelecer uma sessão remota com o Skype for Business Online:

- **Erro**: *Get-CsWebTicket : não é possível carregar o módulo ID ao vivo. Certifique-se de que a versão correta do assistente de entrada do Live Id está instalada.*

- **Resolução**: o Microsoft Online Services assistente de login está disponível no Centro de Download da Microsoft Microsoft Online Services Sign-In Assistente para Profissionais de [TI RTW](https://www.microsoft.com/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Falha no logon para o usuário
<a name="BKMKLogonFailed"> </a>

Ao tentar fazer uma conexão remota com o Skype for Business Online, você deve fornecer o nome de usuário e a senha de uma conta de usuário válida do Skype for Business Online. Se você não fizer isso, o logon falhará juntamente com uma mensagem de erro semelhante a esta mensagem:

- **Erro**: *Get-CsWebTicket : Falha no logon para o usuário "kenmyer@litwareinc.com". Crie um novo objeto PSCredential,* certifique-se de que você tenha usado o nome de usuário e a senha corretos.

- **Resolução**: se você acha que está usando uma conta de usuário válida e que tem a senha correta, tente fazer logor novamente. Se isso falhar, use as mesmas credenciais e tente entrar em [https://login.microsoftonline.com/](https://login.microsoftonline.com/) . Se você não conseguir entrar, entre em contato com o Suporte da Microsoft. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>O usuário não tem permissão para gerenciar esse locatário
<a name="BKMKUserPermission"> </a>

Você não pode fazer uma conexão remota do PowerShell com oSkype for Business Online, a menos que seja membro do grupo Administradores de Locatários. Se você não estiver, sua tentativa de conexão falhará e receberá a seguinte mensagem de erro:

- **Erro**: New-PSSession : [admin.vdomain.com] O processamento de dados do servidor remoto admin.vdomain.com falhou com a seguinte mensagem de erro: o usuário 'user@foo.com' não tem permissão para gerenciar esse *locatário. As permissões podem ser concedidas atribuindo o usuário à função RBAC apropriada. Para obter mais informações, consulte [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Resolução**: se você acha que é ou deveria ser um membro do grupo Administradores de Locatários, você precisará entrar em contato com o Suporte da Microsoft.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>A capacidade de se conectar ao locatário foi desabilitada no Skype for Business Online
<a name="BKMKAbilityConnect"> </a>

Para usar o PowerShell para gerenciar o Skype for Business Online, a propriedade EnableRemotePowerShellAccess de sua política de locatário do PowerShell deve ser definida como  `True` . Se não estiver, sua conexão falhará e você receberá a seguinte mensagem de erro:

- **Erro**: New-PSSession : [admin.vdomain.com] O processamento de dados do servidor remoto admin.vdomain.com falhou com a seguinte mensagem de erro: a capacidade de se conectar a esse locatário usando uma sessão remota do PowerShell foi *desabilitada. Entre em contato com a Ajuda do Lync para verificar a Política de Locatário do Powershell deste locatário. Para obter mais informações, consulte [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Resolução**: se você vir essa mensagem de erro, precisará entrar em contato com o Suporte da Microsoft e habilitar o acesso remoto do PowerShell.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>O número máximo de shells simultâneos para esse usuário no Skype for Business Online foi excedido
<a name="BKMKMaxNumberShellsUser"> </a>

Cada administrador tem permissão para no máximo três conexões remotas simultâneas com o Skype for Business Online. Se você tiver três conexões remotas do PowerShell funcionando, qualquer tentativa de fazer uma quarta conexão simultânea falhará, com a seguinte mensagem de erro: 

- **Erro**: New-PSSession : [admin.vdomain.com] A conexão ao servidor remoto admin.vdomain.com falhou com a seguinte mensagem de erro : o serviço WS-Management não pode processar *a solicitação. O número máximo de shells simultâneos para esse usuário foi excedido. Feche os shells existentes ou aumente a cota para esse usuário. Para obter mais informações, consulte [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Resolução**: a única maneira de resolver esse problema é fechar uma ou mais das conexões anteriores. Quando terminar uma sessão do Skype for Business Online, recomendamos que você use o cmdlet **Remove-PSSession** para encerrar a sessão. Isso ajudará você a evitar esse problema.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>O número máximo de shells simultâneos para esse locatário no Skype for Business Online foi excedido
<a name="BKMKMaxNumberShellsTenant"> </a>

Embora cada administrador tenha permissão para ter até três conexões simultâneas com um locatário do Skype for Business Online, nenhum único locatário tem permissão para ter mais de 20 conexões simultâneas. Por exemplo, seis administradores podem ter três sessões abertas. Se um quarto administrador tentar fazer mais de duas conexões (resultando em um total de 21 conexões simultâneas), essa tentativa falhará, com a seguinte mensagem de erro:
  
- **Erro**: New-PSSession : [admin.vdomain.com] A conexão ao servidor remoto admin.vdomain.com falhou com a seguinte mensagem de erro: o serviço WS-Management não pode processar *a solicitação. O número máximo de shells simultâneos para esse locatário foi excedido. Feche os shells existentes ou eleva a cota para esse locatário. Para obter mais informações, consulte [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Resolução**: a única maneira de resolver esse problema é fechar uma ou mais das conexões anteriores. Quando terminar uma sessão do Skype for Business Online, recomendamos que você use o cmdlet **Remove-PSSession** para encerrar essa sessão. Isso ajudará você a evitar esse problema.  
 
## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador para gerenciamento do skype for business online usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
