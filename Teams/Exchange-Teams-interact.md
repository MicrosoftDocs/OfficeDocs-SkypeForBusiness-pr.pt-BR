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
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c1ade306ab1a9dc3c3f716b36d931bcf7a6d0b41
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711495"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Como o Exchange e o Microsoft Teams interagem

> [!Tip]
> Assista à seguinte sessão para saber como as equipes interagem com o Azure Active Directory (AAD), o Microsoft 365 Groups, o Exchange, o SharePoint e o OneDrive for Business: [Fundamentos do Microsoft Teams](https://aka.ms/teams-foundations)

Para a experiência completa com o Teams, todos os usuários devem estar habilitados para o Exchange Online, SharePoint Online e para a criação no Microsoft 365 Group.

As caixas de correio dos usuários do Exchange não podem ficar hospedadas online nem no local.

Os usuários hospedados no Exchange Online ou no Exchange Dedicated vNext podem usar todos os recursos do Microsoft Teams. Eles podem criar e integrar equipes e canais, criar e visualizar reuniões, ligar e conversar, modificar imagens de perfil de usuário (se a política de caixa de correio do Outlook na Web permitir que eles façam isso) e adicionar e configurar conectores, guias e bots. Para obter uma lista mais abrangente de recursos disponíveis, confira a tabela abaixo.

Os usuários hospedados no Exchange Online dedicado (Herdado) devem ser sincronizados com o Azure Active Directory no Microsoft 365 ou Office 365. Eles podem criar e entrar em equipes e canais, adicionar e configurar guias e bots, conversar via bate-papo e fazer chamadas. No entanto, eles não podem modificar imagens de perfil, gerenciar reuniões, acessar contatos do Outlook ou gerenciar conectores.

> [!IMPORTANT]
> Para integração com o local, é altamente recomendável que você tenha uma implantação Híbrida clássica Completa do Exchange com o Exchange Server 2016 ou posterior. O suporte Híbrido Moderno fica limitado a disponibilidade e não fornecerá integração de calendário do Teams para caixas de correio locais, por exemplo. Para obter mais informações sobre configurar uma implantação híbrida, consulte [implantação do Exchange Server Híbrido](/exchange/exchange-hybrid).

Os usuários com caixas de correio hospedadas no local devem ser sincronizados com o Azure Active Directory. Eles podem usar todos os recursos no cenário acima, mas, além disso, eles podem gerenciar as reuniões se os requisitos listados na seção [Requisitos para caixas de correio hospedadas no local](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) forem atendidos.

A tabela a seguir fornece uma referência rápida útil para a disponibilidade de recursos com base no ambiente do Exchange.

**Ações suportadas:**

| A caixa de correio do usuário está hospedada em:                                       | Descoberta eletrônica         | Bloqueio&nbsp;Legal    | Retenção        | Gerenciamento de Canal e Equipe | Criar e exibir reuniões no Teams | Modificar fotos de perfil de usuário | Histórico de chamadas | Gerenciar contatos | Acessar Contatos do Outlook | Caixa postal        | Adicionar e configurar conectores | Adicionar e configurar guias | Adicionar e configurar bots |
|--------------------------------------------------------------------|--------------------|--------------------|------------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                | Sim <sup>1</sup>   | Sim <sup>1</sup>   | Sim              | Sim                   | Sim                               | Sim<sup>7</sup>             | Sim          | Sim             | Sim <sup>6</sup>        | Sim              | Sim                          | Sim                    | Sim                    |
| **Exchange Online Dedicated vNext**                                | Sim <sup>1</sup>   | Sim <sup>1</sup>   | Sim              | Sim                   | Sim                               | Sim<sup>7</sup>             | Sim          | Sim             | Sim <sup>6</sup>        | Sim              | Sim                          | Sim                    | Sim                    |
| **Exchange Online Dedicated – Legacy** (Sincronização obrigatória com o Azure AD) | Sim <sup>1</sup>   | Sim <sup>(1,2)</sup> | Sim <sup>3</sup> | Sim                   | Não                                | Não                          | Sim          | Sim             | Não                      | Sim <sup>4</sup> | Sim <sup>5</sup>             | Sim                    | Sim                    |
| **Exchange no local** (sincronizar com o Azure AD)                        | Sim <sup>1,9</sup> | Sim <sup>1</sup>   | Sim <sup>3</sup> | Sim                   | Sim <sup>8</sup>                  | <sup>Sim10</sup>            | Sim          | Sim             | Não                      | Sim <sup>4</sup> | Sim <sup>5</sup>             | Sim                    | Sim                    |

<sup>1</sup> Descoberta eletrônica e Retenção legal para conformidade nas mensagens de canal têm suporte para todas as opções de hospedagem.

<sup>2</sup> As mensagens privadas de chat do Teams ainda não têm suporte para essa opção de hospedagem.

<sup>3</sup> A retenção usará uma caixa de correio de sombra para que o usuário online armazene mensagens.

<sup>4</sup> Usuários do Teams com a caixa de correio local do Exchange podem usar a caixa postal com o Teams e receber mensagens de caixa postal no Outlook, mas as mensagens de caixa postal não estarão disponíveis para exibição ou reprodução dentro do cliente do Teams.

<sup>5</sup> Se um dos proprietários de uma equipe pode adicionar conectores, todas as outras pessoas da equipe poderão fazê-lo, mesmo que as caixas de correio sejam hospedadas no local.

<sup>6</sup> Somente contatos na pasta de contatos padrão. Não há suporte para o acesso a outras pastas de contatos ou subpastas.

<sup>7</sup>O Teams respeita a configuração da [Política de caixa de correio do Outlook na Web](/powershell/module/exchange/client-access/set-owamailboxpolicy) configurada pelos administradores de locatários para controlar se os usuários podem alterar a imagem de perfil. Se a **configuração -SetPhotoEnabled** estiver desabilitada na política, os usuários não poderão adicionar, alterar ou remover sua imagem de perfil, para que a imagem do perfil não seja sincronizada com as equipes se o administrador alterar a foto.

<sup>8</sup> Você precisa atender aos requisitos listados na seção[Requisitos para criar e exibir reuniões para caixas de correio do local](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises).

<sup>9</sup> Um mínimo de uma licença Exchange Online Plano 1 também é necessário. Para obter mais informações, consulte [Pesquisar Teams dados de chat para usuários locais](/microsoft-365/compliance/search-cloud-based-mailboxes-for-on-premises-users).

<sup>10</sup> Usuários `SetPhotoEnabled` locais podem usar o Teams para atualizar sua imagem de perfil, mesmo que o Outlook na política de caixa de correio da Web seja definida como `false`.
 > [!NOTE]
 > A configuração de Office (OOF) por meio do cliente Teams atualmente não tem suporte para usuários cujas caixas de correio estão hospedadas no local; esses usuários devem executar essa ação por meio do cliente Outlook.
## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Treinamentos para ajudar seus usuários a usufruir ao máximo o Microsoft Teams

O Microsoft Teams funciona com vários serviços do Microsoft 365 e do Office 365 para fornecer aos usuários uma experiência avançada. Para dar suporte a essa experiência, você precisa habilitar determinados recursos ou serviços e atribuir licenças.

- Os usuários devem receber uma licença do Exchange Online.

- O SharePoint Online é necessário para compartilhar e armazenar arquivos em conversas de equipe. O Microsoft Teams não dá suporte para o SharePoint no local.

- Os usuários devem receber uma licença do SharePoint Online se desejarem compartilhar arquivos em chats. Se os usuários não forem designados e habilitados com as licenças do SharePoint Online, eles não terão o armazenamento OneDrive for Business no Microsoft 365 ou Office 365. O compartilhamento de arquivos continuará funcionando nos canais, mas os usuários não conseguirão compartilhar arquivos em bate-papos sem o armazenamento do OneDrive for Business no Microsoft 365 ou Office 365.

- Os usuários devem estar habilitados para a criação do grupo do Microsoft 365 para criar equipes no Microsoft Teams.

  > [!IMPORTANT]
  > Se você desinstalar o cliente do Skype for Business depois de mover um usuários para o modo **Somente Microsoft Teams**, a presença deixará de funcionar no Outlook e em outros aplicativos do Office. A presença funciona bem no Microsoft Teams. Para resolver esse problema, selecione a sua imagem de perfil no canto superior direito do Microsoft Teams e selecione **Configurações**. Na guia **Geral**, em **Aplicativo**, selecione **Registrar o Teams como o aplicativo de chat do Office (exige o reinício de aplicativos do Office)**. Depois de selecionar essa opção, feche e reabra todos os aplicativos do Office, como o Outlook. Depois de abrir o Outlook, as informações de presença estarão disponíveis.

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>Requisitos para criar e exibir reuniões para caixas de correio hospedadas no local

Se as caixas de correio forem hospedadas no local, para criar e exibir reuniões, os seguintes requisitos devem ser atendidos:

- A licença necessária do Teams deve ser atribuída para o usuário sincronizado do Azure Active Directory.

- Os usuários devem estar sincronizados com o Azure Active Directory. Para saber mais sobre como usar o Azure AD Connect para sincronizar com o Azure Active Directory, confira [Documentação de identidade híbrida](/azure/active-directory/hybrid/).

- As caixas de correio são hospedadas na atualização cumulativa 3 do Exchange Server 2016 ou posterior.

- A descoberta automática e os serviços Web do Exchange são publicados externamente.

- A autenticação OAuth está configurada de preferência por meio do Assistente de Configuração Híbrida do Exchange, executando uma configuração híbrida completa (Clássica ou Moderna). Se você não conseguir usar o assistente de configuração híbrida, configure o OAuth conforme descrito em [Configurar a autenticação OAuth entre as organizações do Exchange Online e do Exchange](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

  > [!NOTE]
  > O Exchange confia no token OAuth do serviço do Teams, que é conhecido como EvoSTS. A etapa 1 deve ser suficiente, mas apenas a EvoSTS; ACS é usado para pesquisa de disponibilidade no calendário.

- A caixa de seleção do recurso Implantação Híbrida do Exchange no Azure AD Connect está definida. Para obter mais informações, [consulte Exchange writeback híbrido](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized#exchange-hybrid-writeback).

- Para suporte de aplicativo de calendário e suplemento Teams Outlook para Mac, as URLs do Exchange Web Service devem ser configuradas como SPNs no Tenant Azure AD para o Exchange Service Principal. Esta etapa foi concluída com o assistente de configuração híbrida ou [etapas manuais para Autenticação Moderna Híbrida](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad).

Para habilitar a delegação de calendário para esses usuários:

- Você também deve concluir etapas conforme descrito em [Configure Integration and OAuth between Skype for Business Online e Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises); estas etapas fornecerão ao aplicativo de agendamento Teams as permissões necessárias para confirmar permissões de representante.
 
  > [!NOTE]
  > A etapa 2 inclui uma atribuição de função para ArchiveApplication, que não é necessária para delegação.

- O Teams de agendamento para Outlook requer Exchange 2013 CU19 ou posterior ao agendar uma reunião em nome de outra pessoa. Isso é para oferecer suporte à descoberta não autenticada da caixa de correio por nosso serviço para verificar as permissões delegadas na caixa de correio do delegador. O local do delegado e do delegador podem ser o Exchange 2013 ou posterior ou o Exchange online, mas a Descoberta Automática deve ser resolvida para o Exchange 2013 CU19 ou posterior.

## <a name="additional-considerations"></a>Considerações adicionais

Aqui estão algumas coisas que você precisa saber ao implementar o Microsoft Teams em sua organização.

- No Microsoft Teams, os recursos de segurança e conformidade, como o eDiscovery, o Content Search, arquivamento e retenção legal, funcionam melhor nos ambientes do Exchange Online e do SharePoint Online. Para conversas em canais, as mensagens serão rastreadas para a caixa de correio de grupo no Exchange Online, onde estão disponíveis para o eDiscovery. Se o SharePoint Online e o OneDrive for Business (usando contas de trabalho ou escolares) estiverem habilitados em toda a organização e para os usuários, esses recursos de conformidade estarão disponíveis para todos os arquivos dentro do Teams também.

- Controle e proteja a configuração das políticas de conformidade no Teams e no Exchange usando o Acesso Condicional. Para saber mais, confira [Como funcionam as políticas de acesso condicional para o Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)

- Se sua organização tiver exigências de conformidade para garantir que todas as discussões nas reuniões sejam detectáveis, é necessário desabilitar as reuniões privadas se o organizador tiver uma caixa de correio no Exchange. Para obter mais informações, consulte [Agendamento de reuniões particulares](./meeting-policies-in-teams-general.md#private-meeting-scheduling).

- Em uma implantação híbrida do Exchange, o conteúdo das mensagens de chat é pesquisável, independentemente de os participantes de chat terem uma caixa de correio baseada na nuvem ou em uma caixa de correio local. Para saber mais, leia [Pesquisar caixas de correio baseadas em nuvem para usuários locais](/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Para saber mais sobre como pesquisar conteúdo no Teams, leia [Pesquisar Conteúdo no Centro de Conformidade do Microsoft 365](/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

- Para o status de presença, o Microsoft Teams deve verificar se a caixa de correio está hospedada no Exchange Online ou no local. Em seguida, o serviço decide onde acessar a caixa de correio. Para habilitar o serviço do Teams a verificar o local da caixa de correio por meio da chamada da API REST para o serviço do Exchange Online, você deve implantar um ambiente híbrido do Exchange executando o assistente de configuração híbrida do Exchange, conforme descrito em [Criar uma implantação híbrida com o assistente de Configuração Híbrida](/exchange/hybrid-deployment/deploy-hybrid).

## <a name="troubleshooting"></a>Solução de problemas

Para obter um guia de solução de problemas completo sobre o tópico, não deixe de conferir [Solucionar problemas de interação do Microsoft Teams e do Exchange Server](/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue).
