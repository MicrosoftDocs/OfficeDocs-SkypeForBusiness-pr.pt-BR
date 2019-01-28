---
title: Chamando planos em equipes da Microsoft
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: crowe
search.appverid: MET150
description: Página inicial do plano de chamada
appliesto:
- Microsoft Teams
ms.openlocfilehash: d3299460eeb504c53737d163a6026081775fce5d
ms.sourcegitcommit: 3a0b90af8eb3c10579b9eea7837c60a19a577881
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/28/2019
ms.locfileid: "29595348"
---
# <a name="phone-system-with-calling-plans"></a>Sistema de Telefonia com Planos de Chamadas 

Você concluiu a [Introdução](get-started-with-teams-quick-start.md). Você já distribuiu equipes com [bate-papo, equipes, canais, & aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) em toda a organização. Talvez você implantou [conferência de & de reuniões](deploy-meetings-microsoft-teams-landing-page.md). Agora você está pronto para adicionar as cargas de trabalho de voz de nuvem e você decidiu usar o sistema de telefone da Microsoft com chamar planejar para conectar-se para a comutação telefônica PSTN (rede pública). 

Este artigo descreve as principais decisões sobre implantação para chamar planos, bem como considerações adicionais que convém configurar, com base nas necessidades da sua organização. Você também deve ler [Nuvem de voz equipes da Microsoft](cloud-voice-landing-page.md) para obter mais informações sobre as ofertas de voz de nuvem da Microsoft.


## <a name="learn-more-about-calling-plans"></a>Saiba mais sobre planos de chamada

Os artigos a seguir fornecem mais informações sobre como implantar e usar o Microsoft chamar planos:

- [Sistema de Telefonia no Office 365](what-is-phone-system-in-office-365.md)
- [Planos de Chamadas para o Office 365](calling-plans-for-office-365.md)
- [Configurar Planos de Chamadas](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>Decisões sobre implantação de núcleo

Para usar o Microsoft como sua operadora de telefonia, você precisará obter licenças chamar planejar e atribuí-las aos usuários de seu sistema telefônico. 

Há dois tipos de planos de chamar disponíveis:

- Planos de chamada domésticas 
- Planos de chamada nacionais e internacionais

|Pergunte-se|Ação |
|------------|-------|
|Estão chamar planos disponíveis na minha área? Quais locais de usuário terá chamar planejar o serviço? | Para obter mais informações, consulte [disponibilidade país e região para conferência de áudio e planos de chamada](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). | 
Meus usuários preciso chamadas internacionais? | Para obter mais informações, consulte [Chamando planos do Office 365](calling-plans-for-office-365.md). |
Meus usuários tem planos de chamar licenças? | Para comprar e atribuir licenças, consulte [etapa 2: comprar e atribuir licenças](set-up-calling-plans.md#step-2-buy-and-assign-licenses). |
Meus usuários tem uma conexão direta (DID) número de telefone de discagem para dentro? | Para obter os números de telefone, consulte [etapa 3: obter os números de telefone](set-up-calling-plans.md#step-3-get-phone-numbers). |
|||

### <a name="transfer-phone-numbers-to-office-365"></a>Transferir números de telefone para o Office 365

É fácil transferir seus números de telefone do seu provedor de serviços atual para equipes. Depois que você a porta seus números de telefone para equipes, a Microsoft se tornará o provedor de serviços e bill referentes aos números de telefone. Para obter mais informações, consulte [transferir os números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).


### <a name="phone-numbers-and-emergency-locations"></a>Números de telefone e locais de emergência

Com a chamada estiver planejando no Office 365, cada usuário na sua organização precisa ter um exclusivo DID discagem direta (DID) números de telefone e um endereço de emergência validado correspondente. Você também pode especificar um local de emergência dentro o endereço de emergência (por exemplo, um número do escritório ou o número de chão). 

|Pergunte-se|Ação |
|:------------|:-------|
|Detalhada de como você deseja as informações de endereço e o local de emergência a serem? |Para obter mais informações, consulte [Cite locais de emergência, endereços e roteamento de chamadas?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).


### <a name="calling-identity"></a>Identificação de chamadas

Por padrão, todas as chamadas de saída usam o número de telefone atribuído como identidade de chamada (ID de chamador). O destinatário da chamada pode identificar o autor da chamada rapidamente e decidir se deseja aceitar ou rejeitar a chamada.

|Pergunte-se|Ação |
|:------------|:-------|
|Eu quiser mascarar ou desabilitar o ID do chamador? | Para alterar ou bloquear a ID do chamador, consulte [definir a identificação do chamador para um usuário](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user). |
|||




