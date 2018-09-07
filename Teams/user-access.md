---
title: Gerenciamento do acesso de usuários ao Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: Saiba como habilitar ou desabilitar o acesso em nível de usuário na base por usuário.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 272a7c4e77e1d8a62fa9f1de49461b44bc50b687
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23851543"
---
<a name="manage-user-access-to-microsoft-teams"></a>Gerenciamento do acesso de usuários ao Microsoft Teams
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

No nível do usuário, o acesso ao Microsoft Teams pode ser habilitado ou desabilitado em uma base por usuário por como atribuir ou remover a licença do produto Microsoft Teams.

Atualmente, não existem opções para equipes ou um subconjunto dos recursos de equipes, ativando ou desativando em um nível de usuário individual fora do licenciamento por política.

> [!NOTE]
>A Microsoft recomenda que você ativar equipes para todos os usuários em uma empresa para que as equipes podem ser formadas organicamente para projetos e outras iniciativas dinâmicas. Mesmo se você decidir para piloto, ainda será útil manter equipes habilitadas para todos os usuários, mas apenas as comunicações para o grupo piloto de usuários de destino.

## <a name="manage-teams-through-the-office-365-admin-center"></a>Gerenciar equipes por meio do Centro de administração do Office 365

As equipes licenças de nível de usuário são gerenciadas diretamente por meio das interfaces de gerenciamento de usuário do Office 365 admin center. Um administrador pode atribuir licenças a novos usuários quando novas contas de usuário forem criadas ou a usuários com contas existentes. O administrador precisa ter privilégios do Administrador Global do Office 365 ou Administrador de Gerenciamento de Usuários para administrar as licenças do Microsoft Teams.

Quando o SKU de uma licença, como E3 ou E5, for atribuído a um usuário, a licença do Microsoft Teams é atribuída automaticamente e o usuário fica habilitado para o Microsoft Teams. Os administradores podem ter um controle mais detalhado sobre todos os serviços e licenças do Office 365, e a licença do Microsoft Teams para um usuário específico ou um grupo de usuários pode ser habilitada ou desabilitada.

![Captura de tela da seção de licenças de produto no centro de administração do Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

Uma licença de usuário de equipes pode estar desabilitada a qualquer momento. Depois que a licença é desabilitada, não poderá fazer o acesso de usuários a Microsoft Teams e o usuário não terá mais conseguirá ver equipes na home page e iniciador de aplicativo do Office 365.

![Captura de tela da seção de licenças de produto no centro de administração do Office 365, mostrando o Microsoft Teams selecionado.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a>Gerenciar via PowerShell

A habilitação e desabilitação do Microsoft Teams como uma licença de carga de trabalho pelo PowerShell é realizada da mesma forma que com qualquer outra carga de trabalho. O nome do plano de serviço é TEAMS1 for Microsoft Teams. Para o governo, o nome do plano de serviço é TEAMS_GOV. (Consulte mais informações em [Desabilitar o acesso aos serviços com o PowerShell do Office 365](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell).)

**Exemplo:** A seguir é apenas uma amostra rápida sobre como você faria desabilitar equipes para todas as pessoas em um tipo de licença específico. Você precisa fazer isso primeiro e depois habilitá-lo individualmente para os usuários que devem ter acesso para fins de piloto.

Para exibir os tipos de assinatura que você tem na organização, use este comando:

      Get-MsolAccountSku

Preencha o nome do seu plano, quen inclui o nome da organização e o plano da escola (como ContosoSchool:ENTERPRISEPACK_STUDENT) e execute estes comandos:

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
Para desabilitar as equipes de todos os usuários com uma licença ativa para o seu plano nomeado, execute o seguinte comando:

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |Ponto de decisão         |<ul><li>O que é o planejamento da sua organização para inclusão de equipes em toda a organização?  (Piloto ou Aberto)</li></ul>         |
|![Ícone de próximos passos.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |Próximos passos         |<ul><li>Se for iniciar via piloto fechado, decida se deseja fazê-lo através de licenciamento ou comunicação direcionada.</li><li>Dependendo de decisão, siga as etapas para certificar-se testar apenas usuários que têm permissão para acessar as equipes (se necessário).</li><li>Documente as diretrizes para quais usuários que serão (ou não) têm acesso às equipes.</li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a>Gerenciar equipes a nível de locatário do Office 365
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

