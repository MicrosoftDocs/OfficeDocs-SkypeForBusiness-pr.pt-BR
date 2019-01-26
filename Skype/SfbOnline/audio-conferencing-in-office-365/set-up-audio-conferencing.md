---
title: Configurar conferência de áudio para o Skype for Business e Teams da Microsoft
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
- Audio Conferencing
- LIL_Placement
description: 'Saiba como configurar a conferência discada ou áudio para as pessoas em sua empresa que precisam para ingressar em chamadas de conferência usando um telefone. '
ms.openlocfilehash: 5d069822bf818db63ed35545a34a0bfa2eeee672
ms.sourcegitcommit: c0679cbaf7df38769f722afd65c4232311d25515
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2019
ms.locfileid: "29562664"
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Configurar conferência de áudio para o Skype for Business e Teams da Microsoft

Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC. 
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Para as perguntas frequentes sobre Audioconferência, consulte [Perguntas comuns sobre Audioconferência](/MicrosoftTeams/audio-conferencing-common-questions).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Etapa 1: Descobrir se a audioconferência está disponível em seu país/região
<a name="__top"> </a>


Acesse [Disponibilidade do país e região para audioconferência e planos de chamada](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) e selecione seu país ou região para obter informações de disponibilidade sobre a audioconferência, assim como informações sobre as sistema telefônico, planos de chamada, números de chamada tarifada e chamada gratuita, e créditos de comunicação. 
 
## <a name="step-2-get-and-assign-licenses"></a>Etapa 2: Comprar e atribuir licenças
 
1. For Audio Conferencing, you need a license for each user who will set up dial-in meetings. To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
        
2. After you buy the Audio Conferencing licenses, you will ned to assign them to those people in your organization who are going to schedule or lead meetings. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.
    
3. We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step. To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).
    
> [!NOTE]
> You can also set up pay-per-minute Audio Conferencing. Go [here](/microsoftteams/audio-conferencing-pay-per-minute) to find out more about how to use them.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Etapa 3: Obtenha números de serviço para suas pontes de conferência
<a name="__top"> </a>

For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers. You can get either toll or toll-free service numbers for your conferencing bridges. There are three ways to get toll and toll-free service numbers: 
  
- **Use the Skype for Business admin center.** For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center, see [Getting service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Port your existing service numbers.** To port or transfer existing numbers from your current service provider or phone carrier to Office 365. You can see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.  
  
- **Use a request form for new numbers.** Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes. If so, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information. 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Etapa 4: Atribuir um número de serviço para a ponte de conferência
<a name="__top"> </a>

Depois de obter seus números de serviço tarifado e/ou gratuito para sua ponte de conferência, você precisa atribuir os números para que possam ser usados em convites de reunião.  

Para atribuir um novo número de telefone para sua ponte de audioconferência:

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para o Centro de administração de negócios:**

 Vá para o **Centro de administração do Office 365** > **Admin centrais** > **Skype para negócios** > **voz** > **números de telefone**, selecione o número de telefone e clique em **atribuir**.

Para obter mais detalhes, consulte [alterar os números de telefone na sua ponte de conferência de áudio](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Etapa 5: Definir o padrão e os idiomas alternativos para uma ponte de conferência
<a name="__top"> </a>

Em seguida, você deseja [Definir os idiomas de atendedor automático da audioconferência](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) que o atende dor automático da audioconferência usa para saudar um chamador quando ele disca para um número de telefone para uma audioconferência. 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Usar o centro de administração do Microsoft Teams e do Skype para Business:**

No painel, vá para **Reuniões** > **Pontes de conferência**, selecione o número de telefone da ponte de conferência, clique em **Editar**e escolha o idioma padrão.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para o Centro de administração de negócios:**

Vá para o **Centro de administração do Office 365** > **Admin centrais** > **Skype para negócios** > **audioconferências** > **ponte da Microsoft**, selecione o número de telefone de ponte de conferência e, em seguida, clique em ** Definir idiomas**.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Etapa 6: Definir suas configurações da ponte de conferência
<a name="__top"> </a>
    
Após configurar sua ponte de conferência, verifique se as configurações padrão, como notificações de entrada/saída e o comprimento do PIN, são aquelas que deseja usar; caso contrário, você pode alterá-las. 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Usar o centro de administração do Microsoft Teams e do Skype para Business:**

From the Dashboard, go to **Meetings** > **Conference bridges** > **Bridge settings**. This will open the **Bridge settings** pane. For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para o Centro de administração de negócios:**

Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Microsoft bridge settings**. This will open the **Microsoft bridge settings** page. For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Etapa 7: Atribuir números de telefone para discagem para os usuários que realizarão as reuniões

Após ter criado uma ponte de audioconferênci, você precisará definir números de chamada tarifada e chamada gratuita para seus usuários.

You will need to do this for all of the people in your organization who lead or schedule meetings. To do this:

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Usar o centro de administração do Microsoft Teams e do Skype para Business:**

No painel, clique em **Usuários**, selecione o usuário na lista, clique em **Editar**, clique em **Editar** ao lado de **Audioconferência**e, em seguida, no painel de **Audioonferência**, escolha um número nas listas **Número de chamada tarifada** e **Número de chamada gratuita**.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para o Centro de administração de negócios:**

Go to the **Office 365 admin center** > **Skype for Business** > **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**. If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Etapa 8: Configurar os convites para reuniões (opcional)
<a name="__top"> </a>
 
The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees. However, you can add your own help and legal links, a text message, and small company graphic if you want. See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Tópicos relacionados

[Perguntas comuns sobre a Audioconferência](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Números de telefone para audioconferência](phone-numbers-for-audio-conferencing.md)
  
[Definir opções para reuniões on-line e chamadas em conferência](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
