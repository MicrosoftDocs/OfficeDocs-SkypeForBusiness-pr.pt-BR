---
title: "Configurar conferência de áudio para o Skype for Business e Teams da Microsoft"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 03/15/2018
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
- LIL_Placement
description: "Saiba como configurar a conferência discada ou áudio para as pessoas em sua empresa que precisam para ingressar em chamadas de conferência usando um telefone. "
ms.openlocfilehash: 4d82de668ec31f1664fb05202979dd6df94bda2b
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2018
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Configurar conferência de áudio para o Skype for Business e Teams da Microsoft

Às vezes, as pessoas em sua organização precisarão usar um telefone para ligar para uma reunião. Skype para Teams da Microsoft e de negócios incluir o recurso de conferência de áudio para apenas essa situação! As pessoas podem ligar para Skype para reuniões de negócios ou Microsoft Teams usando um telefone, em vez de usar o Skype para negócios ou Teams Microsoft app em um PC ou dispositivo móvel. 
  
Você precisa configurar a conferência de áudio para as pessoas que pretende agendar ou liderança de reuniões. Os participantes da reunião que discam não precisam quaisquer licenças atribuídas a eles ou outro programa de instalação.
  
Para as perguntas frequentes sobre a conferência de áudio, consulte [perguntas comuns de conferência de áudio](audio-conferencing-common-questions.md).
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Etapa 1: Descobrir se a conferência de áudio está disponível em seu país/região
<a name="__top"> </a>


Acesse a [disponibilidade do país e região para conferência de áudio e chamar planos](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) e selecione seu país ou região para obter informações sobre a conferência de áudio de disponibilidade, bem como informações sobre as tarifas de sistema telefônico, chamar planos e chamada gratuita números e créditos de comunicações. 
 
## <a name="step-2-get-and-assign-licenses"></a>Etapa 2: Obter e atribuir licenças
 
1. Para conferências de áudio, você precisa de uma licença de cada usuário que irá configurar discagem reuniões. Para saber quais licenças você precisará comprar para conferência de áudio e quanto eles terá um custo, consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
        
2. Depois que você adquire as licenças de conferência de áudio, você irá ned para atribuí-las às pessoas em sua organização que estão indo para agendar ou liderança de reuniões. Consulte [atribuir ou remover licenças do Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) você comprou às pessoas em sua organização que pretende agendar ou líder de reuniões.
    
3. Também é recomendável que você atribua licenças créditos de comunicações (não custam nada) para as mesmas pessoas que você atribuiu licenças para na etapa anterior. Para saber como configurar comunicações créditos, consulte [Configurar créditos de comunicações para sua organização](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).
    
> [!NOTE]
> Você também pode configurar a conferência de áudio de pagamento por minuto. Vá [aqui](../skype-for-business-and-microsoft-teams-add-on-licensing/audio-conferencing-pay-per-minute.md) para obter mais informações sobre como usá-los.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Etapa 3: Obtenha números de serviço para seus pontes de conferência
<a name="__top"> </a>

Para conferências de áudio, você não pode usar números de telefone para usuários; Você precisará fazer os números de serviço. Você pode obter tarifas ou números gratuitos de serviço para seus pontes de conferência. Há três maneiras de Chamada Tarifada do get e números gratuitos de serviço: 
  
