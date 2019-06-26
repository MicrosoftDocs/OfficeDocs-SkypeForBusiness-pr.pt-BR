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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Consulte como selecionar idiomas para o atendedor automático para um número de Audioconferência no Skype for Business Online.
ms.openlocfilehash: 753efca2117363774865817d3095d8b981b4342c
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35220898"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Definir os idiomas para o atendedor automático de Audioconferência no Skype for Business Online

> [!Note]
> Para obter informações sobre como definir idiomas para o atendedor automático no Microsoft Teams, consulte [Definir idiomas para o atendedor automático de Audioconferência no Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

O atendedor automático de Audioconferência do Skype for Business pode saudar as pessoas que ligam em vários idiomas diferentes quando ingressarem em uma reunião.
  
Choose one primary language and up to four secondary languages. The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select. 
  
> [!NOTE]
>  Você só pode alterar os idiomas dos números de audioconferência da categoria dedicada. Não é possível alterar os idiomas do número da conferência de áudio compartilhado.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Definir os idiomas do atendedor automático da conferência

Você deve ser um [administrador global do Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) ou [administrador do Skype for Business](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para executar esta etapa.
    
1. No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para o **portal herdado**. Uma vez no portal herdado, selecione **videoconferência**e, em seguida, clique em **ponte da Microsoft**.
    
2. Selecione o número de telefone da conferência de áudio na lista e, no painel Ação, clique em **definir idiomas**. Só é possível alterar os idiomas de números dedicados de audioconferência.  
    
3. Na página **definir idiomas** , clique na lista de **idiomas principal** para exibir a lista completa de idiomas disponíveis. Se for necessário, clique em cada uma das listas de **idiomas secundários** para selecionar o idioma secundário.
    
    > [!NOTE]
    > [!OBSERVAçãO] Os idiomas primário e secundários aceitos são listados. A ordem em que você os seleciona nas listas será a ordem dos idiomas apresentados aos chamadores. 
  
4. Clique em **Salvar**.
    
## <a name="want-else-should-i-know"></a>O que mais devo saber?

- Para ver a lista de idiomas com suporte para Audioconferência, consulte [Idiomas com suporte para Audioconferência](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Os idiomas podem ser definidos para números de telefone dedicados, mas não para números compartilhados.
    
- Para ver uma lista de países/regiões onde a Audioconferência no Office 365 usando a Microsoft como provedor está disponível, consulte [Números de telefone para AudioConferência](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Você deseja usar o Windows PowerShell?

Para automatizar essa etapa, você pode usar os cmdlets [set-csonlinedialinconferencingservicenumberhttp](https://go.microsoft.com/fwlink/?LinkId=617689) e [Get-csonlinedialinconferencinglanguagessupportedhttp](https://go.microsoft.com/fwlink/?LinkId=617684) .
  
Para saber mais, consulte [usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
