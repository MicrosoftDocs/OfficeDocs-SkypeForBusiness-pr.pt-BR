---
title: Adicionar um convidado a uma equipe
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: Os administradores podem aprender a adicionar novos usuários convidados a uma organização nos clientes para área de trabalho e Web do Microsoft Teams e no portal de colaboração B2B do Azure Active Directory.
ms.openlocfilehash: e74819ba46af8a9f6bcf3b2198f78354bf7bfb79
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346172"
---
# <a name="add-a-guest-to-a-team"></a>Adicionar um convidado a uma equipe

Qualquer pessoa com uma conta de email corporativa ou de consumidor, como o Outlook, o Gmail ou outras, pode participar como convidado no Teams.

Como administrador, você pode adicionar um novo usuário convidado à organização de algumas maneiras:

- Os administradores globais ou administradores do Teams e os proprietários de equipes adicionam um convidado a uma equipe nos clientes do Teams ou no centro de administração do Teams. Para saber mais, leia [Adicionar convidados a uma equipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f). Se você ainda não configurou o acesso de convidado, siga as etapas em [Colaborar com convidados em uma equipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).

- Adicione convidados à sua organização através da colaboração do Azure AD (Azure Active Directory) B2B. Para obter detalhes, consulte [o início rápido: adicionar usuários convidados ao seu diretório no portal do Azure](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).

Os administradores também podem delegar permissões para adicionar convidados para outras pessoas em sua organização, ao atribuir a função de Emissor do Convite. Para saber mais, confira [Habilitar colaboração externa B2b e gerenciar quem podem pode convidar pessoas](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).

Com a colaboração do Azure AD B2B, as organizações podem impor políticas de acesso condicional e autenticação multifator (MFA) para usuários B2B. Essas políticas podem ser impostas no nível do locatário, aplicativo ou usuário individual, da mesma maneira que podem ser habilitadas para membros e funcionários em tempo integral da organização. Essas políticas são aplicadas na organização de recursos. Para obter mais informações, consulte [Acesso condicional para usuários de colaboração B2B](https://go.microsoft.com/fwlink/?linkid=857454). Usuários convidados não podem ser bloqueados individualmente.

Os usuários convidados já adicionados por meio do Azure AD B2B, dos grupos do Microsoft 365 ou do SharePoint estão prontos para serem acessados. O administrador do Microsoft 365 ou um proprietário da equipe pode adicionar esses convidados às respectivas equipes. Se adicionar um convidado diretamente ao grupo do Microsoft 365 associado a uma equipe, o convidado receberá acesso à equipe, mas o grupo do 365 da Microsoft não gerará um email de convite para o convidado, para que alguém da equipe notifique o convidado.

> [!NOTE]
> Os convidados estão sujeitos aos limites de serviço do [Microsoft 365 ou Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) e do [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).

Você pode acompanhar adições de convidados no Azure AD ou no Centro de segurança do Microsoft 365. A adição de um convidado no Microsoft Teams é auditada e registrada como uma atividade de administração de grupo do Azure AD: “Adicionou membro a grupo”. Para obter mais detalhes, consulte [auditar e relatar um usuário de colaboração B2B](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) e [Pesquisar o log de auditoria no centro de conformidade](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).


## <a name="related-topics"></a>Tópicos relacionados

[Autorizar o acesso para convidado no Microsoft Teams](teams-dependencies.md)

[Ativar ou desativar o acesso a convidados no Microsoft Teams](set-up-guests.md)
