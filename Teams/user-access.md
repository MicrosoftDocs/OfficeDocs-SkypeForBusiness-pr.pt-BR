---
title: Gerenciamento do acesso de usuários ao Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1keywords: ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.reviewer: ritikag
search.appverid: MET150
description: Saiba como habilitar ou desabilitar o acesso em nível de usuário na base por usuário.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26abd2a69bc8097c4f74cbc85435cda4eec00887
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37563110"
---
<a name="manage-user-access-to-microsoft-teams"></a>Gerenciamento do acesso de usuários ao Microsoft Teams
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

No nível do usuário, o acesso ao Microsoft Teams pode ser habilitado ou desabilitado para cada usuário, atribuindo ou removendo a licença de produto do Microsoft Teams.

Use políticas de mensagens, gerenciadas a partir do centro de administração do Teams, para controlar quais recursos de chat e mensagens de canal estão disponíveis para os usuários do teams. Você pode usar a política padrão ou criar uma ou mais políticas de mensagens personalizadas para as pessoas em sua organização. Para saber mais, leia [gerenciar políticas de mensagens no Microsoft Teams](messaging-policies-in-teams.md).

> [!NOTE]
>A Microsoft recomenda que você ative o Teams para todos os usuários de uma empresa para que as equipes possam ser formadas de forma orgânica para projetos e outras iniciativas dinâmicas. Mesmo que você esteja decidindo para o piloto, talvez ainda seja útil manter o Microsoft Teams habilitado para todos os usuários, mas somente as comunicações são direcionadas para o grupo piloto de usuários.

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a>Gerenciar equipes por meio do centro de administração do Microsoft 365

As licenças de nível de usuário do Team são gerenciadas diretamente por meio das interfaces de gerenciamento de usuários do centro de administração do Microsoft 365. Um administrador pode atribuir licenças a novos usuários quando novas contas de usuário forem criadas ou a usuários com contas existentes. O administrador precisa ter privilégios do Administrador Global do Office 365 ou Administrador de Gerenciamento de Usuários para administrar as licenças do Microsoft Teams.

Quando o SKU de uma licença, como E3 ou E5, for atribuído a um usuário, a licença do Microsoft Teams é atribuída automaticamente e o usuário fica habilitado para o Microsoft Teams. Os administradores podem ter um controle mais detalhado sobre todos os serviços e licenças do Office 365, e a licença do Microsoft Teams para um usuário específico ou um grupo de usuários pode ser habilitada ou desabilitada.

![Captura de tela da seção licenças de produto no centro de administração.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

Uma licença de usuário do teams pode ser desabilitada a qualquer momento. Depois que a licença estiver desabilitada, o acesso dos usuários ao Microsoft Teams será impedido e o usuário não poderá mais ver as equipes no inicializador de aplicativos e na página inicial do Office 365.

![Captura de tela mostrando as equipes selecionadas na seção licenças de produto.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>Gerenciar via PowerShell

> [!IMPORTANT]
> New-MsolLicenseOptions habilitará todos os serviços que foram desabilitados anteriormente, a menos que explictitly identitied em seu script personalizado. Como exemplo, se você quisesse deixar o & do Sway desabilitado durante a desativação do Microsoft Teams, você precisará inlcude-lo no script ou no Exchange & o Sway será habilitado para os usuários que você identificou. Se você quiser usar uma GUI para gerenciar essa funcionalidade, consulte: [ferramenta de relatório e gerenciamento de licenças do Office 365-atribuir licenças de remoção em massa](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)

A habilitação e desabilitação do Microsoft Teams como uma licença de carga de trabalho pelo PowerShell é realizada da mesma forma que com qualquer outra carga de trabalho. O nome do plano de serviço é TEAMS1 for Microsoft Teams. Para o GCC, o nome do plano do serviço é TEAMS_GOV. Para GCC alto, o nome do plano de serviço é TEAMS_GCCHIGH. Para DoD, o nome do plano de serviço é TEAMS_DOD (consulte [desabilitar o acesso aos serviços com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) para obter mais informações.)

**Exemplo:** Veja a seguir um exemplo rápido sobre como você desabilitaria o Teams para todos em um determinado tipo de licença. Você precisa fazer isso primeiro e depois habilitá-lo individualmente para os usuários que devem ter acesso para fins de piloto.

Para exibir os tipos de assinatura que você tem na organização, use este comando:

      Get-MsolAccountSku

Preencha o nome do seu plano, quen inclui o nome da organização e o plano da escola (como ContosoSchool:ENTERPRISEPACK_STUDENT) e execute estes comandos:

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
Para desabilitar o Microsoft Teams para todos os usuários com uma licença ativa para o seu plano nomeado, execute o seguinte comando:

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Um ícone representando um ponto de decisão](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |Ponto de decisão         |<ul><li>Qual é o plano da sua organização para o enquadro de equipes em toda a organização?  (Piloto ou Aberto)</li></ul>         |
|![Um ícone que representa as próximas etapas](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |Próximos passos         |<ul><li>Se estiver integração por meio de um piloto fechado, decida se deseja fazer isso por meio de licenciamento ou comunicação direcionada.</li><li>Dependendo da decisão, siga as etapas para garantir que somente os usuários pilotos que têm permissão para acessar o Microsoft Teams (se necessário).</li><li>Documentar as diretrizes para as quais os usuários que (ou não terão) terão acesso ao Microsoft Teams.</li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a>Gerenciar equipes no nível do locatário do Office 365
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

