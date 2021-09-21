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
ms.localizationpriority: high
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
ms.openlocfilehash: aa14fc3a59d893b152f96d31a20c46119f8a71f9
ms.sourcegitcommit: cf2f96dbd485ac4cc822c5a591ccce6b47f12cc7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2021
ms.locfileid: "59456331"
---
# <a name="guest-access-in-microsoft-teams"></a>Acesso para convidado no Microsoft Teams

Com o acesso de convidado, você pode fornecer acesso às equipes, documentos em canais, recursos, chats e aplicativos para pessoas fora da sua organização, enquanto mantêm controle total sobre seus próprios dados corporativos. Confira [Configurar colaboração segura com Microsoft 365 e Microsoft Teams](/microsoft-365/solutions/setup-secure-collaboration-with-teams).

> [!NOTE]
> Se você deseja encontrar, ligar, conversar e marcar reuniões com pessoas de outras organizações, use o [acesso externo](manage-external-access.md).

Convidado é alguém que não é um funcionário, aluno ou membro da sua organização. Eles não têm uma conta escolar nem de trabalho com a sua organização. Por exemplo, convidados podem incluir parceiros, revendedores, fornecedores ou consultores. Qualquer pessoa que não faça parte da sua organização pode ser adicionada como convidado no Teams. Isso significa que qualquer pessoa com uma conta comercial (ou seja, uma conta do Azure Active Directory) ou uma conta de email de consumidor (com Outlook.com, Gmail.com ou outros) pode participar como convidado no Teams, com acesso total a equipes e experiências de canal.

Os convidados no Teams estão cobertos pela mesma proteção de conformidade e auditoria que o restante do Microsoft 365, e podem ser gerenciados no Azure AD. O acesso de convidados está sujeito aos limites de serviço do Azure AD e do Microsoft 365 ou Office 365.

A experiência de convidado tem limitações por padrão. Para obter uma lista completa do que um convidado pode ou não fazer no Teams, consulte [comparação de recursos de membros e de convidados da equipe](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

> [!IMPORTANT]
> Os convidados seguem as configurações de Toda a organização do Teams para o modo de atualização de coexistência. Isso não pode ser alterado.

Para configurar o acesso de convidado, consulte [Colaborar com convidados em uma equipe](/microsoft-365/solutions/collaborate-as-team). 

Para comparar o acesso externo (federação) com o acesso de convidados (e decidir qual deles usar), leia [Comunicar-se com usuários de outras organizações no Teams](communicate-with-users-from-other-organizations.md).

## <a name="set-up-guest-access"></a>Configurar o acesso de convidado

O acesso de convidado no Teams requer a definição de outras configurações no Microsoft 365, incluindo configurações no Azure AD, Grupos do Microsoft 365 e SharePoint. Se você estiver pronto para começar a convidar pessoas para equipes, leia um dos seguintes:

- Para configurar o acesso de convidado do Teams para uso geral, consulte [Colaborar com convidados em uma equipe](/microsoft-365/solutions/collaborate-as-team).
- Para colaborar com uma organização parceira que usa o Azure Active Directory e permitir que os convidados se inscrevam para acesso da equipe, consulte [Criar uma extranet B2B com convidados gerenciados](/microsoft-365/solutions/b2b-extranet).

O acesso de convidado no Teams é uma configuração para toda a organização e está desativado por padrão. Você pode controlar o acesso de convidados a equipes individuais usando [rótulos de confidencialidade](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

### <a name="turning-guest-access-off"></a>Desativando o acesso de convidado

Se você desativar o acesso de convidados no Teams, os convidados existentes perderão o acesso à equipe. No entanto, eles não são removidos da equipe. Eles ainda estão visíveis para os membros da equipe e podem ser @mencionados. Se você ativar o acesso de convidado do Teams novamente, eles recuperarão o acesso.

Se você planeja deixar o acesso de convidados desativado, convém avisar os proprietários da equipe para remover manualmente as contas de convidado de suas equipes. Embora esses convidados não tenham acesso, ter suas contas visíveis na equipe pode causar confusão para outros membros da equipe.

## <a name="how-a-guest-becomes-a-member-of-a-team"></a>Como um convidado se torna membro de uma equipe

1. Um proprietário de equipe ou um administrador do Microsoft 365 [adiciona um convidado a uma equipe.](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. O convidado recebe um e-mail de boas-vindas do proprietário da equipe com informações sobre a equipe e o que esperar agora que é membro.
3. O convidado aceita o convite.
  Os convidados que têm uma conta de trabalho ou escolar no Azure Active Directory podem aceitar o convite e se autenticar diretamente. Outros usuários recebem uma senha de uso único para validar sua identidade ([Autenticação de senha de uso único ](/azure/active-directory/external-identities/one-time-passcode) necessária).
4. Depois de aceitar o convite, o convidado pode [participar de equipes e de canais](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), receber e responder mensagens de canais, [acessar arquivos em canais](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), participar de bate-papos participar de reuniões, colaborar em documentos e muito mais. 

Nas equipes, os convidados são identificados de forma clara. O nome de um convidado inclui o rótulo **(Convidado)**, e um canal inclui um ícone para indicar que há convidados na equipe. Para obter mais detalhes, consulte [Como é a experiência do convidado](guest-experience.md)
  
Os convidados podem deixar a equipe a qualquer momento no Teams. Para obter detalhes, consulte [Como posso sair de uma equipe?](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)

> [!NOTE]
> Sair da equipe não remove a conta de convidado do diretório da organização. Isso deve ser feito por um administrador global do Microsoft 365 ou um administrador do Azure AD.

## <a name="licensing-for-guest-access"></a>Licenciamento para acesso de convidado

O acesso de convidados está incluído em todas as assinaturas do Microsoft 365 Business Standard, do Microsoft 365 Enterprise e do Microsoft 365 Education. Não é necessária nenhuma licença adicional do Microsoft 365. O [modelo de cobrança para Identidades Externas do Azure AD](/azure/active-directory/b2b/licensing-guidance) aplica-se aos convidados no Microsoft 365. Somente pessoas de fora da sua organização podem ser convidadas como convidados.

## <a name="guest-access-reviews"></a>Comentários de acesso de convidados

Você pode usar o Azure AD para criar uma revisão de acesso para membros do grupo ou usuários atribuídos a um aplicativo. A criação de revisões de acesso recorrentes pode economizar seu tempo. Se você precisar revisar rotineiramente os usuários que têm acesso a um aplicativo, equipe ou membros de um grupo, poderá definir a frequência dessas revisões. 

Você mesmo pode realizar uma revisão de acesso de convidado, pedir aos convidados que revisem a própria assinatura ou pedir a um proprietário de aplicativo ou tomador de decisões de negócios para realizar a revisão de acesso. Use o portal do Azure para realizar análises de acesso de convidado. Para obter mais informações, consulte [Gerenciar o acesso de convidado com análises de acesso do Azure AD](/azure/active-directory/governance/manage-guest-access-with-access-reviews).

## <a name="related-topics"></a>Tópicos relacionados

[Colaborar com pessoas fora de sua organização](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Bloquear convidados de um grupo específico do Microsoft 365 ou equipe do Microsoft Teams](/microsoft-365/solutions/per-group-guest-access)

[Criar um ambiente de compartilhamento de convidados seguro](/microsoft-365/solutions/create-secure-guest-sharing-environment)

[Entre em contato com o suporte de produtos para empresas - Ajuda da Administração](/microsoft-365/admin/contact-support-for-business-products)

[Configure o Teams com três níveis de proteção](/microsoft-365/solutions/configure-teams-three-tiers-protection)
