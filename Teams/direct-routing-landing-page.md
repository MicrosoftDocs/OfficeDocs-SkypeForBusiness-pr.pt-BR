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
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Saiba mais sobre Roteamento Direto, como configuração, decisões de implantação principais necessárias e considerações de roteamento de voz.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4298cc34122d6b3bb7d9f9bb1f8698aec864426f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122205"
---
# <a name="phone-system-direct-routing"></a>Roteamento Direto do Sistema de Telefonia

Você concluiu a [Introdução](get-started-with-teams-quick-start.md). Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização. Talvez você tenha implantado [Reuniões & conferência.](deploy-meetings-microsoft-teams-landing-page.md) Agora você está pronto para adicionar cargas de trabalho de voz na nuvem e decidiu usar sua própria operadora de telefonia para conectividade PSTN (Rede Telefônica Pública Comugada) usando Sistema de Telefonia Roteamento Direto. Com o Roteamento Direto, você pode usar o Sistema de Telefonia praticamente com qualquer portadora de telefonia.

Este artigo descreve as principais decisões de implantação para Roteamento Direto, bem como considerações adicionais que você pode querer pensar, com base nas necessidades da sua organização. Você também deve ler [o Cloud Voice no Microsoft Teams](cloud-voice-landing-page.md) para obter mais informações sobre as ofertas de voz na nuvem da Microsoft.

## <a name="learn-more-about-direct-routing"></a>Saiba mais sobre Roteamento Direto

Os artigos a seguir fornecem mais informações sobre como configurar e usar Sistema de Telefonia Roteamento Direto. Configurar o Roteamento Direto requer a compreensão do design de roteamento PSTN. Você deve ler todos esses artigos para entender como planejar e configurar o Roteamento Direto:

- [Planejar o Roteamento Direto](direct-routing-plan.md) 
- [Configurar o Roteamento Direto](direct-routing-configure.md)
- [Lista de controladores de borda da sessão certificados para Roteamento Direto](direct-routing-border-controllers.md)
- [Monitorar e solucionar problemas do Roteamento Direto](direct-routing-monitor-and-troubleshoot.md)

Além disso, talvez você queira ler os seguintes artigos, dependendo de seus requisitos:

-  [Configurar um controlador de borda da sessão para vários locatários](direct-routing-sbc-multiple-tenants.md)
-  [Migrar para o roteamento direto](direct-routing-migrating.md)
-  [Contas de usuário em um ambiente híbrido com conectividade PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Assista à sessão a seguir para saber mais sobre Roteamento Direto: [Roteamento Direto no Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Decisões importantes sobre implantação

Estas são as principais decisões a considerar para Roteamento Direto. 

|Pergunte a si mesmo|Ação |
| :------------|:-------|
|Para quais usuários vou habilitar o Roteamento Direto? | Para obter mais informações, consulte [Enable users for Direct Routing Service](direct-routing-configure.md). |
Tenho as licenças necessárias para Roteamento Direto? | Para obter mais informações, consulte [Licenciamento e outros requisitos.](direct-routing-plan.md#licensing-and-other-requirements)
|||

### <a name="session-border-controller-sbc-considerations"></a>Considerações do Controlador de Borda de Sessão (SBC)

Com o Roteamento Direto, você conecta seu próprio Controlador de Borda de Sessão (SBC) diretamente Sistema de Telefonia.  Para ver uma lista de SBCs certificados, consulte Controladores de Borda de Sessão [Com Suporte.](direct-routing-border-controllers.md)

|Pergunte a si mesmo|Ação |
|:------------|:-------|
| Onde e como implantarei SBCs? | Para obter mais informações, consulte [Configure Direct Routing](direct-routing-configure.md) | 
Tenho vários locatários? | Para obter mais informações, [consulte Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>Considerações sobre roteamento de voz

Você precisará configurar o Sistema de Telefonia rotear as chamadas para os SBCs específicos.

|Pergunte a si mesmo|Ação |
|:------------|:-------|
| Quais políticas de roteamento de voz, uso de PSTN e rotas de voz que preciso criar? | Para obter informações sobre roteamento de voz, consulte [Configure Voice Routing](direct-routing-configure.md).
| Quais usuários serão atribuídos à política de roteamento de voz que eu defina? | Consulte os exemplos em [Configure Voice Routing](direct-routing-configure.md). |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Verifique se as chamadas de entrada chegam ao cliente Teams teamsUpgradePolicy

O Roteamento Direto só é suportado com Microsoft Teams. Para receber chamadas PSTN por meio de Roteamento Direto, você precisa configurar o TeamsUpgradePolicy para garantir que as chamadas de entrada sejam recebidas em Teams. Os usuários devem estar Teams modo Somente, o que você pode fazer atribuindo a eles a instância "UpgradeToTeams" do TeamsUpgradePolicy. 

|Pergunte a si mesmo|Ação |
|:------------|:-------|
|O que Teams modo Only significa? | Para obter mais informações, consulte [Diretrizes de migração](./migration-interop-guidance-for-teams-with-skype.md)e interoperabilidade para organizações que usam Teams em conjunto com Skype for Business .|
|||

## <a name="additional-deployment-considerations"></a>Considerações adicionais sobre implantação

Você pode considerar o seguinte, com base nas necessidades e configurações da sua organização:

| Pergunte a si mesmo| Ação |
| :------------|:-------|
| Você tem uma implantação Skype for Business Server existente com conectividade híbrida configurada? |  Para entender como as contas de usuário em um ambiente híbrido são provisionadas e gerenciadas, consulte Contas de usuário em um ambiente híbrido com [conectividade PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md).| 
| Você está migrando para Roteamento Direto do Plano de Chamadas ou de um ambiente Skype for Business local? | Para entender mais sobre como migrar para Roteamento Direto de um ambiente existente, consulte [Migrating to Direct Routing](direct-routing-migrating.md). |
|||