---
title: Roteamento Direto
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: filippse
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Saiba mais sobre Teams Sistema de Telefonia com Roteamento Direto.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fe723ee8347ea96c87cb0a9e85f7794c5e50e01
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518703"
---
# <a name="direct-routing"></a>Roteamento Direto

Você concluiu a [Introdução](get-started-with-teams-quick-start.md). Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização. Talvez você tenha implantado [Reuniões & conferência](deploy-meetings-microsoft-teams-landing-page.md). Agora você está pronto para adicionar cargas de trabalho de voz e decidiu usar sua própria operadora de telefonia para conectividade PSTN (Rede Telefônica Pública Comugada) usando o Sistema de Telefonia com Roteamento Direto. Com o Roteamento Direto, você pode usar o Sistema de Telefonia praticamente com qualquer portadora de telefonia.

Este artigo descreve as principais decisões de implantação para Roteamento Direto, bem como considerações adicionais que você pode querer pensar, com base nas necessidades da sua organização. Você também deve ler [Plan your voice solution](cloud-voice-landing-page.md) para obter mais informações sobre as ofertas de voz da Microsoft.

## <a name="learn-more-about-direct-routing"></a>Saiba mais sobre Roteamento Direto

Os artigos a seguir fornecem mais informações sobre como configurar e usar o Roteamento Direto. Configurar o Roteamento Direto requer a compreensão do design de roteamento PSTN. Você deve ler todos esses artigos para entender como planejar e configurar o Roteamento Direto:

- [Planejar o Roteamento Direto](direct-routing-plan.md) 
- [Configurar o Roteamento Direto](direct-routing-configure.md)
- [Lista de controladores de borda da sessão certificados para Roteamento Direto](direct-routing-border-controllers.md)
- [Monitorar e solucionar problemas do Roteamento Direto](direct-routing-monitor-and-troubleshoot.md)

Além disso, talvez você queira ler os seguintes artigos, dependendo de seus requisitos:

-  [Configurar um controlador de borda da sessão para vários locatários](direct-routing-sbc-multiple-tenants.md)
-  [Migrar para o roteamento direto](direct-routing-migrating.md)
-  [Contas de usuário em um ambiente híbrido com conectividade PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Assista à sessão a seguir para saber mais sobre Roteamento Direto: [Roteamento Direto Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Decisões importantes sobre implantação

Estas são as principais decisões a considerar para Roteamento Direto. 

|Pergunte-se|Ação |
| :------------|:-------|
|Para quais usuários vou habilitar o Roteamento Direto? | Para obter mais informações, consulte [Enable users for Direct Routing Service](direct-routing-configure.md). |
Tenho as licenças necessárias para Roteamento Direto? | Para obter mais informações, consulte [Licenciamento e outros requisitos](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Considerações do Controlador de Borda de Sessão (SBC)

Com o Roteamento Direto, você conecta seu próprio Controlador de Borda de Sessão (SBC) diretamente Sistema de Telefonia. Para ver uma lista de SBCs [certificados, consulte Controladores de Borda de Sessão Com Suporte](direct-routing-border-controllers.md).

|Pergunte-se|Ação |
|:------------|:-------|
| Onde e como implantarei SBCs? | Para obter mais informações, consulte [Configure Direct Routing](direct-routing-configure.md) | 
Tenho vários locatários? | Para obter mais informações, [consulte Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>Considerações sobre roteamento de voz

Você precisará configurar o Sistema de Telefonia rotear as chamadas para os SBCs específicos.

|Pergunte-se|Ação |
|:------------|:-------|
| Quais políticas de roteamento de voz, uso de PSTN e rotas de voz que preciso criar? | Para obter informações de roteamento de voz, consulte [Configure Voice Routing](direct-routing-configure.md).
| Quais usuários serão atribuídos à política de roteamento de voz que eu defina? | Consulte os exemplos em [Configure Voice Routing](direct-routing-configure.md). |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Verifique se as chamadas de entrada chegam ao cliente Teams teamsUpgradePolicy

O Roteamento Direto só é suportado com Microsoft Teams. Para receber chamadas PSTN por meio de Roteamento Direto, você precisa configurar o TeamsUpgradePolicy para garantir que as chamadas de entrada sejam recebidas em Teams. Os usuários devem estar no modo TeamsOnly, que você pode fazer atribuindo a eles a instância "UpgradeToTeams" do TeamsUpgradePolicy. 

|Pergunte-se|Ação |
|:------------|:-------|
|O que significa o modo TeamsOnly? | Para obter mais informações, consulte [Diretrizes de migração e interoperabilidade para organizações que usam Teams em conjunto com Skype for Business](./migration-interop-guidance-for-teams-with-skype.md).|
|||


