---
title: Acesso para convidado no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
description: O acesso de convidados no Microsoft Teams permite que as equipes da sua organização colaborem com pessoas de fora da sua organização, lhes concedendo acesso a equipes e a canais.
ms.openlocfilehash: f04fce7f75df32111b2577119c12b14eadf963b9
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761237"
---
# <a name="guest-access-in-microsoft-teams"></a>Acesso para convidado no Microsoft Teams

O acesso de convidados permite que as equipes da sua organização colaborem com pessoas de fora da sua organização, concedendo-lhes acesso às equipes e canais existentes no Teams. Qualquer pessoa com uma conta de email comercial ou de consumidor, como o Microsoft 365, o Outlook, o Gmail ou outros, pode participar como um convidado no Microsoft Teams com acesso total a chats, reuniões e arquivos de equipe. Como administrador do Teams, você controla quais recursos os convidados podem (e não podem) usar no Teams - confira [Gerenciar acesso de convidados](manage-guests.md).

Para comparar o acesso externo (federação) com o acesso de convidados (e decidir qual deles usar), leia [Comunicar-se com usuários de outras organizações no Teams](communicate-with-users-from-other-organizations.md).

O acesso de convidados é uma configuração em toda a organização no Teams e está desativado por padrão. (Você pode controlar o acesso de convidados a equipes individuais usando [Rótulos de sensibilidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).)

Se você estiver pronto para começar a convidar convidados para o Microsoft Teams, leia um dos seguintes procedimentos:

- Para configurar o acesso de convidado para o Microsoft Teams para uso geral, consulte [colaborar com convidados em uma equipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).
- Para colaborar com uma organização parceira que usa o Azure Active Directory e permitir que os convidados se registrem automaticamente para acesso à equipe, consulte [criar uma extranet B2B com convidados gerenciados](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).

O acesso de convidados está sujeito aos limites de serviço do Azure AD e do Microsoft 365 ou Office 365.

> [!IMPORTANT]
> Os usuários convidados seguem as configurações em toda a organização do Teams para o modo de atualização de coexistência. Isso não pode ser alterado.

## <a name="licensing-for-guest-access"></a>Licenciamento para acesso de convidados

O acesso de convidados está incluído em todas as assinaturas do Microsoft 365 Business Standard, do Office 365 Enterprise e do Office 365 Education. Não é necessária nenhuma licença adicional do Microsoft 365 ou Office 365. O Teams não restringe o número de convidados que você pode adicionar. No entanto, o número total de convidados que podem ser adicionados ao seu locatário pode ficar restrito pelos recursos pagos do Azure AD. Para obter mais informações, confira [Licenciamento de colaboração B2B do Azure AD](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).


> [!NOTE]
> Os usuários em sua organização que possuem apenas planos de assinatura autônomos do Microsoft 365 ou Office 365, como o Exchange Online Plano 2, não podem ser convidados para participar da sua organização porque o Teams considera que esses usuários pertencem à mesma organização. Para esses usuários usarem o Teams, eles devem receber uma assinatura do Microsoft 365 Business Standard, do Office 365 Enterprise ou do Office 365 Education. 

## <a name="who-is-a-guest"></a>Quem é um convidado?

Convidado é alguém que não é um funcionário, aluno ou membro da sua organização. Eles não têm uma conta escolar nem de trabalho com a sua organização. Por exemplo, convidados podem incluir parceiros, revendedores, fornecedores ou consultores. Qualquer pessoa que não faça parte da sua organização pode ser adicionada como convidado no Teams. Isso significa que qualquer pessoa com uma conta comercial (ou seja, uma conta do Azure Active Directory) ou uma conta de email de consumidor (com Outlook.com, Gmail.com ou outros) pode participar como convidado no Teams, com acesso total a equipes e experiências de canal.

Para saber mais sobre o que um convidado pode ou não fazer, leia [Autorizar o acesso de convidados no Microsoft Teams](teams-dependencies.md). Ou confira a tabela [comparação de recursos de membros e de convidados da equipe](guest-experience.md#comparison-of-team-member-and-guest-capabilities). 

Por fim, todos os convidados do teams são cobertos pela mesma proteção de auditoria e conformidade que o restante do Microsoft 365 e podem ser gerenciados no Azure AD.

## <a name="why-use-guest-access"></a>Por que usar o acesso de convidados?

Com o acesso de convidados, as organizações que usam o Teams podem fornecer acesso externo às equipes, documentos em canais, recursos, chats e aplicativos para seus parceiros, enquanto mantêm controle total sobre seus próprios dados corporativos. 

## <a name="understand-the-limitations-for-guests"></a>Compreender as limitações de convidados

A experiência de convidado tem limitações por padrão. Compreenda a experiência de convidado para não tentar corrigir algo que não seja um problema. Aqui está uma lista de algumas das funcionalidades que não estão disponíveis para um convidado no Microsoft Teams:

- OneDrive
- Pesquisa de pessoas de fora do Teams
- Calendário, Reuniões Agendadas ou Detalhes da Reunião
- PSTN
- Organograma
- Criar ou revisar uma equipe
- Procurar uma esquipe
- Carregar arquivos para um chat de pessoa para pessoa
- Atualmente, o Teams oferece suporte somente para [os tipos de usuários convidados do estado 1 e do estado 2](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)

Para obter uma lista completa do que um convidado pode ou não fazer no Teams, confira a tabela [comparação de recursos de membros e de convidados da equipe](guest-experience.md#comparison-of-team-member-and-guest-capabilities). Para saber mais sobre o acesso de convidados no nível do Microsoft 365, leia [colaborando com pessoas de fora da sua organização](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization).


## <a name="related-topics"></a>Tópicos relacionados

[Entre em contato com o suporte para produtos para empresas - ajuda para administradores](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[Configurar o Microsoft Teams com três níveis de proteção](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
