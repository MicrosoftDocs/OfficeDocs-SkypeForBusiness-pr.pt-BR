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
description: Saiba mais sobre o Roteamento Direto, como configuração, decisões de implantação principais necessárias e considerações de roteamento de voz.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1c5120f60778879be0978cb80c56daf99e5b5a38
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031817"
---
# <a name="phone-system-direct-routing"></a>Roteamento Direto do Sistema de Telefonia

Você concluiu a [Introdução](get-started-with-teams-quick-start.md). Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização. Talvez você tenha implantado [Reuniões & conferência.](deploy-meetings-microsoft-teams-landing-page.md) Agora você está pronto para adicionar cargas de trabalho de voz na nuvem e decidiu usar sua própria operadora de telefonia para conectividade PSTN (Rede Telefônica Pública Comutado) usando Roteamento Direto do Sistema telefônico. Com o Roteamento Direto, você pode usar o Sistema de Telefonia praticamente com qualquer portadora de telefonia.

Este artigo descreve as principais decisões de implantação para Roteamento Direto, bem como considerações adicionais que você pode querer pensar, com base nas necessidades da sua organização. Você também deve ler [o Cloud Voice no Microsoft Teams](cloud-voice-landing-page.md) para obter mais informações sobre as ofertas de voz na nuvem da Microsoft.

## <a name="learn-more-about-direct-routing"></a>Saiba mais sobre o Roteamento Direto

Os artigos a seguir fornecem mais informações sobre como configurar e usar o Roteamento Direto do Sistema de Telefonia. Configurar o Roteamento Direto requer compreensão do design de roteamento PSTN. Você deve ler todos esses artigos para entender como planejar e configurar o Roteamento Direto:

- [Planejar o Roteamento Direto](direct-routing-plan.md) 
- [Configurar o Roteamento Direto](direct-routing-configure.md)
- [Lista de controladores de borda da sessão certificados para Roteamento Direto](direct-routing-border-controllers.md)
- [Monitorar e solucionar problemas do Roteamento Direto](direct-routing-monitor-and-troubleshoot.md)

Além disso, talvez você queira ler os seguintes artigos, dependendo das suas necessidades:

-  [Configurar um controlador de borda da sessão para vários locatários](direct-routing-sbc-multiple-tenants.md)
-  [Migrar para o roteamento direto](direct-routing-migrating.md)
-  [Contas de usuário em um ambiente híbrido com conectividade PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Assista à sessão a seguir para saber mais sobre o Roteamento Direto: [Roteamento Direto no Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Decisões importantes sobre implantação

Estas são as principais decisões a considerar para o Roteamento Direto. 

|Pergunte a si mesmo|Ação |
| :------------|:-------|
|Para quais usuários habilitarei o Roteamento Direto? | Para obter mais informações, consulte [Habilitar usuários para o Serviço de Roteamento Direto.](direct-routing-configure.md) |
Eu tenho as licenças necessárias para Roteamento Direto? | Para obter mais informações, consulte [Licenciamento e outros requisitos.](direct-routing-plan.md#licensing-and-other-requirements)
|||

### <a name="session-border-controller-sbc-considerations"></a>Considerações sobre o Controlador de Borda de Sessão (SBC)

Com o Roteamento Direto, você conecta seu próprio Controlador de Borda de Sessão (SBC) diretamente ao Sistema telefônico.  Para ver uma lista de SBCs certificados, consulte Controladores de Borda de Sessão [com Suporte.](direct-routing-border-controllers.md)

|Pergunte a si mesmo|Ação |
|:------------|:-------|
| Onde e como implantarei SBCs? | Para obter mais informações, consulte [Configurar Roteamento Direto](direct-routing-configure.md) | 
Tenho vários locatários? | Para obter mais informações, [consulte Configurar um Controlador de Borda de Sessão para vários locatários.](direct-routing-sbc-multiple-tenants.md)|
|||

### <a name="voice-routing-considerations"></a>Considerações sobre o roteamento de voz

Você precisará configurar o Sistema telefônico para encaminhar as chamadas para os SBCs específicos.

|Pergunte a si mesmo|Ação |
|:------------|:-------|
| Quais políticas de roteamento de voz, uso de PSTN e rotas de voz eu preciso criar? | Para obter informações de roteamento de voz, consulte [Configurar Roteamento de Voz.](direct-routing-configure.md)
| Quais usuários serão atribuídos à política de roteamento de voz que eu definir? | Veja os exemplos em [Configurar Roteamento de Voz.](direct-routing-configure.md) |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Garantir que as chamadas de entrada chegam ao cliente do Teams usando o TeamsUpgradePolicy

O Roteamento Direto só tem suporte no Microsoft Teams. Para receber chamadas PSTN por meio do Roteamento Direto, você precisa configurar o TeamsUpgradePolicy para garantir que as chamadas de entrada sejam recebidas no Teams. Os usuários devem estar no modo Somente equipes, o que você pode fazer atribuindo a eles a instância "UpgradeToTeams" do TeamsUpgradePolicy. 

|Pergunte a si mesmo|Ação |
|:------------|:-------|
|O que significa o modo Somente equipes? | Para obter mais informações, consulte as diretrizes de migração e interoperabilidade para [organizações que usam o Teams em conjunto com o Skype for Business.](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)|
|||

## <a name="additional-deployment-considerations"></a>Considerações adicionais sobre a implantação

Talvez você queira considerar o seguinte, com base nas necessidades e configurações da sua organização:

| Pergunte a si mesmo| Ação |
| :------------|:-------|
| Você tem uma implantação existente do Skype for Business Server com conectividade híbrida configurada? |  Para entender como as contas de usuário em um ambiente híbrido são provisionadas e gerenciadas, consulte Contas de usuário em um ambiente híbrido com [conectividade PSTN.](direct-routing-user-accounts-in-a-hybrid-environment.md)| 
| Você está migrando para o Roteamento Direto do Plano de Chamada ou de um ambiente local do Skype for Business? | Para entender mais sobre como migrar para o Roteamento Direto de um ambiente existente, consulte [Migrar para Roteamento Direto.](direct-routing-migrating.md) |
|||
