---
title: Acesso para convidado no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: O acesso de convidados no Microsoft Teams permite que as equipes da sua organização colaborem com pessoas de fora da sua organização, lhes concedendo acesso a equipes e a canais.
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c025e408842c3d883112b7c99d930fc77db47435
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2020
ms.locfileid: "44867968"
---
<a name="guest-access-in-microsoft-teams"></a>Acesso para convidado no Microsoft Teams
======================================

O acesso de convidados permite que você adicione usuários individuais de fora da sua organização às suas equipes e canais no Microsoft Teams. 

Para comparar o acesso externo (federação) com o acesso de convidados (e decidir qual deles usar), leia [Comunicar-se com usuários de outras organizações no Teams](communicate-with-users-from-other-organizations.md).

Se você estiver pronto para ativar o acesso de convidados em sua organização, comece com a [Lista de verificação de acesso de convidados](guest-access-checklist.md).

## <a name="guest-access-overview"></a>Visão geral do acesso de convidados

O acesso de convidados permite que as equipes da sua organização colaborem com pessoas de fora da sua organização, concedendo-lhes acesso às equipes e canais existentes no Teams. Qualquer pessoa com uma conta de email corporativa ou de consumidor, como do Outlook, Gmail ou outras, pode participar como convidado no Microsoft Teams, com acesso total a chats, reuniões e arquivos de equipe. Como administrador do Teams, você controla quais recursos os convidados podem (e não podem) usar no Teams - confira [Gerenciar acesso de convidados](manage-guests.md).

O acesso de convidados é uma configuração em toda a organização no Teams e está desativado por padrão. O acesso de convidados está sujeito aos limites de serviço do Azure AD e do Microsoft 365 ou Office 365.


> [!IMPORTANT]
> Os usuários convidados seguem as configurações em toda a organização do Teams para o modo de atualização de coexistência. Isso não pode ser alterado.

## <a name="licensing-for-guest-access"></a>Licenciamento para acesso de convidados

O acesso de convidados está incluído em todas as assinaturas do Microsoft 365 Business Standard, do Office 365 Enterprise e do Office 365 Education. Não é necessária nenhuma licença adicional do Microsoft 365 ou Office 365. O Teams não restringe o número de convidados que você pode adicionar. No entanto, o número total de convidados que podem ser adicionados ao seu locatário é baseado no que o licenciamento do seu Azure AD permite - normalmente, 5 convidados por usuário licenciado. Para obter mais informações, confira [Licenciamento de colaboração B2B do Azure AD](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).


> [!NOTE]
> Os usuários em sua organização que possuem apenas planos de assinatura autônomos do Microsoft 365 ou Office 365, como o Exchange Online Plano 2, não podem ser convidados para participar da sua organização porque o Teams considera que esses usuários pertencem à mesma organização. Para esses usuários usarem o Teams, eles devem receber uma assinatura do Microsoft 365 Business Standard, do Office 365 Enterprise ou do Office 365 Education. 

## <a name="who-is-a-guest"></a>Quem é um convidado?

Convidado é alguém que não é um funcionário, aluno ou membro da sua organização. Eles não têm uma conta escolar nem de trabalho com a sua organização. Por exemplo, convidados podem incluir parceiros, revendedores, fornecedores ou consultores. Qualquer pessoa que não faça parte da sua organização pode ser adicionada como convidado no Teams. Isso significa que qualquer pessoa com uma conta comercial (ou seja, uma conta do Azure Active Directory) ou uma conta de email de consumidor (com Outlook.com, Gmail.com ou outros) pode participar como convidado no Teams, com acesso total a equipes e experiências de canal.

Para saber mais sobre o que um convidado pode ou não fazer, leia [Autorizar o acesso de convidados no Microsoft Teams](teams-dependencies.md). Ou confira a tabela [comparação de recursos de membros e de convidados da equipe](guest-experience.md#comparison-of-team-member-and-guest-capabilities). 

Por fim, todos os convidados no Teams estão cobertos pela mesma proteção de conformidade e auditoria que o restante do Microsoft 365 e Office 365 e podem ser gerenciados com segurança no Azure AD.

## <a name="why-use-guest-access"></a>Por que usar o acesso de convidados?

Com o acesso de convidados, as organizações que usam o Teams podem fornecer acesso externo às equipes, documentos em canais, recursos, chats e aplicativos para seus parceiros, enquanto mantêm controle total sobre seus próprios dados corporativos. Todos os convidados no Teams estão cobertos pela mesma proteção de conformidade e auditoria que o restante do Microsoft 365 e Office 365, e os convidados podem ser gerenciados com segurança no Azure AD.  

## <a name="understand-the-limitations-for-guests"></a>Compreender as limitações de convidados

A experiência de convidado tem limitações por padrão. Compreenda a experiência de convidado para não tentar corrigir algo que não seja um problema. Por exemplo, aqui está uma lista de algumas das funcionalidades que não estão disponíveis para um convidado no Microsoft Teams:

- OneDrive for Business
- Pesquisa de pessoas de fora do Teams
- Calendário, Reuniões Agendadas ou Detalhes da Reunião
- PSTN
- Organograma
- Criar ou revisar uma equipe
- Procurar uma esquipe
- Carregar arquivos para um chat de pessoa para pessoa
- Atualmente, o Teams é compatível apenas aos usuários convidados do Estado 1 e Estado 2, [conforme definido pelo Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)

Para obter uma lista completa do que um convidado pode ou não fazer no Teams, confira a tabela [comparação de recursos de membros e de convidados da equipe](guest-experience.md#comparison-of-team-member-and-guest-capabilities). Para saber mais sobre o acesso de convidados nos níveis do Microsoft 365 e Office 365, leia [Adicionar convidados aos Grupos do Microsoft 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).


## <a name="more-information"></a>Mais informações

[Entre em contato com o suporte para produtos para empresas - ajuda para administradores](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)  
[Acesso de convidados aos Grupos do Microsoft 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
