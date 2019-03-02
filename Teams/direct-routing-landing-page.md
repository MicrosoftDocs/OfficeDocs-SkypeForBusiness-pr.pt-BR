---
title: Roteamento direto de sistema do telefone
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: Página de aterrissagem do roteamento direto
appliesto: Microsoft Teams
ms.openlocfilehash: 6aeff0f79dfbc6cd7b3ba3cddefee382673d24eb
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/01/2019
ms.locfileid: "30353262"
---
# <a name="phone-system-direct-routing"></a>Roteamento direto de sistema do telefone

Você concluiu a [Introdução](get-started-with-teams-quick-start.md). Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização. Talvez você implantou [conferência de & de reuniões](deploy-meetings-microsoft-teams-landing-page.md). Agora você está pronto para adicionar as cargas de trabalho de voz de nuvem e você decidiu usar sua próprias operadora de telefonia para conectividade de rede de telefônica pública comutada (PSTN) usando o recurso de roteamento direto de sistema do telefone. Com o roteamento direto, você pode usar o sistema telefônico com praticamente qualquer operadora de telefonia.

Este artigo descreve as principais decisões sobre implantação para roteamento direto, bem como considerações adicionais que convém configurar, com base nas necessidades da sua organização.  Você também deve ler [Nuvem de voz equipes da Microsoft](cloud-voice-landing-page.md) para obter mais informações sobre as ofertas de voz de nuvem da Microsoft.

## <a name="learn-more-about-direct-routing"></a>Saiba mais sobre o roteamento direto


Os artigos a seguir fornecem mais informações sobre como configurar e usar roteamento de telefone sistema direto. Configurando o roteamento direto requer uma compreensão do design de roteamento de PSTN. Você deve ler todos estes artigos para entender como planejar e configurar o roteamento direto:

- [Planejar o Roteamento Direto](direct-routing-plan.md) 
- [Configurar o Roteamento Direto](direct-routing-configure.md)
- [Lista de controladores de borda da sessão certificados para Roteamento Direto](direct-routing-border-controllers.md)
- [Monitorar e solucionar problemas de roteamento direto](direct-routing-monitor-and-troubleshoot.md)

Além disso, convém ler os artigos a seguir, dependendo dos requisitos:

-  [Configurar um controlador de borda da sessão para vários locatários](direct-routing-sbc-multiple-tenants.md)
-  [Migrar para o roteamento direto](direct-routing-migrating.md)
-  [Contas de usuário em um ambiente híbrido com conectividade PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Assista a sessão de seguir para saber mais sobre o roteamento direto: [Roteamento direta em equipes da Microsoft](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Decisões importantes sobre implantação

Estas são as decisões principais a serem considerados para roteamento direto. 


|Pergunte a si mesmo|Ação |
| :------------|:-------|
|Para os usuários que eu habilitará o roteamento direto? | Para obter mais informações, consulte [habilitar usuários para atendimento de roteamento direto](direct-routing-configure.md#enable-users-for-direct-routing-service). |
Eu tenho as licenças necessárias para roteamento direto? | Para obter mais informações, consulte [licenciamento e outros requisitos](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Considerações de controlador de borda (SBC) da sessão

Com o roteamento direto, você pode conectar seu próprio controlador de borda de sessão (SBC) diretamente ao sistema telefônico.  Para obter uma lista de certificados SBCs, consulte [Suporte para controladores de borda de sessão](direct-routing-border-controllers.md).

|Pergunte a si mesmo|Ação |
|:------------|:-------|
| Onde e como posso implantará SBCs? | Para obter mais informações, consulte [Configurar o roteamento direto](direct-routing-configure.md) | 
Eu tenho vários locatários? | Para obter mais informações, consulte [Configurar um controlador de borda de sessão para vários locatários](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>Considerações sobre o roteamento de voz

Você precisará configurar o sistema telefônico para rotear as chamadas para os SBCs específicos.

|Pergunte a si mesmo|Ação |
|:------------|:-------|
| Quais políticas de roteamento de voz, uso da PSTN e roteamentos de voz preciso criar? | Para informações de roteamento de voz, consulte [Configurar o roteamento de voz](direct-routing-configure.md#configure-voice-routing).
| Os usuários que serão atribuídos para a política de roteamento de voz que eu definem? | Consulte os exemplos em [Configurar o roteamento de voz](direct-routing-configure.md#configure-voice-routing). |
|||

### <a name="calling-and-interop-policies"></a>Políticas de chamada e de interoperabilidade

Roteamento direto somente é compatível com Microsoft Teams. Para fazer ou receber chamadas PSTN por meio de roteamento direto, você precisa configurar as políticas necessárias para garantir que as chamadas recebidas são recebidas em equipes. Você pode configurar usuários para definir as equipes como seu cliente preferencial para chamadas por Configurando o usuário para o modo somente equipes ou configuração de equipes como o cliente de chamada preferencial, atribuindo o TeamsCallingPolicy e o TeamsInteropPolicy.

|Pergunte a si mesmo|Ação |
|:------------|:-------|
|Como serão definidas equipes como cliente preferencial para chamadas? | Para obter mais informações, consulte [definir equipes da Microsoft como o preferencial chamar cliente para usuários](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).|
|||

## <a name="additional-deployment-considerations"></a>Outras considerações sobre implantação

Talvez você queira, considere o seguinte, com base nas necessidades e a configuração da sua organização:

| Pergunte a si mesmo| Ação |
| :------------|:-------|
| Você tem um Skype existente para implantação de servidor de negócios com conectividade híbrida configurada? |  Para entender como as contas de usuário em um ambiente híbrido são provisionadas e gerenciados, consulte [contas de usuário em um ambiente híbrido com conectividade PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md).| 
| Você está migrando roteamento direta a partir de chamar planejar ou um Skype para ambiente de local de negócios? | Para entender mais sobre a migração para o roteamento direta a partir de um ambiente existente, consulte [Migrando para o roteamento direto](direct-routing-migrating.md). |
|||
