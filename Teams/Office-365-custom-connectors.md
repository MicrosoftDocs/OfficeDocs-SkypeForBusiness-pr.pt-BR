---
title: Gerenciar conectores e conectores personalizados do Microsoft 365
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 01/24/2023
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba como os conectores mantêm sua equipe atualizada fornecendo conteúdo e atualizações diretamente em um canal do Teams para serviços que você usa.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bf38711da0205e7c674e769942d00d340d51f66e
ms.sourcegitcommit: 1cb5f7129562eb2b228da23497c0e09e53da3872
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2023
ms.locfileid: "69983679"
---
# <a name="manage-microsoft-365-connectors-and-custom-connectors"></a>Gerenciar conectores e conectores personalizados do Microsoft 365

Os conectores no Microsoft Teams fornecem atualizações de conteúdo e serviço diretamente de serviços de terceiros em um canal do Teams. Usando conectores, os usuários recebem atualizações de serviços populares como Trello, Wunderlist, GitHub e Azure DevOps Services. As atualizações são postadas diretamente no fluxo de chat. Isso facilita que todos os membros permaneçam em sincronização e recebam rapidamente as informações relevantes.

Os conectores do Microsoft 365 são usados com grupos do Teams e do Microsoft 365. Você pode usar os mesmos conectores no Teams e no Microsoft Exchange. 

<!--- However, if you disable any connectors configured for a Microsoft 365 group, it also disables the ability for the Microsoft 365 group to create connectors. --->

Se as permissões da equipe permitirem, qualquer membro de uma equipe poderá adicionar um conector na equipe e todos os membros da equipe serão notificados sobre as atividades desse serviço. Qualquer membro da equipe com as permissões para adicionar ou remover pode modificar a configuração de conectores por outros membros.

## <a name="enable-or-disable-connectors-in-teams"></a>Habilitar ou desabilitar conectores no Teams

O módulo Exchange Online PowerShell v2 usa autenticação moderna e funciona com MFA (autenticação multifator) para se conectar a todos os ambientes do PowerShell relacionados ao Exchange no Microsoft 365. Os administradores podem usar o PowerShell do Exchange Online para desabilitar conectores para um locatário inteiro ou uma caixa de correio de grupo específica, afetando todos os usuários nesse locatário ou caixa de correio. Não é possível desabilitar para alguns usuários específicos.

A configuração de locatário substitui a configuração de grupo. Por exemplo, se um administrador habilitar conectores para o grupo e desabilitá-los no locatário, os conectores do grupo serão desabilitados. Para habilitar um conector no Teams, [conecte-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true) usando autenticação moderna com ou sem MFA.

Para habilitar ou desabilitar um conector, execute os seguintes comandos no Exchange Online PowerShell:

* Para desabilitar conectores para o locatário: `Set-OrganizationConfig -ConnectorsEnabled:$false`.
* Para desabilitar mensagens acionáveis para o locatário: `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`.
* Para habilitar conectores para o Teams, execute os seguintes comandos:
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

Para obter mais informações sobre a troca de módulos do PowerShell, consulte [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true). Para habilitar ou desabilitar conectores do Outlook, [conecte aplicativos aos seus grupos no Microsoft Outlook](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab).

## <a name="publish-connectors-for-your-organization"></a>Publicar conectores para sua organização

Para disponibilizar um conector personalizado para os usuários da sua organização, carregue um aplicativo de conector personalizado no catálogo de aplicativos da sua organização. Os usuários finais dentro da organização podem instalar, configurar e usar o conector em uma equipe.

> [!IMPORTANT]
> Os conectores personalizados não estão disponíveis nos ambientes GCC (Nuvem da Comunidade Governamental), GCCH (Government Community Cloud-High) e DOD (Departamento de Defesa).

Para usar conectores em uma equipe ou canal, abra o menu Mais Opções no canto superior direito de um canal. No menu, selecione **Conectores** e localize ou pesquise o conector necessário. Configure o conector selecionado, se necessário.

:::image type="content" source="media/connectors-selection-ui.png" alt-text="Adicione conectores ao canal no Teams nas opções Mais no canto superior direito do canal.":::

## <a name="update-url-of-a-connector"></a>Atualizar URL de um conector

Os conectores do Teams estão em transição para uma nova URL para aumentar a segurança. Durante a transição, você receberá uma notificação para atualizar o conector configurado. Atualize seu conector o quanto antes para evitar qualquer interrupção nos serviços do conector. Para atualizar seu conector:

1. Na página de configuração dos conectores, verifique a mensagem **Atenção Necessária** ao lado do conector configurado.

   :::image type="content" source="media/teams-attention-required-message.png" alt-text="Captura de tela da mensagem Atenção Necessária.":::

1. Para recriar a conexão para conectores de webhook de entrada, selecione **Atualizar URL** e use o URL de webhook gerado.

   :::image type="content" source="media/teams-update-url-option.png" alt-text="Captura de tela do botão Atualizar URL.":::

1. Para outros tipos de conector, remova o conector e recrie a configuração do conector. Uma mensagem **URL está atualizado** é exibida.

   :::image type="content" source="media/teams-url-updated.png" alt-text="A captura de tela da URL está atualizada.":::

## <a name="considerations-when-using-connectors-in-teams"></a>Considerações ao usar conectores no Teams

* Os conectores são desabilitados por padrão nos ambientes da GCC (Comunidade de Nuvem Governamental). Para habilita-los, defina os parâmetros `ConnectorsEnabled` ou `ConnectorsEnabledForTeams` para `$true` com o cmdlet `SetOrganizationConfig`. Conecte-se ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true).

* Se o usuário que adicionou um conector a uma equipe deixar a equipe, o conector continuará funcionando.

* Os conectores a seguir não estão disponíveis para uso em janeiro de 2023:

  * AHA
  * AIRBRAKE
  * AIRCALL
  * APPLINKS
  * APPSIGNAL
  * FEIJÃO
  * BITBUCKET
  * BITBUCKETSERVER
  * AMIGO
  * BUGSNAG
  * BUILDKITE
  * CATSONE
  * CHATRA
  * CIRCLECI
  * CODESHIP
  * GETRESPONSE
  * GHOSTINSPECTOR
  * GROOVE
  * HEROKU
  * HONEYBADGER
  * INTERCOMUNICADOR
  * LOGENTRIES
  * NEWRELIC
  * OPSGENIE
  * PAGERDUTY
  * PAPERTRAIL
  * PINGDOM
  * PIVOTALTRACKER
  * RAYGUN
  * ROLLBAR
  * RUNSCOPE
  * SATISMETER
  * SEMÁFORO
  * SENTINELA
  * SHAREPOINTNEWS
  * SIMPLEINOUT
  * STATUSPAGEIO
  * SUBVERSION
  * TEAMFOUNDATIONSERVER
  * TESTFAIRY
  * TRAVISCI
  * UPDOWN
  * USERLIKE
  * XPDEV

## <a name="related-articles"></a>Artigos relacionados

* [Visão geral de conectores personalizados e webhooks](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Como criar conectores Office 365](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
