---
title: Definir os idiomas para o atendedor automático de Audioconferência no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Consulte como selecionar idiomas para o atendedor automático para um número de Audioconferência no Skype for Business Online.
ms.openlocfilehash: 15eca114c4f3d108a078642e6af23923fe817f66
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58584425"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Definir os idiomas para o atendedor automático de Audioconferência no Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Para obter informações sobre como definir idiomas para o atendedor automático no Microsoft Teams, consulte [Definir idiomas para o atendedor automático de Audioconferência no Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

O atendedor automático de Audioconferência do Skype for Business pode saudar as pessoas que ligam em vários idiomas diferentes quando ingressarem em uma reunião.
  
Escolha um idioma principal e até quatro idiomas secundários. O idioma principal que você definir será usado primeiro e os idiomas secundários serão usados pelo assistente automático para que você selecione. 
  
> [!NOTE]
>  Você só pode alterar os idiomas dos números de audioconferência que são da categoria Dedicado. Os idiomas do número de audioconferência compartilhada não podem ser alterados.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Definir os idiomas de atendimento automático de conferência

Você deve ser um [administrador global ou](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) Skype for Business [para](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) executar esta etapa.
    
1. No centro **Skype for Business de** administração , na navegação à esquerda, vá para **Portal Herdada**. Uma vez no portal herdado, selecione **Audioconferência** e clique em **Ponte da Microsoft.**
    
2. Selecione o número de telefone de audioconferência na lista e, no painel Ação, clique em **Definir idiomas**. Só é possível alterar os idiomas dos números de audioconferência dedicados.  
    
3. Na página **Definir idiomas,** clique na **lista Idioma principal** para exibir a lista completa de idiomas disponíveis. Se precisar, clique em cada uma das listas de idiomas **secundários** para selecionar idioma secundário.
    
    > [!NOTE]
    > [!OBSERVAçãO] Os idiomas primário e secundários aceitos são listados. A ordem na qual você os seleciona nas listas será a ordem dos idiomas apresentados aos chamadores. 
  
4. Clique em **Salvar**.
    
## <a name="want-else-should-i-know"></a>O que mais devo saber?

- Para ver a lista de idiomas com suporte para Audioconferência, consulte [Idiomas com suporte para Audioconferência](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Os idiomas podem ser definidos para números de telefone dedicados, mas não para números compartilhados.
    
- Para ver uma lista de países/regiões em que a Audioconferência em Microsoft 365 ou Office 365 usando a Microsoft como o provedor está disponível, consulte Telefone números para [Audioconferência](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Você deseja usar o Windows PowerShell?

Para automatizar essa etapa, você pode usar os cmdlets [Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) e [Get-CsOnlineDialInConferencingLanguagesSupported.](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported)
  
Para saber mais, consulte [Using Windows PowerShell to do common Skype for Business Online management tasks](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimente ou compre Audioconferência em Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
