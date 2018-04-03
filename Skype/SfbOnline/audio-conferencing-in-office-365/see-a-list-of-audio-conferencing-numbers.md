---
title: See a list of Audio Conferencing numbers
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
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
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to look up your dial-in conferencing numbers from within Skype for Business. '
ms.openlocfilehash: 19bbf38968afb094deaf97ff14a6673b4cfdda48
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2018
---
# <a name="see-a-list-of-audio-conferencing-numbers"></a>See a list of Audio Conferencing numbers

When you set up Audio Conferencing for Skype for Business and Microsoft Teams users, you can view the phone numbers that are available to them for audio conferencing. This list will have all of the audio conferencing phone numbers that are available to your organization.
  
 **Quer saber os preços?** See [Pricing for Audio Conferencing](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.** If you are looking to see if there are dial-in phone numbers available in your area or country/region, go to **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add**, and then click **New Service Numbers**. Use as listas de **País/Região**, **Estado/Região** e **Cidade** para filtrar sua pesquisa. Also, if you are looking for toll-free service numbers, select **Toll-Free** from the **State/Region** list.
  
Se houver somente um número de telefone disponível para sua organização, ele será usado como número padrão para todos os seus usuários. Quando vários números de telefone estiverem disponíveis, você pode selecionar o número de telefone padrão para cada usuário. This default number will be included in Skype for Business and Microsoft Teams meeting invitations.
  
You can see [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md) to change the dial-in phone number for a single user.
  
> [!NOTE]
> [!OBSERVAçãO] Números de discagem locais são dedicados à sua organização e são os únicos que podem ser definidos como números de telefone padrão. No entanto, números de discagem internacionais podem ser compartilhados entre várias organizações. 
  
## <a name="to-view-your-audio-conferencing-phone-numbers"></a>To view your audio conferencing phone numbers

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**, and then:
    
  - You can view the phone numbers that are available for audio conferencing.
    
  - You can also view the location, and the primary and secondary languages that will be used by the audio conferencing auto attendant.
    
> [!NOTE]
> You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number by choosing a new number from the list of available numbers in your organization. See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md). 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691).
    
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
