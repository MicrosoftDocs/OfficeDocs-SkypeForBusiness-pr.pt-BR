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
ms.openlocfilehash: 689b2fcad408f0fe18651ada1a5ed03467bea345
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255234"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Como o Exchange e o Microsoft Teams interagem

> [!Tip]
> Assista à sessão a seguir para saber como as equipes interagem com o Azure Active Directory (AAD), o Microsoft 365 Groups, o Exchange, o SharePoint e o OneDrive for Business: [noções básicas do Microsoft Teams](https://aka.ms/teams-foundations)

Para toda a experiência do Teams, todos os usuários devem ser habilitados para a criação de grupos do Exchange Online, do SharePoint Online e do Microsoft 365.

As caixas de correio dos usuários do Exchange não podem ficar hospedadas online nem no local.

Os usuários hospedados no Exchange Online ou no Exchange Dedicated vNext podem usar todos os recursos do Microsoft Teams. Eles podem criar e ingressar em equipes e canais, criar e exibir reuniões, ligar e bater papo, modificar imagens de perfil de usuário (se a política de caixa de correio do Outlook na Web permitir que elas façam isso) e adicionar e configurar conectores, guias e bots. Para obter uma lista mais abrangente de recursos disponíveis, consulte a tabela a seguir.

Os usuários hospedados no Exchange Online dedicado (Herdado) devem ser sincronizados com o Azure Active Directory no Microsoft 365 ou o Office 365. Eles podem criar e ingressar em equipes e canais, adicionar e configurar guias e bots e usar os recursos de chat e chamadas. No entanto, eles não podem modificar imagens de perfil, gerenciar reuniões, acessar contatos do Outlook ou gerenciar conectores.

> [!IMPORTANT]
> Para a integração com o local, é altamente recomendável que você tenha uma implantação híbrida completamente clássica do Exchange com o Exchange Server 2016 ou posterior para atender aos requisitos abaixo. Para obter mais informações sobre como configurar uma implantação híbrida, consulte [implantações híbridas do Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid).

Os usuários com caixas de correio hospedadas no local devem ser sincronizados com o Azure Active Directory. Eles podem usar todos os recursos no cenário acima, mas também podem gerenciar reuniões se os requisitos listados em [requisitos para caixas de correio hospedadas na seção hospedada no local](#requirements-for-mailboxes-hosted-on-premises) forem atendidos.

A tabela a seguir fornece uma referência rápida útil para a disponibilidade de recursos com base no ambiente do Exchange.

**Ações suportadas:**

| A caixa de correio do usuário está hospedada em:                                        | eDiscovery       | &nbsp;Controle legal    | Tention  | Gerenciamento de canal e equipe | Criar e exibir reuniões no Microsoft Teams | Modificar fotos de perfil de usuário | Histórico de chamadas | Gerenciar contatos | Acessar contatos do Outlook | Caixa postal  | Adicionar e configurar conectores | Adicionar e configurar guias | Adicionar e configurar bots |
|---------------------------------------------------------------------|------------------|--------------------|------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                 | Sim <sup>1</sup> | Sim <sup>1</sup>   | Sim        | Sim                   | Sim                               | Sim<sup>7</sup>             | Sim          | Sim             | Sim <sup>6</sup>        | Sim        | Sim                          | Sim                    | Sim                    |
| **Exchange Online Dedicated vNext**                                 | Sim <sup>1</sup> | Sim <sup>1</sup>   | Sim        | Sim                   | Sim                               | Sim<sup>7</sup>             | Sim          | Sim             | Sim <sup>6</sup>        | Sim        | Sim                          | Sim                    | Sim                    |
| **Exchange Online Dedicated – Legacy** (Sincronização obrigatória com o Azure AD)  | Sim <sup>1</sup> | Sim <sup>1, 2</sup> | Sim <sup> 3 | Sim                   | Não                                | Não                          | Sim          | Sim             | Não                      | Sim <sup> 4 | Sim <sup> 5                   | Sim                    | Sim                    |
| **Exchange no local** (sincronização com o Azure AD) | Sim <sup>1</sup> | Sim <sup>1</sup>   | Sim <sup>3</sup> | Sim                   | Sim <sup>8</sup>         | Não                          | Sim          | Sim             | Não                      | Sim <sup> 4 | Sim <sup> 5                   | Sim                    | Sim                    |

<sup>1</sup> descoberta eletrônica e retenção legal para conformidade com mensagens de canal são compatíveis com todas as opções de hospedagem.

<sup>2</sup> as equipes de chat privadas do teams ainda não são suportadas para o controle legal para esta opção de hospedagem.

<sup>3</sup> a retenção usará uma caixa de correio de sombra para o usuário online armazenar mensagens.

<sup>4</sup> os usuários do teams com caixa de correio local do Exchange podem usar o correio de voz com o Teams e receber mensagens de correio de voz no Outlook, mas as mensagens de correio de voz não estarão disponíveis para exibição ou reprodução dentro do cliente da equipe.

<sup>5</sup> se um dos proprietários de uma equipe puder adicionar conectores, todos os outros participantes dessa equipe poderão fazer isso, mesmo se as caixas de correio estiverem hospedadas no local.

<sup>6</sup> somente contatos na pasta de contatos padrão. Não há suporte para o acesso a outras pastas de contatos ou subpastas.

<sup>7</sup> as equipes honram a configuração da [política de caixa de correio do Outlook](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) que é configurada por administradores de locatários para controlar se os usuários podem alterar a imagem do perfil. Se a configuração **-SetPhotoEnabled** estiver desativada na política, os usuários não poderão adicionar, alterar ou remover a imagem do perfil. Por exemplo, se um usuário carregar uma imagem de perfil que foi aprovada pelo departamento de ti ou RH da sua organização, nenhuma ação será necessária. No entanto, se um usuário carregar uma imagem inadequada, altere-a de acordo com as políticas internas da sua organização.

<sup>8</sup> você precisa atender aos requisitos listados em [requisitos para caixas de correio hospedadas na seção local](#requirements-for-mailboxes-hosted-on-premises) .

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Requisitos para aproveitar ao máximo o Microsoft Teams

O Microsoft Teams funciona com vários serviços do Microsoft 365 e do Office 365 para fornecer aos usuários experiência avançada. Para dar suporte a essa experiência, você precisa habilitar certos recursos ou serviços e atribuir licenças.

- Os usuários devem receber uma licença do Exchange Online.

- O SharePoint Online é necessário para compartilhar e armazenar arquivos em conversas de equipe. O Microsoft Teams não tem suporte para o SharePoint no local.

- Os usuários devem receber uma licença do SharePoint Online se desejam compartilhar arquivos em chats. Se os usuários não forem atribuídos e habilitados com as licenças do SharePoint Online, eles não terão o armazenamento do OneDrive for Business no Microsoft 365 ou no Office 365. O compartilhamento de arquivos continuará a funcionar em canais, mas os usuários não poderão compartilhar arquivos em chats sem o armazenamento do OneDrive for Business no Microsoft 365 ou no Office 365.

- Os usuários devem ser habilitados para criação de grupos do Microsoft 365 para criar equipes no Microsoft Teams.

> [!IMPORTANT]
> Se você desinstalar o cliente Skype for Business após mover um usuário para o modo **somente para equipes** , a presença poderá parar de funcionar no Outlook e em outros aplicativos do Office. A presença funciona bem no Microsoft Teams. Para solucionar esse problema, selecione a imagem do seu perfil no canto superior direito do Microsoft Teams e selecione **configurações**. Na guia **geral** , em **aplicativo**, selecione **registrar equipes como o aplicativo de chat do Office (requer a reinicialização de aplicativos do Office)**. Depois de selecionar essa opção, feche e abra novamente todos os aplicativos do Office, incluindo o Outlook. Depois de abrir o Outlook, as informações de presença estarão disponíveis.

## <a name="requirements-for-mailboxes-hosted-on-premises"></a>Requisitos para caixas de correio hospedadas no local

Se os usuários quiserem a funcionalidade de agendar uma reunião de equipe usando o Exchange Server local, os seguintes requisitos devem ser atendidos:

- A licença de equipe necessária precisa ser atribuída para o usuário sincronizado do Azure Active Directory.

- Os usuários devem ser sincronizados com o Azure Active Directory. Para obter informações sobre como usar o Azure AD Connect para sincronizar com o Azure Active Directory, consulte [documentação de identidade híbrida](https://docs.microsoft.com/azure/active-directory/hybrid/).

- As caixas de correio são hospedadas na atualização cumulativa 3 ou posterior do Exchange Server 2016.

- O autodiscover e o Exchange Web Services são publicados externamente.
 
> [!NOTE]
> A descoberta automática (automática) V2 é necessária para permitir que o serviço Teams execute uma descoberta não autenticada da caixa de correio do usuário. A v2 automática tem suporte no Exchange 2016 CU3 e posterior.

- A autenticação OAuth é configurada de preferência por meio do assistente de configuração híbrida do Exchange que executa uma configuração híbrida completa (clássica ou moderna). Se não for possível usar o assistente de configuração híbrida, configure o OAuth conforme descrito em [Configurar a autenticação OAuth entre organizações Exchange e Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).

> [!NOTE]
> Token de confiança do Exchange tokens OAuth do serviço do Teams, que é conhecido como EvoSTS. A etapa 1 deve ser suficiente, mas apenas a EvoSTS; O ACS é usado para pesquisa de disponibilidade no calendário.

- A caixa de seleção do recurso de implantação híbrida do Exchange no Azure AD Connect é definida.

- Para o suporte a aplicativos de calendário e o suplemento do teams Outlook para Mac, as URLs do serviço Web do Exchange devem ser configuradas como SPNs no Azure AD do locatário para a entidade de serviço do Exchange. Esta etapa é feita com o assistente de configuração híbrida ou com [as seguintes etapas manuais para autenticação moderna híbrida](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad).

Para habilitar a delegação de calendário para estes usuários:


- O delegado e o delegante devem ter uma caixa de correio no servidor Exchange.

- Você também deve completar as etapas 2-3 conforme descrito em [Configurar a integração e o OAuth entre o Skype for Business Online e o Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises); essas etapas fornecerão ao aplicativo agendamento de equipe as permissões necessárias para confirmar as permissões de representante.
 
> [!NOTE]
> A etapa 2 inclui a atribuição de função para ArchiveApplication, que não é necessária para delegação.

## <a name="additional-considerations"></a>Considerações adicionais

Veja algumas coisas adicionais a serem lembradas ao implementar o Microsoft Teams em sua organização.

- No Microsoft Teams, os recursos de segurança e conformidade, como o eDiscovery, o Content Search, arquivamento e retenção legal, funcionam melhor nos ambientes do Exchange Online e do SharePoint Online. Para conversas em canais, as mensagens serão rastreadas para a caixa de correio de grupo no Exchange Online, onde estão disponíveis para o eDiscovery. Se o SharePoint Online e o OneDrive for Business (usando contas de trabalho ou escolares) estiverem habilitados em toda a organização e para os usuários, esses recursos de conformidade estarão disponíveis para todos os arquivos dentro do Teams também.

- Controlar e proteger a configuração de políticas de conformidade no Teams e no Exchange usando o acesso condicional. Para obter mais informações, consulte [como funcionam as políticas de acesso condicional do teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams) .

- Se a sua organização tiver requisitos de conformidade para garantir que todas as discussões na reunião sejam detectáveis, você deve desabilitar reuniões privadas se o organizador tiver uma caixa de correio local do Exchange. Para obter mais informações, consulte [permitir agendar reuniões particulares](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-scheduling-private-meetings).

- Em uma implantação híbrida do Exchange, o conteúdo de mensagens de chat é pesquisável, independentemente de os participantes do chat terem uma caixa de correio ou uma caixa de correio local baseada em nuvem. Para saber mais, leia [pesquisando caixas de correio baseadas em nuvem para usuários locais](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Para saber mais sobre como pesquisar conteúdo no Teams, leia [pesquisa de conteúdo no centro de conformidade do Microsoft 365](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

## <a name="troubleshooting"></a>Solução de problemas

Para obter um guia de solução de problemas completo sobre o tópico, confira [solucionar problemas de interação do Microsoft Teams e do Exchange Server](https://docs.microsoft.com/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue).
