---
title: Acesso para convidado no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
description: O acesso de convidados no Microsoft Teams permite que as equipes da sua organização colaborem com pessoas de fora da sua organização, lhes concedendo acesso a equipes e a canais.
ms.openlocfilehash: 266830f29f98d517450f4062ff23de9a7582a24f
ms.sourcegitcommit: 207e6aa97867e3fd80734cc839c0c5858bca24c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2020
ms.locfileid: "49476990"
---
# <a name="guest-access-in-microsoft-teams"></a>Acesso para convidado no Microsoft Teams

Com o acesso de convidado, você pode fornecer acesso a equipes, documentos em canais, recursos, chats e aplicativos para pessoas de fora da sua organização, mantendo o controle sobre os dados corporativos.

Convidado é alguém que não é um funcionário, aluno ou membro da sua organização. Eles não têm uma conta escolar nem de trabalho com a sua organização. Por exemplo, convidados podem incluir parceiros, revendedores, fornecedores ou consultores. Qualquer pessoa que não faça parte da sua organização pode ser adicionada como convidado no Teams. Isso significa que qualquer pessoa com uma conta empresarial (ou seja, uma conta do Azure Active Directory) ou uma conta de email do consumidor (com Outlook.com, Gmail.com ou outras) pode participar como um convidado no Teams, com acesso a equipes e experiências de canal.

Os convidados no Teams são cobertos pela mesma proteção de auditoria e conformidade que o restante do Microsoft 365 e podem ser gerenciados no Azure AD. O acesso de convidados está sujeito aos limites de serviço do Azure AD e do Microsoft 365 ou Office 365.

A experiência de convidado tem limitações por padrão. Para obter uma lista completa do que um convidado pode e não pode fazer no Teams, consulte [comparação de recursos de convidados e de membros da equipe](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

> [!IMPORTANT]
> Os usuários convidados seguem as configurações em toda a organização do Teams para o modo de atualização de coexistência. Isso não pode ser alterado.

Para configurar o acesso de convidado, confira [colaborar com convidados em uma equipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team). 

Para comparar o acesso externo (federação) com o acesso de convidados (e decidir qual deles usar), leia [Comunicar-se com usuários de outras organizações no Teams](communicate-with-users-from-other-organizations.md).

## <a name="set-up-guest-access"></a>Configurar o acesso de convidado

O acesso de convidado no Teams exige a configuração de outras configurações no Microsoft 365, incluindo configurações no Azure AD, grupos do Microsoft 365 e no SharePoint. Se você estiver pronto para começar a convidar convidados para o Microsoft Teams, leia um dos seguintes procedimentos:

- Para configurar o acesso de convidado para o Microsoft Teams para uso geral, consulte [colaborar com convidados em uma equipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).
- Para colaborar com uma organização parceira que usa o Azure Active Directory e permitir que os convidados se registrem automaticamente para acesso à equipe, consulte [criar uma extranet B2B com convidados gerenciados](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).

O acesso de convidado no Teams é uma configuração em toda a organização e está desativado por padrão. Você pode controlar o acesso de convidados a equipes individuais usando [Rótulos de sensibilidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

## <a name="how-a-guest-becomes-a-member-of-a-team"></a>Como um convidado se torna membro de uma equipe

1. Um proprietário de equipe ou um administrador do Microsoft 365 [adiciona um convidado a uma equipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. O convidado recebe um e-mail de boas-vindas do proprietário da equipe com informações sobre a equipe e o que esperar agora que é membro.
3. O convidado aceita o convite.
  Os usuários convidados que têm uma conta corporativa ou de estudante no Azure Active Directory podem aceitar o convite e autenticar diretamente. Outros usuários recebem um código de passagem única para validar sua identidade (necessária[autenticação de senha única](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) ).
4. Depois de aceitar o convite, o convidado pode [participar de equipes e de canais](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), receber e responder mensagens de canais, [acessar arquivos em canais](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), participar de bate-papos participar de reuniões, colaborar em documentos e muito mais. 

Nas equipes, os convidados são identificados de forma clara. O nome de um usuário convidado inclui o rótulo **(Convidado)** e o canal inclui um ícone para indicar que há convidados na equipe. Para obter mais detalhes, consulte [Como é a experiência do convidado](guest-experience.md)
  
Os convidados podem deixar a equipe a qualquer momento no Teams. Para obter detalhes, consulte [Como posso sair de uma equipe?](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)

> [!NOTE]
> Deixar a equipe não remove a conta de convidado do diretório de sua organização. Isso deve ser feito por um administrador global do Microsoft 365 ou um administrador do Azure AD.

## <a name="licensing-for-guest-access"></a>Licenciamento para acesso de convidado

O acesso de convidado está incluído em todas as assinaturas Microsoft 365 Business Standard, Microsoft 365 Enterprise e Microsoft 365 Education. Não é necessária nenhuma licença adicional da Microsoft 365. O Teams não restringe o número de convidados que você pode adicionar. No entanto, o número total de convidados que podem ser adicionados ao seu locatário pode ficar restrito pelos recursos pagos do Azure AD. Para obter mais informações, consulte [modelo de cobrança para identidades externas do Azure ad](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).

> [!NOTE]
> Os usuários em sua organização que têm planos de assinatura autônomos do Microsoft 365 apenas, como o Exchange Online Plan 2, não podem ser convidados como convidados para a sua organização porque as equipes consideram esses usuários pertencentes à mesma organização. Para esses usuários usarem o Teams, eles devem receber uma assinatura do Microsoft 365 Business Standard, do Office 365 Enterprise ou do Office 365 Education. 

## <a name="guest-access-reviews"></a>Análises de acesso de convidado

Você pode usar o Azure AD para criar uma revisão do Access para os membros do grupo ou usuários atribuídos a um aplicativo. Criar análises recorrentes do Access pode poupar tempo. Se precisar revisar rotineiramente os usuários que têm acesso a um aplicativo, a uma equipe ou a membros de um grupo, você pode definir a frequência dessas análises. 

Você também pode fazer uma crítica de acesso de convidado, pedir aos convidados que examinem sua própria associação ou peça ao proprietário do aplicativo ou ao responsável por decisões comerciais para executar a revisão do Access. Use o portal do Azure para executar análises de acesso de convidado. Para obter mais informações, consulte [gerenciar o acesso de convidados com as críticas do Azure ad Access](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).

## <a name="related-topics"></a>Tópicos relacionados

[Colaborar com pessoas de fora da sua organização](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Bloquear usuários convidados de um grupo específico do Microsoft 365 ou da equipe do Microsoft Teams](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Criar um ambiente de compartilhamento de convidado seguro](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

[Entre em contato com o suporte para produtos para empresas - ajuda para administradores](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[Configurar o Microsoft Teams com três níveis de proteção](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
