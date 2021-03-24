---
title: Planos de chamada do Microsoft Teams
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
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: Determine qual Plano de Chamadas do Sistema de Telefonia da Microsoft atenderá melhor sua organização no Cloud Voice no Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b88af706f79dd195e2f9363ff45e586a1123686f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102727"
---
# <a name="which-calling-plan-is-right-for-you"></a>Qual plano de chamadas é ideal para você? 

Você concluiu o [get started](get-started-with-teams-quick-start.md). Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização. Talvez você tenha implantado [Reuniões & conferência.](deploy-meetings-microsoft-teams-landing-page.md) Agora você está pronto para adicionar cargas de trabalho de voz na nuvem e decidiu usar o Sistema de Telefonia da Microsoft com o Plano de Chamadas para se conectar à PSTN (Rede Telefônica Pública Comugada). 

Este artigo descreve as principais decisões de implantação para Planos de Chamada, bem como considerações adicionais que você pode querer configurar, com base nas necessidades da sua organização. Você também deve ler [o Cloud Voice no Microsoft Teams](cloud-voice-landing-page.md) para obter mais informações sobre as ofertas de voz na nuvem da Microsoft.


## <a name="learn-more-about-calling-plans"></a>Saiba mais sobre Planos de Chamada

Os artigos a seguir fornecem mais informações sobre como implantar e usar planos de chamada da Microsoft:

- [Sistema de Telefonia no Microsoft 365 ou Office 365](what-is-phone-system-in-office-365.md)
- [Planos de chamada para o Microsoft 365 ou Office 365](calling-plans-for-office-365.md)
- [Configurar Planos de Chamadas](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>Decisões principais de implantação

Para usar a Microsoft como sua operadora de telefonia, você precisa obter licenças do Plano de Chamadas e atribuí-las aos usuários do Sistema de Telefonia. 

Há dois tipos de Planos de Chamada disponíveis:

- Planos de Chamada Doméstica 
- Planos de chamada domésticas e internacionais

|Pergunte a si mesmo|Ação |
|------------|-------|
|Os Planos de Chamada estão disponíveis na minha área? Quais locais de usuário terão serviço de Plano de Chamada? | Para obter mais informações, consulte [Disponibilidade de país e região para Audioconferência e Planos de Chamada.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) | 
Meus usuários precisam de chamada internacional? | Para obter mais informações, consulte [Planos de Chamada para o Microsoft 365 ou Office 365](calling-plans-for-office-365.md). |
Meus usuários têm licenças de Planos de Chamada? | Para comprar e atribuir licenças, consulte [Etapa 2: Comprar e atribuir licenças.](set-up-calling-plans.md#step-2-buy-and-assign-licenses) |
Cada um dos meus usuários tem um número de telefone did (discagem direta) para dentro? | Para obter números de telefone, consulte [Etapa 3: Obter números de telefone](set-up-calling-plans.md#step-3-get-phone-numbers). |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>Transferir números de telefone para o Microsoft 365 ou Office 365

É fácil transferir seus números de telefone do seu provedor de serviços atual para o Teams. Depois de por seus números de telefone para o Teams, a Microsoft se tornará seu provedor de serviços e cobrará por esses números de telefone. Para obter mais informações, consulte [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).


### <a name="phone-numbers-and-emergency-locations"></a>Números de telefone e locais de emergência

Com Planos de Chamadas no Microsoft 365 ou Office 365, cada usuário em sua organização precisa ter um número de telefone DID (discagem direta direta) exclusivo e um endereço de emergência validado correspondente. Você também pode especificar um local de emergência no endereço de emergência (por exemplo, um número de escritório ou um número de piso). 

|Pergunte a si mesmo|Ação |
|:------------|:-------|
|Quão detalhado eu quero que o endereço de emergência e as informações de local sejam? |Para obter mais informações, consulte [O que são locais de emergência, endereços e roteamento de chamadas?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).


### <a name="calling-identity"></a>Identidade de chamada

Por padrão, todas as chamadas de saída usam o número de telefone atribuído como identidade de chamada (ID do chamador). O destinatário da chamada pode identificar o autor da chamada rapidamente e decidir se deseja aceitar ou rejeitar a chamada.

|Pergunte a si mesmo|Ação |
|:------------|:-------|
|Quero mascarar ou desabilitar a ID do chamador? | Para alterar ou bloquear a ID do chamador, consulte Definir a [ID do chamador para um usuário](set-the-caller-id-for-a-user.md). |
|||