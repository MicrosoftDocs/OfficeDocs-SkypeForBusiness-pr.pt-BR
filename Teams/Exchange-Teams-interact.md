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
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2806d913fb63dcd2a7a25b26153435333282e871
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752973"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Como o Exchange e o Microsoft Teams interagem

> [!Tip]
> Assista à sessão a seguir para saber como as equipes interagem com o Azure Active Directory (AAD), o Microsoft 365 Groups, o Exchange, o SharePoint e o OneDrive for Business: [noções básicas do Microsoft Teams](https://aka.ms/teams-foundations)

Para toda a experiência do Teams, todos os usuários devem ser habilitados para a criação de grupos do Exchange Online, do SharePoint Online e do Microsoft 365.

As caixas de correio dos usuários do Exchange não podem ficar hospedadas online nem no local. A integração com o Exchange local requer uma implantação híbrida do Exchange. Para obter mais informações sobre como configurar uma implantação híbrida, consulte [implantações híbridas do Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid).

Os usuários hospedados no Exchange Online ou no Exchange Dedicated vNext podem usar todos os recursos do Microsoft Teams. Eles podem criar e ingressar em equipes e canais, criar e exibir reuniões, ligar e bater papo, modificar imagens de perfil de usuário (se a política de caixa de correio do Outlook na Web permitir que elas façam isso) e adicionar e configurar conectores, guias e bots.

Os usuários hospedados no Exchange Online dedicado (Herdado) devem ser sincronizados com o Azure Active Directory no Microsoft 365 ou o Office 365. Eles podem criar e ingressar em equipes e canais, adicionar e configurar guias e bots e usar os recursos de chat e chamadas. No entanto, eles não podem modificar imagens de perfil, gerenciar reuniões, acessar contatos do Outlook ou gerenciar conectores.

Os usuários com caixas de correio hospedadas no local devem ser sincronizados com o Azure Active Directory. Eles podem usar todos os recursos no cenário acima, mas além disso, também podem alterar a imagem do perfil do usuário (se a política de caixa de correio do Outlook na Web permitir que elas façam isso) e gerenciar reuniões, fornecer o Exchange Server 2016 (atualização cumulativa 3), ou posterior, estiver em execução no local com o OAuth configurado (preferencialmente por meio do assistente de configuração híbrida do Exchange), conforme descrito em [Configurar a autenticação OAuth entre](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) Para habilitar a delegação de calendário para esses usuários, você também deve completar as etapas 2-3 conforme descrito em [Configurar a integração e o OAuth entre o Skype for Business Online e o Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises); essas etapas fornecerão ao aplicativo agendamento de equipe as permissões necessárias para confirmar as permissões de representante.

A tabela a seguir fornece uma referência rápida útil para a disponibilidade de recursos com base no ambiente do Exchange.

> [!NOTE]
> A integração de recursos entre o Exchange e o Teams locais requer uma implantação híbrida do Exchange. Esse requisito é além dos requisitos específicos de versão, chamados em alguns recursos da tabela a seguir.

**Ações suportadas:**

| A caixa de correio do usuário está hospedada em: | eDiscovery| &nbsp;Controle legal | Tention| Gerenciamento de canal e equipe |Criar e exibir reuniões no Microsoft Teams| Modificar fotos de perfil de usuário | Histórico de chamadas | Gerenciar contatos | Acessar contatos do Outlook | Caixa postal |Adicionar e configurar conectores|Adicionar e configurar guias|Adicionar e configurar bots|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Sim <sup>2</sup>|Sim <sup>2</sup>|Sim |Sim |Sim|Sim<sup>8</sup>|Sim |Sim|Sim <sup>7</sup>|Sim |Sim |Sim |Sim|
|**Exchange Online Dedicated vNext**|Sim <sup>2</sup>|Sim <sup>2</sup>|Sim |Sim |Sim|Sim<sup>8</sup>|Sim |Sim|Sim <sup>7</sup>|Sim |Sim |Sim |Sim|
|**Exchange Online Dedicated – Legacy** (Sincronização obrigatória com o Azure AD)|Sim <sup>2</sup>|Sim <sup>2, 3</sup>|Sim <sup> 4|Sim|Não|Não|Sim|Sim|Não|Sim <sup> 5|Sim <sup> 6|Sim |Sim|
|**Exchange no local** (sincronização com o Azure ad & a configuração OAuth necessária)|Sim <sup>2</sup>| Sim <sup>2</sup> |Sim <sup> 4|Sim|Sim (Exchange 2016 CU3 +)|Não|Sim|Sim|Não|Sim <sup> 5|Sim <sup> 6|Sim |Sim|

<sup>1</sup> suporte do Exchange 2016 Cu3 e versões mais recentes.  

<sup>2</sup> EDiscovery e retenção legal para conformidade com mensagens de canal são compatíveis com todas as opções de hospedagem.

<sup>3</sup> as equipes de chat privadas do teams ainda não têm suporte para o controle legal para essa opção de hospedagem.

<sup>4</sup> a retenção usará uma caixa de correio de sombra para o usuário online armazenar mensagens. [O Microsoft Teams dá suporte à descoberta eletrônica para usuários do teams em um ambiente híbrido do Exchange](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009).

<sup>cinco</sup> usuários do teams com caixa de correio local do Exchange podem usar o correio de voz com o Microsoft Teams e receber mensagens de correio de voz no Outlook, mas as mensagens de correio de voz não estarão disponíveis para exibição ou reprodução dentro do cliente da equipe.

<sup>6</sup> se um dos proprietários de uma equipe puder adicionar conectores, todos os outros participantes dessa equipe poderão fazer isso, mesmo se as caixas de correio estiverem hospedadas no local.

<sup>7</sup> somente contatos na pasta de contatos padrão. Não há suporte para o acesso a outras pastas de contatos ou subpastas.

<sup>8</sup> o Teams homenageia a configuração de [política de caixa de correio da Web do Outlook](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) configurada por administradores de locatários para controlar se os usuários podem alterar a imagem do seu perfil. Se a configuração **-SetPhotoEnabled** estiver desativada na política, os usuários não poderão adicionar, alterar ou remover a imagem do perfil dela. Por exemplo, se um usuário carregar uma imagem de perfil que foi aprovada pelo departamento de ti ou RH da sua organização, nenhuma ação será necessária. No entanto, se um usuário carregar uma imagem que não seja apropriada, altere a imagem de acordo com as políticas internas da sua organização.

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Requisitos para aproveitar ao máximo o Microsoft Teams

O Microsoft Teams funciona com vários serviços do Microsoft 365 e do Office 365 para fornecer aos usuários uma experiência avançada. Para dar suporte a essa experiência, você precisa habilitar certos recursos ou serviços e atribuir licenças.

- O SharePoint Online é necessário para compartilhar e armazenar arquivos em conversas de equipe. O Microsoft Teams não tem suporte para o SharePoint no local.

- Os usuários devem receber uma licença do SharePoint Online se desejam compartilhar arquivos em chats. Se os usuários não forem atribuídos e habilitados com as licenças do SharePoint Online, eles não terão o armazenamento do OneDrive for Business no Microsoft 365 ou no Office 365. O compartilhamento de arquivos continuará a funcionar em canais, mas os usuários não poderão compartilhar arquivos em chats sem o armazenamento do OneDrive for Business no Microsoft 365 ou no Office 365.

- Os usuários devem ser habilitados para criação de grupos do Microsoft 365 para criar equipes no Microsoft Teams.

- Para permitir que o Microsoft Teams funcione com o Exchange no local, você deve configurar o novo protocolo de autenticação OAuth do Exchange, de preferência, executando o assistente híbrido do Exchange, conforme descrito em [Configurar a autenticação OAuth entre as organizações Exchange e Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help). Para permitir que os usuários com a caixa de correio local do Exchange agendem reuniões de equipe em nome de outro usuário, você também deve completar as etapas 2-3 conforme descrito em [Configurar a integração e o OAuth entre o Skype for Business Online e o Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).

> [!NOTE]
> O suplemento do Outlook Teams pode ser usado para agendar uma reunião do teams para caixas de correio hospedadas no Exchange local. No entanto, o agendamento de uma reunião do teams em nome de outro usuário com o Exchange local requer o Exchange 2013 CU9 e superior e o novo protocolo de autenticação OAuth do Exchange. O delegado e o delegante devem ter uma caixa de correio no Exchange local.

> [!NOTE]
> Para a integração do Exchange local e das equipes, a licença necessária precisa ser atribuída para o usuário sincronizado do AAD.

> [!IMPORTANT]
> Se você desinstalar o cliente Skype for Business após mover um usuário para o modo **somente para equipes** , a presença poderá parar de funcionar no Outlook e em outros aplicativos do Office. A presença funciona bem no Microsoft Teams. Para solucionar esse problema, selecione a imagem do seu perfil no canto superior direito do Microsoft Teams e selecione **configurações**. Na guia **geral** , em **aplicativo**, selecione **registrar equipes como o aplicativo de chat do Office (requer a reinicialização de aplicativos do Office)**. Depois de selecionar essa opção, feche e abra novamente todos os aplicativos do Office, incluindo o Outlook. Depois de abrir o Outlook, as informações de presença estarão disponíveis.

## <a name="additional-considerations"></a>Considerações adicionais

Veja algumas coisas adicionais a serem lembradas ao implementar o Microsoft Teams em sua organização.

- No Microsoft Teams, os recursos de segurança e conformidade, como o eDiscovery, o Content Search, arquivamento e retenção legal, funcionam melhor nos ambientes do Exchange Online e do SharePoint Online. Para conversas em canais, as mensagens serão rastreadas para a caixa de correio de grupo no Exchange Online, onde estão disponíveis para o eDiscovery. Se o SharePoint Online e o OneDrive for Business (usando contas de trabalho ou escolares) estiverem habilitados em toda a organização e para os usuários, esses recursos de conformidade estarão disponíveis para todos os arquivos dentro do Teams também.

- Controlar e proteger a configuração de políticas de conformidade no Teams e no Exchange usando o acesso condicional. Para obter mais informações, consulte [como funcionam as políticas de acesso condicional do teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams) .

- Se a sua organização tiver requisitos de conformidade para garantir que todas as discussões na reunião sejam detectáveis, você deve desabilitar reuniões privadas se o organizador tiver uma caixa de correio local do Exchange.

- Em uma implantação híbrida do Exchange, o conteúdo de mensagens de chat é pesquisável, independentemente de os participantes do chat terem uma caixa de correio ou uma caixa de correio local baseada em nuvem. Para saber mais, leia [pesquisando caixas de correio baseadas em nuvem para usuários locais](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Para saber mais sobre como pesquisar conteúdo no Teams, leia [pesquisa de conteúdo no centro de conformidade do Microsoft 365](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

> [!TIP]
> Para obter informações sobre como usar o Azure AD Connect para sincronizar com o Azure Active Directory, confira [integrando suas identidades locais com o Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=854600).

## <a name="requirements-for-on-premises-exchange-mailbox-user"></a>Requisitos do usuário da caixa de correio do Exchange local

Se os usuários quiserem ter a funcionalidade de agendar uma reunião do Microsoft Teams usando o Exchange, você precisará garantir o seguinte:

- O delegado e o delegante devem ter uma caixa de correio no servidor Exchange.

- A descoberta automática (automática) V2 é necessária para permitir que o serviço Teams execute uma descoberta não autenticada da caixa de correio do usuário. A v2 automática tem suporte no Exchange 2013 CU19 +.

- O servidor Exchange deve ser configurado com o servidor de autenticação para EVOSTS. Isso é configurado automaticamente como parte do assistente híbrido para Exchange (HWA).

    Se você não quiser executar o HWA, poderá criar manualmente o servidor de autenticação para EVO STS no servidor Exchange seguindo estas instruções para [Configurar a autenticação OAuth entre as organizações Exchange e Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help). No entanto, recomendamos que você use o HWA.

- O servidor Exchange deve ter um aplicativo parceiro configurado com uma ID de aplicativo do **Skype for Business Online, 00000004-0000-0ff1-ce00-000000000000**. A ID é usada pelo serviço de agendamento de equipes e por uma conta de usuário vinculada que tem as seguintes propriedades:

  - Oculto do catálogo de endereços do Exchange. É uma prática recomendada ocultá-lo no catálogo de endereços porque é uma conta de usuário desabilitada.

  - Atribuição de função de gerenciamento do Exchange do **UserApplication**.

Para concluir a integração, siga as etapas 1-3 em [como configurar a autenticação OAuth entre as organizações Exchange e Exchange Online locais?](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help#how-do-you-configure-oauth-authentication-between-your-on-premises-exchange-and-exchange-online-organizations) Observe que a etapa 2 inclui a atribuição de função para ArchiveApplication que não é necessária para delegação, mas é para o arquivamento SfB chat online em uma caixa de correio do Exchange.
