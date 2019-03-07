---
title: Como o Exchange e o Microsoft Teams interagem
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: crowe
description: Sabia quais funcionalidades existem entre o Microsoft Teams e as diversas configurações do Exchange, como criar e entrar em equipes, criar canais e muito mais.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 020204700101e086691004cb90b5e5f7eabdbe5a
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462184"
---
<a name="how-exchange-and-microsoft-teams-interact"></a>Como o Exchange e o Microsoft Teams interagem 
=========================================

> [!Tip]
> Assista a sessão a seguir para saber como equipes interage com o Windows Azure Active Directory (AAD), grupos do Office 365, Exchange, SharePoint e OneDrive for Business: [Fundamentos das equipes da Microsoft](https://aka.ms/teams-foundations)

Para a experiência completa com o Microsoft Teams, todos os usuários devem estar habilitados para o Exchange Online, para o SharePoint Online e para a criação de grupos no Office 365.

As caixas de correio dos usuários do Exchange não podem ficar hospedadas online nem no local. Os usuários hospedados no Exchange Online ou no Exchange Dedicated vNext podem usar todos os recursos do Microsoft Teams. Eles podem criar e ingressar em equipes e canais, criar e visualizar reuniões, fazer chamadas e chats, modificar imagens do perfil do usuário, adicionar e configurar conectores, guias e bots.

Os usuários hospedados no Exchange Online Dedicated - Legacy ou no Exchange local precisam estar sincronizados com o Azure Active Directory para Office 365. Eles podem criar e entrar em equipes e canais, adicionar e configurar guias e bots, conversar via bate-papo e fazer chamadas. No entanto, eles não podem modificar imagens do perfil do usuário, nem adicionar e configurar conectores. Eles podem receber mensagens de conectores configurados por outros usuários. Para criar e exibir reuniões, há várias opções: É possível criar e exibir reuniões no Exchange 2016 cumulative update 3 (CU3) e superior, mas não nas versões anteriores ao Exchange 2016 CU3.

A tabela a seguir oferece informações para usuários com o Exchange Online hospedado em vários ambientes.

**Ações suportadas:** 

| A caixa de correio do usuário está hospedada em: | eDiscovery| Ofício&nbsp;bloqueio | Retenção| Mgmt de equipe e de canal |Criar e visualizar reuniões| Modificar fotos de perfil de usuário | Histórico de chamadas | Gerenciar contatos | Acessar os contatos do Outlook | Caixa postal |Adicionar e configurar conectores|Adicionar e configurar guias|Adicionar e configurar bots| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Sim <sup>2</sup>|Sim <sup>2</sup>|Sim |Sim|Sim|Sim|Sim|Sim|Sim|Sim|Sim|Sim |Sim|
|**Exchange Online Dedicated vNext**|Sim <sup>2</sup>|Sim <sup>2</sup>|Sim |Sim |Sim|Sim|Sim |Sim|Sim|Sim|Sim |Sim |Sim |
|**Exchange Online Dedicated – Legacy** (Sincronização obrigatória com o Azure AD)|Sim <sup>2</sup>|Sim <sup>2,3</sup>|Sim <sup>4|Sim|Não|Não|Sim|Sim |Não|Sim <sup>5|Sim |Sim |Sim|
|**Exchange no local** (Sincronização obrigatória com o Azure AD)|Sim <sup>2</sup>| Sim <sup>2,3</sup> |Sim <sup>4|Sim|Sim (Exchange 2016 CU3 +)|Sim (Exchange 2016 CU3 +)|Sim |Sim |Não|Sim <sup>5|Sim |Sim |Sim |

<sup>1</sup> do exchange 2016 CU3 e acima suportados  
<sup>2</sup> eDiscovery e retenção Legal para fins de conformidade em mensagens de canal é suportado para todas as opções de hospedagem.  
<sup>3</sup> mensagens de bate-papo privado equipes ainda não são aceitas para a retenção Legal para essa opção de hospedagem.

<sup>4</sup> retenção usará uma caixa de correio de sombra para o usuário online para armazenar mensagens. [EDiscovery suporta de equipes da Microsoft para o usuário de equipes em um ambiente híbrido do Exchange](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009).

<sup>5</sup> usuários de equipes com no local de caixa de correio do Exchange pode usar a caixa postal com equipes e receber mensagens da caixa postal no Outlook, mas as mensagens da caixa postal não estará disponíveis para visualizar ou reproduzir no cliente equipes.

Informações adicionais:

-   O Microsoft Teams não tem suporte para o SharePoint no local.

-   O SharePoint Online é necessário para compartilhar e armazenar arquivos em conversas de equipe.

-   O OneDrive for Business é necessário para compartilhar e armazenar arquivos em bate-papos privados.

-   Se os usuários não forem designados e habilitados com as licenças do SharePoint Online, eles não terão o armazenamento OneDrive for Business no Office 365. O compartilhamento de arquivos continuará funcionando nos canais, mas os usuários não conseguirão compartilhar arquivos em bate-papos sem o armazenamento do OneDrive for Business no Office 365.

-   Os usuários devem estar habilitados para a criação do grupo do Office 365 para criar equipes no Microsoft Teams.

-   No Microsoft Teams, os recursos de segurança e conformidade, como o eDiscovery, o Content Search, arquivamento e retenção legal, funcionam melhor nos ambientes do Exchange Online e do SharePoint Online. Para conversas em canais, as mensagens serão rastreadas para a caixa de correio de grupo no Exchange Online, onde estão disponíveis para o eDiscovery. Se o SharePoint Online e o OneDrive for Business (usando contas de trabalho ou escolares) estiverem habilitados em toda a organização e para os usuários, esses recursos de conformidade estarão disponíveis para todos os arquivos dentro do Teams também.

-   Para o Exchange local, você deve configurar o novo protocolo de autenticação OAuth do Exchange, conforme descrito em [Configure OAuth authentication entre organizações do Exchange e o Exchange Online](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx). 

> [!NOTE]
> No momento, se sua organização tiver exigências de conformidade para garantir que todas as discussões nas reuniões sejam detectáveis, é necessário desabilitar as reuniões privadas se o organizador tiver uma caixa de correio no Exchange.
> 
> [!IMPORTANT]
> Em uma implantação híbrida do Exchange, conteúdo de mensagens de chat é pesquisável independentemente de terem participantes de bate-papo com uma caixa de correio baseadas em nuvem ou local. Para saber mais, leia [Searching caixas de correio baseadas em nuvem para usuários no Office 365 local](https://docs.microsoft.com/en-us/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Para saber sobre a procura por conteúdo em equipes, leia a [Pesquisa de conteúdo no Centro de conformidade do & de segurança do Office 365](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).
> 
> [!TIP]
> Para obter informações sobre como usar o Connect do Azure AD para sincronizar com o Windows Azure Active Directory, consulte [integrando suas identidades no local com o Windows Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=854600).
