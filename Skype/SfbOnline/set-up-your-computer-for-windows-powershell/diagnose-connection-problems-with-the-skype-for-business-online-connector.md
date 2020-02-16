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
description: Solucionar problemas de criação de uma sessão remota do PowerShell para se conectar ao Skype for Business Online, incluindo o módulo de importação, o Shell simultâneo, o Live ID e os erros de permissão.
ms.openlocfilehash: f3de8d67079aaf4afeffdc63588f6806413383fc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010684"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnosticar problemas de conexão com o Conector do Skype for Business Online

Este tópico fornece informações que ajudarão você a diagnosticar e solucionar problemas que podem ocorrer quando você tenta criar uma sessão remota do Microsoft PowerShell que se conecta ao Skype for Business online. Confira as seções a seguir:
  
- [Importar-erro de módulo causado pela política de execução do Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Erro de importação-módulo causado por uma versão incorreta do Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Falha ao se conectar ao servidor de ID dinâmica](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Falha ao carregar o módulo Live ID](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [O logon falhou para o usuário](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [O usuário não tem permissão para gerenciar esse locatário](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [A capacidade de conexão com o locatário foi desabilitada no Skype for Business Online](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)

- [O número máximo de shells simultâneos para este usuário no Skype for Business online foi excedido](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [O número máximo de shells simultâneos para este locatário no Skype for Business online foi excedido](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Importar-erro de módulo causado pela política de execução do Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

A política de execução do PowerShell ajuda a determinar quais arquivos de configuração podem ser carregados no console do PowerShell e quais scripts um usuário pode executar desse console. No mínimo, o módulo do conector Skype for Business online não pode ser importado, a menos que a política de execução tenha sido definida como RemoteSigned. Se não tiver, você receberá a seguinte mensagem de erro ao tentar importar o módulo:
  
- **Erro**: <em>Import-Module: file C:\\arquivos de\\programas arquivos\\comuns Microsoft Lync Server\\2013\\LyncOnlineConnector\\LyncOnlineConnectorStartup. psm1 não podem ser carregados porque a execução de scripts está desabilitada neste sistema. Para obter mais informações, consulte about_Execution_Policies https://go.microsoft.com/fwlink/?LinkID=135170em.</em>

- **Solução**: para resolver esse problema, inicie o PowerShell como administrador e execute o seguinte comando:
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Para obter detalhes sobre a política de execução, consulte [sobre políticas de execução](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Erro de importação-módulo causado por uma versão incorreta do Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

O módulo do conector Skype for Business online pode ser executado somente no Windows PowerShell 3,0. Se você tentar importar o módulo em uma versão anterior do PowerShell, o processo de importação falhará com uma mensagem de erro semelhante a esta:
  
  - **Erro**: *Import-Module: a versão do PowerShell carregado é ' 2,0 '. O\\módulo: Arquivos de programas\\arquivos\\comuns do Microsoft Lync Server\\2013\\LyncOnlineConnector\\LyncOnlineConnector. psd1 ' requer uma versão mínima do PowerShell de ' 3,0 ' para ser executado. Verifique a instalação do PowerShell e tente novamente.*

- **Resolução**: a única maneira de corrigir esse problema é instalar o Windows PowerShell 3,0, que está disponível no centro de download da Microsoft [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595)em.
  
## <a name="failed-to-connect-to-live-id-server"></a>Falha ao se conectar ao servidor de ID dinâmica
<a name="BKMKFailedConnect"> </a>

Geralmente, há três motivos pelos quais a tentativa de conexão pode falhar com a seguinte mensagem de erro:

  - **Erro**: *Get-CsWebTicket: falha ao conectar servidores Live ID. Verifique se o proxy está habilitado ou se o computador tem conexão de rede com servidores Live ID.*

- **Resolução**: geralmente esse erro significa que o assistente de conexão do Microsoft Online Services não está em execução. Você pode verificar o status desse serviço executando o seguinte comando no prompt do PowerShell: 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Se o serviço não estiver em execução, inicie o serviço usando este comando:
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Se o serviço estiver em execução, você pode estar encontrando problemas com a conexão de rede entre seu computador e o servidor de autenticação do Microsoft Live ID. Para verificar isso, abra o Internet Explorer e navegue para [ https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Tente conectar-se ao Office 365 de lá. Se isso falhar, provavelmente você está tendo problemas de conexão de rede.
  
    Menos comumente, é possível que o URI de conexão do servidor de autenticação do Microsoft Live ID tenha sido configurado com o valor errado. Se você já tiver determinado que o assistente de entrada está em execução e que você não está experimentando problemas de conectividade de rede, isso pode ser o problema. Nesse caso, entre em contato com o suporte do Office 365.
  
## <a name="failed-to-load-live-id-module"></a>Falha ao carregar o módulo Live ID
<a name="BKMKFailedLoad"> </a>

Um dos pré-requisitos para usar o PowerShell para gerenciar o Skype for Business Online é instalar o assistente de conexão do Microsoft Online Services. Se o assistente de entrada não estiver instalado, você receberá a seguinte mensagem de erro ao tentar estabelecer uma sessão remota com o Skype for Business Online:

- **Erro**: *Get-CsWebTicket: não é possível carregar o módulo Live ID. Certifique-se de que a versão correta do assistente de conexão do Live ID esteja instalada.*

- **Resolução**: o assistente de conexão do Microsoft Online Services está disponível no Microsoft Download Center no [Assistente de conexão do Microsoft Online Services para profissionais de ti RTW](https://www.microsoft.com/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>O logon falhou para o usuário
<a name="BKMKLogonFailed"> </a>

Ao tentar fazer uma conexão remota com o Skype for Business Online, você deve fornecer o nome de usuário e a senha de uma conta de usuário válida do Skype for Business online. Se você não fizer isso, o logon falhará juntamente com uma mensagem de erro semelhante a esta:

- **Erro**: *Get-CsWebTicket: falha no logon para o usuário ' kenmyer@litwareinc.com '. Crie um novo objeto PSCredential, certificando-se de ter usado o nome de usuário e a senha corretos.*

- **Resolução**: se você acha que está usando uma conta de usuário válida e tem a senha correta, tente conectar-se novamente. Se isso falhar, use as mesmas credenciais e tente fazer logon em [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Se não for possível fazer logon, entre em contato com o suporte do Office 365. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>O usuário não tem permissão para gerenciar esse locatário
<a name="BKMKUserPermission"> </a>

Você não pode fazer uma conexão remota do PowerShell para o Skype for Business Online, a menos que você seja membro do grupo de administradores de locatários. Se não estiver, a tentativa de conexão falhará e você receberá a seguinte mensagem de erro:

- **Erro**: *New-PSSession: [admin.vdomain.com] Falha ao processar dados do servidor remoto admin.vdomain.com com a seguinte mensagem de erro: o usuário ' User@foo.com ' não tem permissão para gerenciar esse locatário. É possível conceder permissões atribuindo o usuário à função RBAC apropriada. Para obter mais informações, consulte [solução de problemas remotos](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Solução**: se você acha que está, ou deveria ser, um membro do grupo de administradores de locatários, precisará entrar em contato com o suporte do Office 365.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>A capacidade de conexão com o locatário foi desabilitada no Skype for Business Online
<a name="BKMKAbilityConnect"> </a>

Para usar o PowerShell para gerenciar o Skype for Business Online, a propriedade EnableRemotePowerShellAccess da sua política de locatário do PowerShell `True`deve ser definida como. Se não for, a conexão falhará e você receberá a seguinte mensagem de erro:

- **Erro**: *New-PSSession: [admin.vdomain.com] Falha ao processar dados do servidor remoto admin.vdomain.com com a seguinte mensagem de erro: a capacidade de se conectar a esse locatário usando uma sessão remota do PowerShell foi desabilitada. Entre em contato com a ajuda do Lync para verificar a política do PowerShell do locatário desse locatário. Para obter mais informações, consulte [solução de problemas remotos](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Resolução**: se você vir esta mensagem de erro, será necessário entrar em contato com o suporte do Office 365 e obter acesso remoto do PowerShell habilitado.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>O número máximo de shells simultâneos para este usuário no Skype for Business online foi excedido
<a name="BKMKMaxNumberShellsUser"> </a>

Cada administrador pode ter no máximo três conexões remotas simultâneas simultâneas com o Skype for Business online. Se você tiver três conexões remotas do PowerShell em funcionamento, qualquer tentativa de fazer uma quarta conexão simultânea falhará, com a seguinte mensagem de erro:

- **Erro**: *New-PSSession: [admin.vdomain.com] Falha ao conectar-se ao servidor remoto admin.vdomain.com com a seguinte mensagem de erro: o serviço WS-Management não pode processar a solicitação. O número máximo de shells simultâneos para este usuário foi excedido. Feche os shells existentes ou aumente a cota para este usuário. Para obter mais informações, consulte [solução de problemas remoto]https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 (*

- **Resolução**: a única maneira de resolver esse problema é fechar uma ou mais das conexões anteriores. Quando tiver terminado uma sessão do Skype for Business Online, recomendamos que use o cmdlet **Remove-PSSession** para encerrar a sessão. Isso vai ajudá-lo a evitar esse problema.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>O número máximo de shells simultâneos para este locatário no Skype for Business online foi excedido
<a name="BKMKMaxNumberShellsTenant"> </a>

Embora cada administrador tenha permissão para ter até três conexões simultâneas com um locatário do Skype for Business Online, nenhum único locatário pode ter mais de nove conexões simultâneas. Por exemplo, três administradores podem ter três sessões abertas. Se um quarto administrador tentar fazer uma conexão (resultando em um total de 10 conexões simultâneas), esta tentativa irá falhar, com a seguinte mensagem de erro:
  
- **Erro**: *New-PSSession: [admin.vdomain.com] Falha ao conectar-se ao servidor remoto admin.vdomain.com com a seguinte mensagem de erro: o serviço WS-Management não pode processar a solicitação. O número máximo de shells simultâneos para esse locatário foi excedido. Feche os shells existentes ou aumente a cota para esse locatário. Para obter mais informações, consulte [solução de problemas remoto]https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 (*

- **Resolução**: a única maneira de resolver esse problema é fechar uma ou mais das conexões anteriores. Quando tiver terminado uma sessão do Skype for Business Online, recomendamos que use o cmdlet **Remove-PSSession** para encerrar essa sessão. Isso vai ajudá-lo a evitar esse problema.  
 
## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador para o gerenciamento do Skype for Business online usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
