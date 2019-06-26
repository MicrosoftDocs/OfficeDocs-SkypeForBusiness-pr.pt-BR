---
title: Adicionar um convidado a uma equipe
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
localization_priority: Priority
description: Conheça as ferramentas disponíveis para adicionar novos usuários a uma organização, incluindo clientes desktop e web do Microsoft Teams e o portal de colaboração do Azure Active Directory B2B.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67a00b87dbe3f29ce6588d4ff84302df2f07ce69
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221630"
---
<a name="add-a-guest-to-a-team"></a>Adicionar um convidado a uma equipe
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Qualquer pessoa com uma conta de email corporativa ou de consumidor, como o Outlook, o Gmail ou outras, pode participar como convidado no Teams.

Como administrador, você pode adicionar um novo usuário convidado à organização de algumas maneiras:
- Administradores globais que são proprietários de uma equipe podem adicionar um convidado a uma equipe através do cliente web ou cliente desktop do Microsoft Teams. Para mais detalhes, confira [Adicionar convidados à uma equipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)
- Adicione convidados à sua organização através da colaboração do Azure AD (Azure Active Directory) B2B. A colaboração do Azure AD B2B permite que um administrador global convide e autorize um conjunto de usuários externos ao fazer o upload de um arquivo com valores separados por vírgulas (CSV) de, no máximo, 2.000 linhas no portal de colaboração B2B. Para obter mais detalhes, confira [colaboração do Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?linkid=826383).

Com a colaboração do Azure AD B2B, as organizações podem impor políticas de acesso condicional e autenticação multifator (MFA) para usuários B2B. Essas políticas podem ser impostas no nível do locatário, aplicativo ou usuário individual, da mesma maneira que podem ser habilitadas para membros e funcionários em tempo integral da organização. Essas políticas são aplicadas na organização de recursos. Para obter mais informações, consulte [Acesso condicional para usuários de colaboração B2B](https://go.microsoft.com/fwlink/?linkid=857454). Usuários convidados não podem ser bloqueados individualmente.

Os usuários convidados que você já adicionou por meio do Azure AD B2B, dos Grupos do Office 365 ou do SharePoint Online estão prontos para uso. O administrador do Office 365 ou o proprietário da equipe pode adicionar aqueles convidados às respectivas equipes. Se uma equipe já estiver com um grupos do Office 365 e um convidado for adicionado ao grupo, ele obterá acesso à equipe. Adicionar um convidado através do grupo do Office 365 não gera um e-mail de convite para o convidado; então, alguém da equipe precisa notificá-lo.

> [!NOTE]
> Os convidados estão sujeitos aos limites de serviço do [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) e do [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).

Você pode acompanhar a adição de convidados no Centro de Conformidade &amp; Segurança do Azure AD ou do Office 365. A adição de um convidado no Microsoft Teams é auditada e registrada como uma atividade de administração de grupo do Azure AD: “Adicionou membro a grupo”. Para obter mais detalhes, consulte [Auditar e reportar um usuário de colaboração B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) e [Procurar registro de auditoria no Centro de Segurança &amp; Conformidade do Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).

## <a name="guest-access-vs-external-access-federation"></a>Acesso de convidado vs. acesso externo (federação)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>Mais informações

[Autorizar o acesso para convidado no Microsoft Teams](teams-dependencies.md)</br>
[Ativar ou desativar o acesso a convidados no Microsoft Teams](set-up-guests.md)</br>
[Usar o PowerShell para controlar o acesso de convidados a uma equipe](guest-access-powershell.md)
