---
title: "Configurar conferência de áudio para o Skype for Business e Teams da Microsoft"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: O365P_DialInConfDesc
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
- LIL_Placement
description: "Saiba como configurar a conferência discada ou áudio para as pessoas em sua empresa que precisam para ingressar em chamadas de conferência usando um telefone. "
ms.openlocfilehash: 6d8fae08a5dc8e6a1cf6bc05b458840c47fc83ed
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Configurar conferência de áudio para o Skype for Business e Teams da Microsoft

Em alguns casos, as pessoas na sua organização precisará usar um telefone para efetuar uma chamada para uma reunião. Skype para Teams da Microsoft e de negócios incluir o recurso de conferência de áudio para apenas essa situação! As pessoas podem ligar para Skype para reuniões de negócios ou Microsoft Teams usando um telefone, em vez de usar o Skype para negócios ou Teams Microsoft app em um PC ou dispositivo móvel. 
  
Você precisa configurar a conferência de áudio para as pessoas que pretende agendar ou liderança de reuniões. Os participantes da reunião que discam não precisam quaisquer licenças atribuídas a eles ou outro programa de instalação.
  
Para as perguntas frequentes sobre a conferência de áudio, consulte [perguntas comuns de conferência de áudio](audio-conferencing-common-questions.md).
  
## <a name="step-1-buy-and-assign-licenses"></a>Etapa 1: comprar e atribuir licenças
<a name="__top"> </a>

Você deve ser um [funções de administrador do Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para executar esta etapa.
  
1. Descubra se a conferência de áudio no Office 365 está disponível em seu país/região. [Disponibilidade de país e região para conferência de áudio e planos de chamada](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). 
    
2. Saiba quais licenças você precisará comprar para conferência de áudio e quanto eles terá um custo. Consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)e adquirir as licenças. 
    
3. [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) que você comprou às pessoas na organização que vão agendar ou realizar reuniões.
    
4. Se adquiriu licenças de complemento de **Conferência de áudio** e licenças créditos de comunicações, atribua muito. Para obter instruções, consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
    
## <a name="step-2-decide-on-your-audio-conferencing-provider"></a>Etapa 2: Decidir qual seu provedor de serviços de audioconferência
<a name="__top"> </a>

Um provedor de serviços de audioconferência fornece uma *ponte de conferência de áudio*. A ponte de conferência define seus números de telefone de discagem, PINs e IDs de conferência para reuniões. Decida quanto ao uso da Microsoft ou um provedor de serviços de audioconferência de terceiros:
  
> [!NOTE]
> Usuários do Microsoft Teams não não um provedor de serviços de audioconferência de terceiros do usuário. 
  
- **Microsoft como seu provedor de serviços de audioconferência**: se você desejar a solução mais simples para conferência de áudio, escolha Microsoft como seu provedor de serviços de audioconferência.
    
- **Terceiros como o seu provedor de serviços de audioconferência**: se você estiver em um país onde os serviços de audioconferência no Office 365 não está disponível, a qualidade de serviço não é ótima devido a seu local ou você tiver um contrato existente, escolha um áudio de terceiros provedor de conferência. Para localizar um provedor, vá para a [Microsoft identifique](http://go.microsoft.com/fwlink/?LinkId=797530).
    
> [!TIP]
> Em sua organização, você pode ter algumas pessoas que usam o Microsoft como seu provedor de serviços de audioconferência e outras pessoas que usam um provedor de terceiros. Mas isso será mais complicado para configurar e gerenciar. 
  
Para obter uma comparação detalhada entre Microsoft como seu provedor de áudio e um provedor de terceiros, consulte [comparar os provedores de serviços de audioconferência](compare-audio-conferencing-providers.md). 
  
## <a name="step-3-assign-the-audio-conferencing-provider-to-people-who-lead-or-schedule-meetings"></a>Etapa 3: Atribuir o provedor de serviços de audioconferência para as pessoas de avanço ou agendem reuniões
<a name="__top"> </a>

Agora que você tiver decidido em seu provedor de serviços de audioconferência, você precisa atribuir o provedor para as pessoas na sua organização de avanço ou agendar reuniões. Siga um destes procedimentos: 
  
- [Atribuir a Microsoft como um provedor de serviços de audioconferência](assign-microsoft-as-the-audio-conferencing-provider.md).
    
- [Atribuir um terceiro como um provedor de serviços de audioconferência](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
## <a name="step-4-set-up-meeting-invitations"></a>Etapa 4: Configurar os convites para reunião
<a name="__top"> </a>

As etapas a seguir são **opcionais**, mas muita admins like para executá-las:
  
1. [Personalizar convites de reunião](../set-up-skype-for-business-online/customize-meeting-invitations.md). Os números de discagem que são definidos para o usuário serão adicionados automaticamente aos convites de reunião serão enviados aos participantes. No entanto, você pode adicionar sua própria Ajuda e links legal, uma mensagem de texto e gráfico de pequena empresa.
    
2. [Conjunto de números de telefone de conferência de áudio para organizadores que estão incluídos nos convites de reunião](set-the-phone-numbers-included-on-invites.md). Esse é o número de telefone que serão exibidas na reunião programada pelo usuário.
    
3. [Definir os idiomas de atendedor automático de conferência de áudio](set-auto-attendant-languages-for-audio-conferencing.md) que o atendedor automático de conferência de áudio usa para saudar um chamador quando eles discam para um número de telefone de conferência de áudio. Esta etapa só se aplica se você estiver usando o Microsoft como seu provedor de áudio.
    
4. [Definir o tamanho do PIN para reuniões de conferência de áudio](set-the-pin-length-for-audio-conferencing-meetings.md).
    
> [!NOTE]
> Esse recurso ainda não disponível para clientes usando o Office 365 operado pela 21Vianet na China. Para saber mais, consulte [Saiba mais sobre o Office 365 operado pela 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE). 
  
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Tópicos relacionados

[Áudio perguntas comuns de conferência](audio-conferencing-common-questions.md)
  
[Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Números de telefone de conferência de áudio](phone-numbers-for-audio-conferencing.md)
  
[Definir opções para reuniões online e chamadas em conferência](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)