- **Use o Skype para centro de administração de negócios.** Para alguns países/regiões, você pode obter números de serviço para seus pontes de conferência usando o Skype para o Centro de administração do Business, consulte [Getting números de telefone de serviço](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Porta de seus números de serviço existente.** A porta ou transferência existentes números do seu provedor de serviço atual ou a operadora de telefone para o Office 365. Você pode ver [transferir os números de telefone para o Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) ou [gerenciar números de telefone para sua organização](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para obter mais informações para ajudá-lo a fazer isso.  
  
- **Use um formulário de solicitação para novos números.** Às vezes (dependendo do seu país/região) não será possível obter seus números de serviço nova usando o Skype para o Centro de administração de negócios ou, você precisará de números de telefone específico ou códigos de área. Se for o caso, será necessário baixar um formulário e enviá-lo para nós. Para obter mais informações, consulte o [gerenciar números de telefone para sua organização](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) . 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Etapa 4: Atribuir um número de serviço para a ponte de conferência
<a name="__top"> </a>

Depois que você obtenha sua chamada Tarifada e/ou números de telefone gratuitos para sua ponte de conferência, você precisa atribuir números para que possam ser usadas em convites de reunião.  

Para atribuir um novo número de telefone para sua ponte de conferência de áudio, vá para o **Centro de administração do Office 365** > **Admin centrais** > **Skype para negócios** > **voz** > **números de telefone**, selecione o telefone número e, em seguida, clique em **atribuir**.

Para obter mais detalhes, consulte [atribuir um novo número de telefone para sua ponte de conferência de áudio](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Etapa 5: Definir o padrão e os idiomas alternativos para uma ponte de conferência
<a name="__top"> </a>

Em seguida, você deseja [definir os idiomas de atendedor automático de conferência de áudio](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) que o atendedor automático de conferência usa para saudar um chamador quando eles discam para um número de telefone para audioconferências. 

Vá para o **Centro de administração do Office 365** > **Admin centrais** > **Skype para negócios** > **audioconferências** > **configurações de ponte da Microsoft**, selecione o número de telefone de ponte de conferência e depois Clique em **definir idiomas**.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Etapa 6: Definir sua conferência as configurações de ponte
<a name="__top"> </a>
    
Após configurar sua ponte de conferência, verifique se as configurações padrão, como notificações de entrada/saída e o comprimento do PIN são aqueles que deseja usar; Se não estiver, você pode alterá-los. 

Você pode ir para o **Centro de administração do Office 365** > **Admin centrais** > **Skype para negócios** > **audioconferências** > **configurações de ponte da Microsoft**. Esse procedimento abrirá a página de **configurações de ponte da Microsoft** . Para obter mais detalhes, consulte [alterar as configurações de uma ponte de conferência de áudio](../audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge.md).

## <a name="step-7-assign-the-audio-conferencing-provider-and-dial-in-phone-numbers"></a>Etapa 7: Atribuir os números de telefone de provedor e dial-in de serviços de audioconferência

Agora, você precisará certificar-se de que a Microsoft é atribuído como um provedor e definir a chamada Tarifada e números para ligações gratuitas para elas ao mesmo tempo.

Atribuir a Microsoft como um provedor para as pessoas na sua organização de avanço ou agendar reuniões, indo para **o Centro de administração do Office 365** > **Skype para negócios** > **audioconferências** > **usuários**e selecione o usuário da lista e clique em **Editar**. Se você precisar de mais detalhes, consulte [Microsoft atribuir como um provedor de serviços de audioconferência](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).

Quando você estiver definindo o provedor, você também pode definir a chamada Tarifada e números para ligações gratuitas que serão adicionado à reunião convidam para esse usuário. Basta selecione os números de telefone nas listas suspensas. Para obter mais detalhes, consulte [Defina o telefone convidam números incluídos no](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md). 


## <a name="step-8-set-up-meeting-invitations-optional"></a>Etapa 8: Configurar os convites para reunião (opcional)
<a name="__top"> </a>
 
Os números de discagem que são definidos para o usuário serão adicionados automaticamente aos convites de reunião que são enviados para os participantes da reunião. No entanto, você pode adicionar sua própria Ajuda e links legal, uma mensagem de texto e gráfico de pequena empresa se desejar. Consulte [Personalizar convites de reunião](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Tópicos relacionados

[Perguntas comuns sobre a audioconferência](audio-conferencing-common-questions.md)
  
[Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Números de telefone para audioconferência](phone-numbers-for-audio-conferencing.md)
  
[Definir opções para reuniões online e chamadas em conferência](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
