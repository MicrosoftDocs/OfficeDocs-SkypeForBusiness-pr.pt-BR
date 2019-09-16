---
title: Obter clientes do Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Aprenda a usar os vários clientes disponíveis para o Microsoft Teams, que incluem web, área de trabalho (Windows e Mac) e dispositivos móveis (Android e iOS).
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 646305383c8f38671c07f598bc9ff1671890d22f
ms.sourcegitcommit: 3c40bdd228ef88967cdf689100f2030f6997d9d5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2019
ms.locfileid: "36715795"
---
<a name="get-clients-for-microsoft-teams"></a>Obter clientes do Microsoft Teams 
===========================

O Microsoft Teams tem clientes disponíveis para desktop (Windows e Mac), web e dispositivos móveis (Android e iOS). Todos esses clientes precisam de uma conexão à internet ativa e não são suportados em modo offline.

> [!NOTE]
> A partir de 29 de novembro de 2018, você não poderá mais usar o aplicativo Microsoft Teams para Windows 10 S (Visualização), disponível na Microsoft Store. Em vez disso, agora você pode baixar e instalar o cliente de área de trabalho do Teams em dispositivos executando o modo Windows 10 S. Para baixar o cliente de área de trabalho, vá para [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754). As compilações MSI do cliente de área de trabalho do Teams ainda não estão disponíveis para dispositivos executando o modo Windows 10 S.
>
> Para obter mais informações sobre o modo Windows 10 S, consulte [Introdução ao Windows 10 no modo S](https://www.microsoft.com/windows/s-mode). 

<a name="desktop-client"></a>Cliente de desktop
--------------

> [!Tip]
> Assista à sessão a seguir para conhecer os benefícios do Windows Desktop Client e como planejar e executar sua implantação: [Cliente de Desktop do Microsoft Teams](https://aka.ms/teams-clients)

O cliente de área de trabalho do Microsoft Teams é um aplicativo autônomo e também está [disponível no Office 365 ProPlus](https://docs.microsoft.com/pt-BR/deployoffice/teams-install). Teams está disponível para Windows (7+) nas versões de 32 e 64 bits e para macOS (10.10+). No Windows, o Teams exige o .NET Framework 4.5 ou posterior; o instalador do Teams oferecerá instalá-lo para você se você não o tiver. 

Os clientes de área de trabalho fornecem suporte de comunicação em tempo real (áudio, vídeo e compartilhamento de conteúdo) para reuniões de equipe, chamadas em grupo e chamadas individuais privadas.

Os clientes de desktop podem ser baixados e instalados diretamente pelos usuários finais[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) se tiverem as permissões locais apropriadas (direitos de administrador não são necessários para instalar o cliente Teams em um PC, mas são necessários em um Mac).

Os administradores de TI podem escolher seu método preferido para distribuir os arquivos de instalação aos computadores de sua organização, como o System Center Configuration Manager (Windows) ou o Jamf Pro (macOS). Para obter o pacote MSI para distribuições do Windows, consulte [Instalar o Microsoft Teams usando MSI](msi-deployment.md).  

> [!NOTE]
> A distribuição do cliente por esses mecanismos é apenas para a instalação inicial dos clientes Microsoft Teams, e não para atualizações futuras.

### <a name="windows"></a>Windows

A instalação do Microsoft Teams para Windows oferece instaladores para download nas arquiteturas de 32 bits e 64 bits.

> [!NOTE]
> A arquitetura (32 bits vs. 64 bits) do Microsoft Teams é independente da arquitetura do Windows e do Office instalados.

O cliente Windows é implantado na pasta AppData localizada no perfil do usuário. A implantação no perfil local do usuário permite que o cliente seja instalado sem exigir direitos elevados. O cliente Windows aproveita os seguintes locais:

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingsAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

Quando os usuários iniciam uma chamada usando o cliente Microsoft Teams pela primeira vez, eles podem notar um aviso com as configurações de firewall do Windows, que solicita que os usuários permitam a comunicação. Os usuários podem ser instruídos a ignorar esta mensagem porque a chamada funcionará mesmo quando o aviso for recusado.

![Captura de tela de um diálogo do Alerta de Segurança do Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> A configuração do Firewall do Windows será alterada mesmo quando o aviso for descartado ao selecionar “Cancelar”. Serão criadas duas regras de entrada para teams.exe com a ação Block para protocolos TCP e UDP.

### <a name="mac"></a>Mac

Usuários de Mac podem instalar o Teams usando um arquivo de instalação PKG para computadores macOS. É necessário acesso administrativo para instalar o cliente Mac. O cliente macOS é instalado na pasta /Applications.

#### <a name="install-teams-by-using-the-pkg-file"></a>Instalar o Teams usando o arquivo PKG

1. Na [página de download do Teams](https://teams.microsoft.com/downloads), em **Mac**, clique em **Download**.
2. Clique duas vezes no arquivo PKG.
3. Siga o assistente de instalação para concluir a instalação.
4. O Teams será instalado na pasta /Applications. É uma instalação em toda a máquina.

> [!NOTE]
> Durante a instalação, o PKG solicitará credenciais de administrador. O usuário precisa inserir as credenciais de administrador, independentemente de o usuário ser ou não um administrador.

Se um usuário tiver atualmente uma instalação DMG do Teams e quiser substituí-lo pela instalação PKG, o usuário deverá:

1. Sair do aplicativo Teams.
2. Desinstalar o aplicativo do Teams.
3. Instalar o arquivo PKG.

Os administradores de TI podem usar a implantação gerenciada do Teams para distribuir os arquivos de instalação para todos os Macs de sua organização, como o Jamf Pro.

> [!NOTE]
> Se você tiver problemas ao instalar o PKG, avise-nos. Na seção **Comentários**, no final deste artigo, clique em **Comentários sobre o produto**.

<a name="web-client"></a>Clientes Web 
----------

O cliente Web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) é um cliente completo e funcional que pode ser usado em vários navegadores. O cliente Web suporta Chamadas e Reuniões usando o webRTC, portanto, não há necessidade de usar um plugin ou download para executar o Teams em um navegador da web. O navegador deve ser configurado para permitir cookies de terceiros. 

[!INCLUDE [browser-support](includes/browser-support.md)]

O cliente Web executa a detecção da versão do navegador ao se conectar[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753). Se uma versão do navegador não suportada for detectada, ela bloqueará o acesso à interface da Web e recomendará que o usuário faça o download do cliente de desktop ou do aplicativo para dispositivos móveis.

<a name="mobile-clients"></a>Clientes móveis
--------------

Os aplicativos móveis da Microsoft Teams estão disponíveis para Android e iOS e são voltados para usuários em trânsito que participam de conversas baseadas em bate-papo e permitem chamadas de áudio ponto a ponto. Para aplicativos para dispositivos móveis, acesse as lojas relevantes, Google Play e a Apple App Store. O aplicativo Windows Phone foi retirado em 20 de julho de 2018 e pode não funcionar mais. 

As plataformas móveis suportadas para os aplicativos móveis da Microsoft Teams são as seguintes:

-   **Android**: 4.4 ou posterior

-   **iOS**: 10.0 ou posterior

> [!NOTE]
> A versão móvel deve estar disponível ao público para que o Teams funcione conforme o esperado.

Os aplicativos móveis são distribuídos e atualizados somente por meio da loja de aplicativos da respectiva plataforma móvel. A distribuição dos aplicativos móveis via MDM ou carregamento lateral não são suportados pela Microsoft. Depois que o aplicativo móvel for instalado em uma plataforma móvel compatível, o próprio aplicativo móvel do Teams será suportado, desde que a versão esteja dentro de três meses a partir da versão atual.


| | | |
|---------|---------|---------|
|![Um ícone representando um ponto de decisão](media/Get_clients_for_Microsoft_Teams_image4.png)      |Ponto de decisão         |Existe alguma restrição que esteja impedindo os usuários de instalar o cliente Microsoft Teams adequado em seus dispositivos?         |
|![Um ícone representando os próximos passos](media/Get_clients_for_Microsoft_Teams_image5.png)     |Próximos passos         |Se sua organização restringe a instalação de software, verifique se esse processo é compatível com o Microsoft Teams. Nota: Os direitos de administrador não são obrigatórios para a instalação do cliente PC, mas são obrigatórios para a instalação em Mac.         |

<a name="client-update-management"></a>Gerenciamento de atualização do cliente
------------------------

No momento, os clientes são atualizados automaticamente pelo serviço do Microsoft Teams, sem a necessidade de intervenção de um administrador de TI. Se uma atualização estiver disponível, o cliente fará o download automaticamente e, quando o aplicativo ficar inativo por um período de tempo, o processo de atualização será iniciado.

<a name="client-side-configurations"></a>Configurações do lado do cliente
---------------------------

No momento, não estão disponibilizadas opções para configurar o cliente através do administrador do locatário, do PowerShell, do Group Policy Objects, nem do registro.

<a name="notification-settings"></a>Configurações de notificação
----------------------------

No momento, não estão disponibilizadas opções para administradores de TI definirem as configurações de notificação do lado do cliente. Todas as opções de notificação são definidas pelo usuário. A figura abaixo descreve as configurações padrão do cliente.

![Captura de tela das configurações de notificação.](media/Get_clients_for_Microsoft_Teams_image6.png)

<a name="sample-powershell-script"></a>Exemplo de script do PowerShell
----------------------------

Este script de exemplo, que precisa ser executado em computadores clientes no contexto de uma conta de administrador elevada, criará uma nova regra de firewall de entrada para cada pasta de usuário encontrada em c:\usuários. Quando o Teams encontrar essa regra, impedirá que o aplicativo do Teams solicite que os usuários criem regras de firewall quando os usuários fizerem a primeira chamada no Teams. 

```

<#
.Synopsis
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($users.Length -gt 0)
{
    foreach ($user in $users)
    {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath)
        {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue))
            {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}

```
