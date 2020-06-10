---
title: Adicionar um convidado a uma equipe
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
f1.keywords:
- NOCSH
localization_priority: Priority
description: Os administradores podem aprender a adicionar novos usuários convidados a uma organização nos clientes para área de trabalho e Web do Microsoft Teams e no portal de colaboração B2B do Azure Active Directory.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea1670078a61366e1ab0207368a58f9ad2b900ab
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2020
ms.locfileid: "44609829"
---
<a name="add-a-guest-to-a-team"></a>Adicionar um convidado a uma equipe
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Qualquer pessoa com uma conta de email corporativa ou de consumidor, como o Outlook, o Gmail ou outras, pode participar como convidado no Teams.

Como administrador, você pode adicionar um novo usuário convidado à organização de algumas maneiras:
- Os administradores globais ou administradores do Teams e os proprietários de equipes adicionam um convidado a uma equipe nos clientes do Teams ou no centro de administração do Teams. Para saber mais, leia [Adicionar convidados a uma equipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f). Se você ainda não configurou o acesso de convidado, siga as etapas da [Lista de verificação de acesso de convidado](guest-access-checklist.md).

> [!NOTE] 
> Isso não se aplica quando o recurso **Administradores e usuários na função de emissor de convites podem convidar** se encontra ativado. Isso ocorre porque a função de emissor de convites não é compatível com o Teams.

- Adicione convidados à sua organização através da colaboração do Azure AD (Azure Active Directory) B2B. A colaboração do Azure AD B2B permite que um administrador global convide e autorize um conjunto de usuários externos ao fazer o upload de um arquivo com valores separados por vírgulas (CSV) de, no máximo, 2.000 linhas no portal de colaboração B2B. Para obter mais detalhes, confira [colaboração do Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?linkid=826383).

Com a colaboração do Azure AD B2B, as organizações podem impor políticas de acesso condicional e autenticação multifator (MFA) para usuários B2B. Essas políticas podem ser impostas no nível do locatário, aplicativo ou usuário individual, da mesma maneira que podem ser habilitadas para membros e funcionários em tempo integral da organização. Essas políticas são aplicadas na organização de recursos. Para obter mais informações, consulte [Acesso condicional para usuários de colaboração B2B](https://go.microsoft.com/fwlink/?linkid=857454). Usuários convidados não podem ser bloqueados individualmente.

Os usuários convidados que você adicionou por meio do Azure AD B2B, Grupos do Microsoft 365 ou SharePoint Online estão prontos para prosseguir. O administrador do Microsoft 365 ou Office 365 ou um proprietário da equipe pode adicionar aqueles convidados às suas respectivas equipes. Se uma equipe já estiver com um grupo do Microsoft 365 e um convidado for adicionado ao grupo, o convidado obterá acesso à equipe. Adicionar um convidado através do grupo do Microsoft 365 não gera um email de convite para o convidado; portanto, alguém da equipe deve notificá-lo.

> [!NOTE]
> Os convidados estão sujeitos aos limites de serviço do [Microsoft 365 ou Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) e do [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).

Você pode acompanhar adições de convidados no Azure AD ou no Centro de segurança do Microsoft 365. A adição de um convidado no Microsoft Teams é auditada e registrada como uma atividade de administração de grupo do Azure AD: “Adicionou membro a grupo”. Para obter mais detalhes, confira [Auditar e reportar um usuário de colaboração B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) e [Procurar registro de auditoria no Centro de segurança do Microsoft 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).


## <a name="more-information"></a>Mais informações

[Autorizar o acesso para convidado no Microsoft Teams](teams-dependencies.md)</br>
[Ativar ou desativar o acesso a convidados no Microsoft Teams](set-up-guests.md)</br>
[Usar o PowerShell para controlar o acesso de convidados a uma equipe](guest-access-powershell.md)
