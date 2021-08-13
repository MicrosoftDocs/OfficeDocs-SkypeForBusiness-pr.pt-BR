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
- m365initiative-externalcollab
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: Os administradores podem aprender a adicionar novos convidados a uma organização Microsoft Teams clientes da área de trabalho e da Web e Azure Active Directory portal de colaboração B2B.
ms.openlocfilehash: 1525a389b5299491dc7d0de2adfd744d0d3437aff7fbeb5832cd37790ab24ffb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344390"
---
# <a name="add-a-guest-to-a-team"></a>Adicionar um convidado a uma equipe

Qualquer pessoa com uma conta de email corporativa ou de consumidor, como o Outlook, o Gmail ou outras, pode participar como convidado no Teams.

Como administrador, você pode adicionar um novo convidado à organização de algumas maneiras:

- Os administradores globais ou administradores do Teams e os proprietários de equipes adicionam um convidado a uma equipe nos clientes do Teams ou no centro de administração do Teams. Para saber mais, leia [Adicionar convidados a uma equipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f). Se você ainda não configurou o acesso de convidado, siga as etapas em [Colaborar com convidados em uma equipe](/microsoft-365/solutions/collaborate-as-team).

- Adicione convidados à sua organização através da colaboração do Azure AD (Azure Active Directory) B2B. Para obter detalhes, confira [Início rápido: Adicionar convidados ao diretório no portal do Azure](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).

Os administradores também podem delegar permissões para adicionar convidados para outras pessoas em sua organização, ao atribuir a função de Emissor do Convite. Para saber mais, confira [Habilitar colaboração externa B2b e gerenciar quem podem pode convidar pessoas](/azure/active-directory/external-identities/delegate-invitations).

Com a colaboração do Azure AD B2B, as organizações podem impor políticas de acesso condicional e autenticação multifator (MFA) para usuários B2B. Essas políticas podem ser impostas no nível do locatário, aplicativo ou usuário individual, da mesma maneira que podem ser habilitadas para membros e funcionários em tempo integral da organização. Essas políticas são aplicadas na organização de recursos. Para obter mais informações, consulte [Acesso condicional para usuários de colaboração B2B](/azure/active-directory/external-identities/conditional-access). Convidados individuais não podem ser bloqueados.

Os convidados que você já adicionou por meio do Azure AD B2B, Microsoft 365 grupos ou SharePoint estão prontos para ir. O Microsoft 365 administrador ou um proprietário de equipe pode adicionar esses convidados às suas respectivas equipes. Se você adicionar um convidado diretamente ao grupo de Microsoft 365 associado a uma equipe, o convidado terá acesso à equipe, mas o grupo Microsoft 365 não gera um email de convite para o convidado, portanto, alguém na equipe deve notificar o convidado.

> [!NOTE]
> Os convidados estão sujeitos aos limites de serviço do [Microsoft 365 ou Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) e do [Azure Active Directory](/azure/active-directory/external-identities/current-limitations).

Você pode acompanhar adições de convidados no Azure AD ou no Centro de segurança do Microsoft 365. A adição de um convidado no Microsoft Teams é auditada e registrada como uma atividade de administração de grupo do Azure AD: “Adicionou membro a grupo”. Para obter mais detalhes, consulte [Auditing and reporting a B2B collaboration user](/azure/active-directory/external-identities/auditing-and-reporting) and [Search the audit log in the compliance Center](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).


## <a name="related-topics"></a>Tópicos relacionados

[Autorizar o acesso para convidado no Microsoft Teams](teams-dependencies.md)

[Ativar ou desativar o acesso a convidados no Microsoft Teams](set-up-guests.md)