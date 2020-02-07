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
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: Página inicial do plano de chamada
appliesto:
- Microsoft Teams
ms.openlocfilehash: c62ce8a891244920257623aea9a62859161a129f
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825189"
---
# <a name="which-calling-plan-is-right-for-you"></a>Qual plano de chamadas é ideal para você? 

Você concluiu a [introdução](get-started-with-teams-quick-start.md). Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização. Talvez você tenha implantado [reuniões & conferência](deploy-meetings-microsoft-teams-landing-page.md). Agora, você está pronto para adicionar cargas de trabalho de voz na nuvem e decidiu usar o sistema telefônico da Microsoft com plano de chamadas para se conectar à rede telefônica pública comutada (PSTN). 

Este artigo descreve as principais decisões de implantação para planos de chamada e outras considerações que você pode querer configurar, com base nas necessidades da sua organização. Você também deve ler [voz na nuvem no Microsoft Teams](cloud-voice-landing-page.md) para obter mais informações sobre as ofertas de voz em nuvem da Microsoft.


## <a name="learn-more-about-calling-plans"></a>Saiba mais sobre planos de chamada

Os artigos a seguir fornecem mais informações sobre como implantar e usar planos de chamada da Microsoft:

- [Sistema de telefonia no Office 365](what-is-phone-system-in-office-365.md)
- [Planos de Chamadas do Office 365](calling-plans-for-office-365.md)
- [Configurar Planos de Chamadas](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>Decisões principais de implantação

Para usar a Microsoft como sua operadora de telefonia, você precisa obter licenças de plano de chamada e atribuí-las aos usuários do sistema telefônico. 

Há dois tipos de planos de chamada disponíveis:

- Planos de chamadas domésticas 
- Planos de chamadas locais e internacionais

|Pergunte-se|Ação |
|------------|-------|
|Os planos de chamada estão disponíveis na minha área? Quais locais de usuário terão o serviço plano de chamadas? | Para obter mais informações, consulte [disponibilidade de país e região para conferências de áudio e planos de chamada](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). | 
Meus usuários precisam fazer chamadas internacionais? | Para obter mais informações, consulte [planos de chamada do Office 365](calling-plans-for-office-365.md). |
Os meus usuários têm licenças de planos de chamada? | Para comprar e atribuir licenças, consulte [etapa 2: comprar e atribuir licenças](set-up-calling-plans.md#step-2-buy-and-assign-licenses). |
Cada um dos meus usuários tem um número de telefone do Direct Inward Dial (DID)? | Para obter números de telefone, consulte a [etapa 3: obter números de telefone](set-up-calling-plans.md#step-3-get-phone-numbers). |
|||

### <a name="transfer-phone-numbers-to-office-365"></a>Transferir números de telefone para o Office 365

É fácil transferir seus números de telefone de seu provedor de serviços atual para o Microsoft Teams. Depois de portar seus números de telefone para o Microsoft Teams, a Microsoft se tornará seu provedor de serviços e cobrará você por esses números de telefone. Para obter mais informações, consulte [transferir números de telefone para o Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).


### <a name="phone-numbers-and-emergency-locations"></a>Números de telefone e locais de emergência

Com planos de chamada no Office 365, todos os usuários de sua organização precisam ter um número de telefone exclusivo do Direct Inward Dial (DID) e um endereço de emergência validado correspondente. Você também pode especificar um local de emergência dentro do endereço de emergência (por exemplo, um número de escritório ou um número de chão). 

|Pergunte-se|Ação |
|:------------|:-------|
|Qual é o nível de detalhamento dos dados do endereço de emergência e do local que devem ser? |Para obter mais informações, consulte [o que são locais de emergência, endereços e encaminhamento de chamadas?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).


### <a name="calling-identity"></a>Identidade de chamada

Por padrão, todas as chamadas de saída usam o número de telefone atribuído como identidade de chamada (identificação de chamadas). O destinatário da chamada pode identificar o autor da chamada rapidamente e decidir se deseja aceitar ou rejeitar a chamada.

|Pergunte-se|Ação |
|:------------|:-------|
|Desejo mascarar ou desabilitar o recurso de identificação de chamadas? | Para alterar ou bloquear a identificação de chamadas, consulte [definir a identificação de chamadas para um usuário](set-the-caller-id-for-a-user.md). |
|||




