---
title: Números de telefone para Audioconferência no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 95a08f84-04e5-4f72-88a8-d6472a7c89d7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: Saiba quais países e regiões têm números de teleconferência discada e como eles são atribuídos automaticamente.
ms.openlocfilehash: daa2312350be038153db168517a1d0f5bd7023cf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299112"
---
# <a name="phone-numbers-for-audio-conferencing-in-skype-for-business-online"></a>Números de telefone para Audioconferência no Skype for Business Online

> [!NOTE]
> Para obter informações sobre números de telefone no Microsoft Teams, consulte [Números de telefone para Audioconferência no Microsoft Teams](/MicrosoftTeams/phone-numbers-for-audio-conferencing-in-teams).

When you are setting up **Audio Conferencing** for Skype for Business, dial-in phone numbers are automatically assigned to your organization. You can see the phone numbers that are assigned to your audio conferencing bridge by going to the **Skype for Business admin center** > **Audio conferencing** > **Microsoft bridge**. See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).
  
> [!NOTE]
> There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing. If you want to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add**, and then click **New Service Numbers**. Use the lists for **Country/Region**, **State/Region**, and **City** to filter your search. Also, if you are looking for toll-free service numbers, select **Toll-Free** from the **State/Region** list.
  
## <a name="audio-conferencing-coverage-and-pricing"></a>Preços e cobertura de Audioconferência

For a complete list of all the countries/regions and cities where Audio Conferencing is available, see [Countries and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans). For pricing information, see [Pricing for Audio Conferencing](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
## <a name="dial-in-phone-numbers-in-a-meeting-invite"></a>Números de telefone de discagem em um convite de reunião

When a Skype for Business Online user schedules a meeting in Outlook or Outlook Web App, the default audio conferencing number that is set for the user is included in the meeting invite. If you want to select a different default number for one or more users, you can change that by going to the **Skype for Business admin center** > **Audio conferencing** > **Users**. See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).
  
Outros números de discagem podem ser vistos clicando no link **Localizar um número local** no convite da reunião.
  
## <a name="dial-in-phone-numbers-set-on-an-audio-conferencing-bridge"></a>Números de telefone de discagem definidos em uma ponte de conferência de áudio

There are two types of audio conferencing phone numbers that can be assigned to your conferencing bridge: **Shared** and **Dedicated**. Both types of these numbers can be used by any caller to join audio meetings that are being held in your organization.
  
 **Números de telefone dedicados** são os que estão disponíveis apenas para usuários em sua organização. Você pode alterar os idiomas usados quando alguém liga para um desses números.
  
 **Números de telefone compartilhados** são os que podem ser compartilhados com outras organizações do Office 365. Não é possível alterar os idiomas usados quando alguém liga para um desses números.
  
While the default audio conferencing number that is assigned to an organizer is only included in the meeting invite, a caller can use any of the phone numbers that are assigned to your conferencing bridge to join a meeting. The list of phone numbers that can be used to join a meeting is available using the **Find a local number** link that is included on every meeting invite.
  
## <a name="automatically-assigned-audio-conferencing-phone-numbers"></a>Números de telefone de conferência de áudio atribuídos automaticamente

Shared audio conferencing phone numbers are automatically assigned to organizations when they're enabled for audio conferencing. When the phone numbers are assigned, a phone number is assigned as the default phone number of the conferencing bridge. The phone number assigned as the default number of the bridge will be one from the country/region of the organization.
  
> [!NOTE]
> O local do país ou região da sua organização pode ser encontrado entrando no centro de **Administração do Office 365** e olhando em **perfil da organização**. 
  
> [!CAUTION]
> Due to limited availability of toll phone numbers in Venezuela, Indonesia, and United Arab Emirates (UAE), organizations from these countries/regions won't have an Audio Conferencing toll number automatically assigned to them. Toll-free numbers from these locations are available depending on available inventory. 
  
Dedicated audio conferencing phone numbers are service numbers that you can get and then assign to your organization. Service numbers can be found by using the **Skype for Business admin center**. For details, see [Getting service phone numbers](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers).
  
Para ver uma lista dos países/regiões que têm números de telefone automaticamente atribuídos às organizações, consulte [Disponibilidade de Audioconferência e Planos de Chamada por país e região](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).
  
## <a name="what-else-should-you-know"></a>O que mais você deve saber?

- Para ver a lista de idiomas com suporte para videoconferências, consulte [idiomas aceitos por audioconferência](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Você pode usar o cmdlet [Get-csonlinedialinconferencingservicenumberhttp](https://go.microsoft.com/fwlink/?LinkId=617691) para ver os números de telefone dedicados para videoconferências para sua organização.
    
- Você pode usar o cmdlet [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) para ver os idiomas que podem ser definidos em um número de telefone de discagem dedicado.
    
- You can set up to four languages for each audio conferencing phone number - one primary and three secondary. And you can also set languages on a dedicated audio conferencing phone number.
    
- Para definir o número de telefone de discagem de um usuário, consulte [definir os números de telefone incluídos nos convites](set-the-phone-numbers-included-on-invites.md).
    
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
