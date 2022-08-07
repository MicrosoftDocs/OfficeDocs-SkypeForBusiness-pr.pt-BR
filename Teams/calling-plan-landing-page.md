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
description: Determine qual Plano de Chamadas do Sistema de Telefonia da Microsoft atenderá melhor à sua organização no Cloud Voice no Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ebe826b55d043c7f8ae8fea76c2d8e59ae5543bd
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268778"
---
# <a name="which-calling-plan-is-right-for-you"></a>Qual plano de chamadas é ideal para você?

Você concluiu a [Introdução](get-started-with-teams-quick-start.md). Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização. Talvez você tenha implantado [Reuniões & conferência](deploy-meetings-microsoft-teams-landing-page.md). Agora você está pronto para adicionar cargas de trabalho de voz na nuvem e decidiu usar o Sistema de Telefonia da Microsoft com o Plano de Chamadas para se conectar à PSTN (Rede Telefônica Pública Comunada).

Este artigo descreve as principais decisões de implantação para Planos de Chamadas e outras considerações que você talvez queira configurar, com base nas necessidades da sua organização. Você também deve ler [o Cloud Voice no Microsoft Teams](cloud-voice-landing-page.md) para obter mais informações sobre as ofertas de voz na nuvem da Microsoft.

## <a name="learn-more-about-calling-plans"></a>Saiba mais sobre planos de chamadas

Os artigos a seguir fornecem mais informações sobre como implantar e usar planos de chamadas da Microsoft:

- [Sistema de telefonia no Microsoft 365 ou Office 365](what-is-phone-system-in-office-365.md)
- [Planos de chamadas para o Microsoft 365 ou Office 365](calling-plans-for-office-365.md)
- [Configurar Planos de Chamadas](set-up-calling-plans.md)

## <a name="core-deployment-decisions"></a>Decisões importantes sobre implantação

Para usar a Microsoft como operadora de telefonia, você precisa obter licenças do Plano de Chamadas e atribuí-las aos usuários do Sistema de Telefonia.

Há três tipos de Planos de Chamadas disponíveis:

- Planos de Chamadas Domésticas
- Planos de Chamadas Internacionais
- Planos de chamadas pagas conforme o uso

| Pergunte-se | Ação |
|--------------|--------|
| Os Planos de Chamadas estão disponíveis na minha área? Quais locais de usuário terão o serviço Plano de Chamadas? | Para obter mais informações, consulte [Disponibilidade de país e região para Audioconferência e Planos de Chamadas](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). |
| Meus usuários precisam de chamadas internacionais? | Para obter mais informações, consulte [Planos de Chamadas para Microsoft 365 ou Office 365](calling-plans-for-office-365.md). |
| Se alguns dos meus usuários não fizerem um número significativo de chamadas de saída, o Plano de Chamadas Pagas Conforme o Uso será a opção mais econômica para eles? | Para obter mais informações, consulte [Planos de Chamadas para Microsoft 365 ou Office 365](calling-plans-for-office-365.md). |
| Meus usuários têm licenças de Planos de Chamadas? | Para comprar e atribuir licenças, consulte [a Etapa 2: Comprar e atribuir licenças](set-up-calling-plans.md#step-2-buy-and-assign-licenses). |
| Cada um dos meus usuários tem um número de telefone DID (direct inward dial)? | Para obter números de telefone, [consulte a Etapa 3: Obter números de telefone](set-up-calling-plans.md#step-3-get-phone-numbers). |

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>Transferir números de telefone para o Microsoft 365 ou Office 365

É fácil transferir seus números de telefone do seu provedor de serviços atual para o Teams. Depois de portar seus números de telefone para o Teams, a Microsoft se tornará seu provedor de serviços e cobrará por esses números de telefone. Para obter mais informações, consulte [Transferir números de telefone para o Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

### <a name="phone-numbers-and-emergency-locations"></a>Números de telefone e locais de emergência

Com os Planos de Chamadas no Microsoft 365 ou Office 365, cada usuário em sua organização precisa ter um número de telefone DID (direct inward dial) exclusivo e um endereço de emergência validado correspondente. Você também pode especificar um local de emergência dentro do endereço de emergência (por exemplo, um número de escritório ou número de andar).

|Pergunte-se|Ação |
|:------------|:-------|
|Qual é o detalhe que eu quero que o endereço de emergência e as informações de localização sejam? |Para obter mais informações, consulte [O que são locais de emergência, endereços e roteamento de chamadas?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).

### <a name="calling-identity"></a>Identidade de chamada

Por padrão, todas as chamadas de saída usam o número de telefone atribuído como identidade de chamada (ID do chamador). O destinatário da chamada pode identificar o autor da chamada rapidamente e decidir se deseja aceitar ou rejeitar a chamada.

|Pergunte-se|Ação |
|:------------|:-------|
|Deseja mascarar ou desabilitar a ID do chamador? | Para alterar ou bloquear a ID do chamador, consulte [Definir a ID do chamador para um usuário](set-the-caller-id-for-a-user.md). |
|||
