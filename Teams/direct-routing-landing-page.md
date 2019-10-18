---
title: Roteamento Direto do Sistema de Telefonia
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
f1keywords: ms.teamsadmincenter.directrouting.overview
description: Página de aterrissagem para roteamento direto
appliesto:
- Microsoft Teams
ms.openlocfilehash: decbe74eaece7508c2118175bd25f8acab200cc2
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572185"
---
# <a name="phone-system-direct-routing"></a>Roteamento Direto do Sistema de Telefonia

Você concluiu a [Introdução](get-started-with-teams-quick-start.md). Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização. Talvez você tenha implantado [reuniões & conferência](deploy-meetings-microsoft-teams-landing-page.md). Agora, você está pronto para adicionar cargas de trabalho de voz na nuvem e decidiu usar sua própria operadora de telefonia para conectividade PSTN (rede telefônica pública comutada) usando o roteamento direto do sistema telefônico. Com o roteamento direto, você pode usar o sistema telefônico com praticamente qualquer operadora de telefonia.

Este artigo descreve as principais decisões de implantação para roteamento direto, bem como considerações adicionais sobre as quais você pode querer pensar, com base nas necessidades da sua organização. Você também deve ler [voz na nuvem no Microsoft Teams](cloud-voice-landing-page.md) para obter mais informações sobre as ofertas de voz em nuvem da Microsoft.

## <a name="learn-more-about-direct-routing"></a>Saiba mais sobre o roteamento direto

Os artigos a seguir fornecem mais informações sobre como configurar e usar o roteamento direto do sistema telefônico. Configurar o roteamento direto requer a compreensão do design de roteamento PSTN. Você deve ler todos esses artigos para entender como planejar e configurar o roteamento direto:

- [Planejar o Roteamento Direto](direct-routing-plan.md) 
- [Configurar o Roteamento Direto](direct-routing-configure.md)
- [Lista de controladores de borda da sessão certificados para Roteamento Direto](direct-routing-border-controllers.md)
- [Monitorar e solucionar problemas do Roteamento Direto](direct-routing-monitor-and-troubleshoot.md)

Além disso, talvez você queira ler os seguintes artigos dependendo dos seus requisitos:

-  [Configurar um controlador de borda da sessão para vários locatários](direct-routing-sbc-multiple-tenants.md)
-  [Migrar para o roteamento direto](direct-routing-migrating.md)
-  [Contas de usuário em um ambiente híbrido com conectividade PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Assista à sessão a seguir para saber mais sobre o roteamento direto: [Roteamento direto no Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Decisões principais de implantação

Estas são as principais decisões a serem consideradas para o roteamento direto. 

|Pergunte-se|Ação |
| :------------|:-------|
|Para quais usuários o roteamento direto será habilitado? | Para obter mais informações, consulte [habilitar usuários para o serviço de roteamento direto](direct-routing-configure.md#enable-users-for-direct-routing-service). |
Tenho as licenças necessárias para o roteamento direto? | Para obter mais informações, consulte [Licenciamento e outros requisitos](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Considerações sobre o controlador de borda de sessão (SBC)

Com o roteamento direto, você conecta seu próprio controlador de borda de sessão (SBC) diretamente ao sistema telefônico.  Para obter uma lista de SBCs certificados, consulte [controladores de borda de sessão com suporte](direct-routing-border-controllers.md).

|Pergunte-se|Ação |
|:------------|:-------|
| Onde e como eu implanto o SBCs? | Para obter mais informações, consulte [Configurar o roteamento direto](direct-routing-configure.md) | 
Tenho vários locatários? | Para obter mais informações, consulte [configurar um controlador de borda de sessão para vários locatários](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>Considerações de roteamento de voz

Você precisará configurar o sistema de telefonia para direcionar as chamadas para o SBCs específico.

|Pergunte-se|Ação |
|:------------|:-------|
| Quais políticas de roteamento de voz, uso de PSTN e rotas de voz preciso criar? | Para obter informações de roteamento de voz, consulte [Configurar roteamento de voz](direct-routing-configure.md#configure-voice-routing).
| Quais usuários serão atribuídos à política de roteamento de voz que eu defino? | Consulte os exemplos em [Configurar roteamento de voz](direct-routing-configure.md#configure-voice-routing). |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Garanta chamadas de entrada no cliente das equipes usando o TeamsUpgradePolicy

O roteamento direto só tem suporte no Microsoft Teams. Para receber chamadas PSTN por meio do direcionamento direto, você precisa configurar o TeamsUpgradePolicy para garantir que as chamadas recebidas sejam recebidas no Microsoft Teams. Os usuários devem estar no modo somente Teams, que você pode fazer atribuindo a eles a instância "UpgradeToTeams" do TeamsUpgradePolicy. 

|Pergunte-se|Ação |
|:------------|:-------|
|O que significa o modo somente Teams? | Para obter mais informações, consulte [orientação de migração e interoperabilidade para organizações que usam o Skype for Business em equipe](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).|
|||

## <a name="additional-deployment-considerations"></a>Considerações adicionais sobre a implantação

Você pode considerar o seguinte, com base nas necessidades e configuração da sua organização:

| Pergunte-se| Ação |
| :------------|:-------|
| Você tem uma implantação existente do Skype for Business Server com conectividade híbrida configurada? |  Para entender como as contas de usuário em um ambiente híbrido são provisionadas e gerenciadas, consulte [contas de usuário em um ambiente híbrido com conectividade PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md).| 
| Você está migrando para o roteamento direto do plano de chamadas ou de um ambiente local do Skype for Business? | Para saber mais sobre a migração para o roteamento direto de um ambiente existente, confira [migrar para roteamento direto](direct-routing-migrating.md). |
|||
