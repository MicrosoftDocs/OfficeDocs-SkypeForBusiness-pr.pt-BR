---
title: Como o Exchange e o Microsoft Teams interagem | Suporte da Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Sabia quais funcionalidades existem entre o Microsoft Teams e as diversas configurações do Exchange, como criar e entrar em equipes, criar canais e muito mais."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 9ca8b0489b5428c938eb7f62101b03fd9f442cbc
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2017
---
<a name="how-exchange-and-microsoft-teams-interact"></a>Como o Exchange e o Microsoft Teams interagem 
=========================================

Para a experiência completa com o Microsoft Teams, todos os usuários devem estar habilitados para o Exchange Online, para o SharePoint Online e para a criação de grupos no Office 365.

As caixas de correio dos usuários do Exchange não podem ficar hospedadas online nem no local. Os usuários hospedados no Exchange Online ou no Exchange Dedicated vNext podem usar todos os recursos do Microsoft Teams. Eles podem criar e entrar em equipes e canais, criar e visualizar reuniões, modificar fotos de perfil de usuário, adicionar e configurar conectores, guias e bots, além de poderem conversar via bate-papo e fazer chamadas.

Usuários hospedados no Exchange Online Dedicated – o Legacy ou o Exchange local precisam estar sincronizados com o Azure Active Directory para o Office 365. Eles podem criar e entrar em equipes e canais, adicionar e configurar guias e bots, conversar via bate-papo e fazer chamadas. No entanto, eles não podem modificar fotos de perfil de usuário, criar e visualizar reuniões, nem adicionar e configurar conectores. Eles podem receber mensagens de conectores configurados por outros usuários.

A tabela a seguir oferece informações para usuários com o Exchange Online hospedado em vários ambientes.

**Ações suportadas:** 

| A caixa de correio do usuário está hospedada em:   | Criar equipes   |Entrar em equipes|Criar canais|Criar e visualizar reuniões|Modificar fotos de perfil de usuário|Adicionar e configurar conectores|Adicionar e configurar guias|Adicionar e configurar bots|
|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Sim|Sim|Sim|Sim|Sim|Sim|Sim|Sim|
|**Exchange Online Dedicated vNext**|Sim|Sim|Sim|Sim|Sim|Sim|Sim|Sim|
|**Exchange Online Dedicated – Legacy** (Sincronização obrigatória com o Azure AD)|Sim|Sim|Sim|Não|Não|Não|Sim| Sim|
|**Exchange no local** (Sincronização obrigatória com o Azure AD)|Sim|Sim|Sim|Sim*|Não|Não|Sim|Sim|
                                                            
*\*Suporte para o Exchange 2016 CU3 e versões acima*

Informações adicionais:

-   O Microsoft Teams não tem suporte para o SharePoint no local.

-   O SharePoint Online é necessário para compartilhar e armazenar arquivos em conversas de equipe.

-   O OneDrive for Business é necessário para compartilhar e armazenar arquivos em bate-papos privados.

-   Se os usuários não forem designados e habilitados com as licenças do SharePoint Online, eles não terão o armazenamento OneDrive for Business no Office 365. O compartilhamento de arquivos continuará funcionando nos canais, mas os usuários não conseguirão compartilhar arquivos em bate-papos sem o armazenamento do OneDrive for Business no Office 365.

-   Os usuários devem estar habilitados para a criação do grupo do Office 365 para criar equipes no Microsoft Teams.

-   No Microsoft Teams, os recursos de segurança e conformidade, como o eDiscovery, o Content Search, arquivamento e retenção legal, funcionam melhor nos ambientes do Exchange Online e do SharePoint Online. Para conversas em canais, as mensagens serão rastreadas para a caixa de correio de grupo no Exchange Online, onde estão disponíveis para o eDiscovery. Se o SharePoint Online e o OneDrive for Business (usando contas de trabalho ou escolares) estiverem habilitados em toda a organização e para os usuários, esses recursos de conformidade estarão disponíveis para todos os arquivos dentro do Teams também.

**Importante:**   Os usuários que participam de conversas que fazem parte da lista de bate-papo do Microsoft Teams precisam ter uma caixa de correio no Exchange Online (baseada em nuvem) para um administrador pesquisar as conversas de bate-papo. Isso ocorre porque as conversas que fazem parte da lista de bate-papo ficam armazenadas nas caixas de correio baseadas em nuvem dos participantes do bate-papo. Se um participante de bate-papo não tiver uma caixa de correio do Exchange Online, o administrador não poderá pesquisar nem fazer uma retenção das conversas de bate-papo. Por exemplo, em uma implantação híbrida do Exchange, os usuários com caixas de correio locais podem participar de conversas que fazem parte da lista de bate-papo do Microsoft Teams. Entretanto, nesse caso, o conteúdo dessas conversas não pode ser pesquisada e não pode ser colocada em retenção porque os usuários não possuem caixas de correio baseadas em nuvem. Para obter mais detalhes sobre as pesquisas de conteúdo e o Microsoft Teams, veja [*Microsoft Teams e Grupos do Office 365*](https://support.office.com/en-us/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).

**Dica:**   Para obter informações de como usar o Azure AD Connect para sincronizar com o Azure Active Directory, veja [*Integração de suas identidades locais com o Azure Active Directory*](https://go.microsoft.com/fwlink/?linkid=854600).
