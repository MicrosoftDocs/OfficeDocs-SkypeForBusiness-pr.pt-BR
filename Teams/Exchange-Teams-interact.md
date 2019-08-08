---
title: Como o Exchange e o Microsoft Teams interagem
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Sabia quais funcionalidades existem entre o Microsoft Teams e as diversas configurações do Exchange, como criar e entrar em equipes, criar canais e muito mais.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d89d9ed514eb5246911fe88d5fadc1af79caff1b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245079"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Como o Exchange e o Microsoft Teams interagem

> [!Tip]
> Assista à sessão a seguir para saber como as equipes interagem com o Azure Active Directory (AAD), o Office 365 Groups, o Exchange, o SharePoint e o OneDrive for Business: [bases do Microsoft Teams](https://aka.ms/teams-foundations)

Para a experiência completa com o Teams, todos os usuários devem estar habilitados para o Exchange Online, para o SharePoint Online e para a criação de grupos no Office 365.

As caixas de correio dos usuários do Exchange não podem ficar hospedadas online nem no local. Os usuários hospedados no Exchange Online ou no Exchange Dedicated vNext podem usar todos os recursos do Microsoft Teams. Eles podem criar e ingressar em equipes e canais, criar e visualizar reuniões, fazer chamadas e chats, modificar imagens do perfil do usuário, adicionar e configurar conectores, guias e bots.

Os usuários hospedados no Exchange Online Dedicated - Legacy ou no Exchange local precisam estar sincronizados com o Azure Active Directory para Office 365. Eles podem criar e entrar em equipes e canais, adicionar e configurar guias e bots, conversar via bate-papo e fazer chamadas. No entanto, eles não podem modificar imagens do perfil do usuário, nem adicionar e configurar conectores. Eles podem receber mensagens de conectores configurados por outros usuários. Para criar e exibir reuniões, há várias opções: É possível criar e exibir reuniões no Exchange 2016 cumulative update 3 (CU3) e superior, mas não nas versões anteriores ao Exchange 2016 CU3.

A tabela a seguir oferece informações para usuários com o Exchange Online hospedado em vários ambientes.

**Ações suportadas:**

| A caixa de correio do usuário está hospedada em: | eDiscovery| Controle&nbsp;legal | Tention| Gerenciamento de canal e equipe |Criar e visualizar reuniões| Modificar fotos de perfil de usuário | Histórico de chamadas | Gerenciar contatos | Acessar contatos do Outlook | Caixa postal |Adicionar e configurar conectores|Adicionar e configurar guias|Adicionar e configurar bots| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Sim <sup>2</sup>|Sim <sup>2</sup>|Sim |Sim|Sim|Sim|Sim|Sim|Sim|Sim|Sim|Sim |Sim|
|**Exchange Online Dedicated vNext**|Sim <sup>2</sup>|Sim <sup>2</sup>|Sim |Sim |Sim|Sim|Sim |Sim|Sim|Sim|Sim |Sim |Sim|
|**Exchange Online Dedicated – Legacy** (Sincronização obrigatória com o Azure AD)|Sim <sup>2</sup>|Sim <sup>2, 3</sup>|Sim <sup>4|Sim|Não|Não|Sim |Sim|Não|Sim <sup>5|Sim |Sim |Sim|
|**Exchange no local** (Sincronização obrigatória com o Azure AD)|Sim <sup>2</sup>| Sim <sup>2, 3</sup> |Sim <sup>4|Sim|Sim (Exchange 2016 CU3 +)|Sim (Exchange 2016 CU3 +)|Sim |Sim|Não|Sim <sup>5|Sim |Sim |Sim|

<sup>1</sup> Exchange 2016 Cu3 e acima com suporte  
<sup>2</sup> EDiscovery e retenção legal para conformidade com mensagens de canal são compatíveis com todas as opções de hospedagem.  
<sup>3</sup> as equipes de chat privadas do teams ainda não têm suporte para o controle legal para essa opção de hospedagem.

<sup>4</sup> a retenção usará uma caixa de correio de sombra para o usuário online armazenar mensagens. [O Microsoft Teams dá suporte à descoberta eletrônica para usuários do teams em um ambiente híbrido do Exchange](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009).

<sup>5</sup> os usuários do Microsoft Teams com a caixa de correio local do Exchange podem usar o correio de voz com o Microsoft Teams e receber mensagens de correio de voz no Outlook, mas as mensagens de correio de voz não estarão disponíveis para exibição ou reprodução dentro do cliente

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Requisitos para aproveitar ao máximo o Microsoft Teams

O Microsoft Teams funciona com vários serviços do Office 365 para fornecer aos usuários uma experiência avançada. Para dar suporte a essa experiência, você precisa habilitar certos recursos ou serviços e atribuir licenças.

- O SharePoint Online é necessário para compartilhar e armazenar arquivos em conversas de equipe. O Microsoft Teams não tem suporte para o SharePoint no local.

- Os usuários devem receber uma licença do SharePoint Online se desejam compartilhar arquivos em chats. Se os usuários não forem designados e habilitados com as licenças do SharePoint Online, eles não terão o armazenamento OneDrive for Business no Office 365. O compartilhamento de arquivos continuará funcionando nos canais, mas os usuários não conseguirão compartilhar arquivos em bate-papos sem o armazenamento do OneDrive for Business no Office 365.

- Os usuários devem estar habilitados para a criação do grupo do Office 365 para criar equipes no Microsoft Teams.

- Para permitir que o Microsoft Teams funcione com o Exchange local, você deve configurar o novo protocolo de autenticação OAuth do Exchange conforme descrito em [Configurar a autenticação OAuth entre as organizações Exchange e Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

> [!NOTE]
>Para a integração do Exchange local e das equipes, a licença necessária precisa ser atribuída para o usuário sincronizado do AAD.

## <a name="additional-considerations"></a>Considerações adicionais

Veja algumas coisas adicionais a serem lembradas ao implementar o Microsoft Teams em sua organização.

- No Microsoft Teams, os recursos de segurança e conformidade, como o eDiscovery, o Content Search, arquivamento e retenção legal, funcionam melhor nos ambientes do Exchange Online e do SharePoint Online. Para conversas em canais, as mensagens serão rastreadas para a caixa de correio de grupo no Exchange Online, onde estão disponíveis para o eDiscovery. Se o SharePoint Online e o OneDrive for Business (usando contas de trabalho ou escolares) estiverem habilitados em toda a organização e para os usuários, esses recursos de conformidade estarão disponíveis para todos os arquivos dentro do Teams também.

- Controlar e proteger a configuração de políticas de conformidade no Teams e no Exchange usando o acesso condicional. Para obter mais informações, consulte [como funcionam as políticas de acesso condicional do teams?](security-compliance-overview.md#how-do-conditional-access-policies-work-for-teams) .

- Se a sua organização tiver requisitos de conformidade para garantir que todas as discussões na reunião sejam detectáveis, você deve desabilitar reuniões privadas se o organizador tiver uma caixa de correio local do Exchange.

- Em uma implantação híbrida do Exchange, o conteúdo de mensagens de chat é pesquisável, independentemente de os participantes do chat terem uma caixa de correio ou uma caixa de correio local baseada em nuvem. Para saber mais, leia [pesquisando caixas de correio baseadas em nuvem para usuários locais no Office 365](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Para saber mais sobre como pesquisar conteúdo no Teams, leia [pesquisa de conteúdo no centro de conformidade do Office 365 Security &](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

> [!TIP]
> Para obter informações sobre como usar o Azure AD Connect para sincronizar com o Azure Active Directory, confira [integrando suas identidades locais com o Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=854600).
