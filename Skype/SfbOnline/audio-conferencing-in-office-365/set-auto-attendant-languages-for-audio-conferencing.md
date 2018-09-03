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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Consulte como selecionar idiomas para o atendedor automático para um número de Audioconferência no Skype for Business Online.
ms.openlocfilehash: fe0abceba1f01b148f1a81163525be0750ef4980
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779071"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Definir os idiomas para o atendedor automático de Audioconferência no Skype for Business Online

> [!Note]
> Para obter informações sobre como definir idiomas para o atendedor automático no Microsoft Teams, consulte [Definir idiomas para o atendedor automático de Audioconferência no Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

O atendedor automático de Audioconferência do Skype for Business pode saudar as pessoas que ligam em vários idiomas diferentes quando ingressarem em uma reunião.
  
Escolha um idioma principal e até quatro idiomas secundários. O idioma primário definido será usado primeiro e os idiomas secundários serão usados pelo atendedor automático na ordem selecionada. 
  
> [!NOTE]
>  Você pode configurar os idiomas apenas em números de telefone de acesso de áudio doméstico.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Definir idiomas para o atendedor automático de conferência

Você deve ser um [administrador global do Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) ou [administrador do Skype for Business](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para executar esta etapa.
    
1. No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **Audioconferência** e clique em **Ponte Microsoft**.
    
2. Selecione o número de telefone de conferência de áudio na lista e, no painel Ações, clique em **Definir idiomas**. 
    
3. Na página **Definir idiomas**, clique na lista **Idioma principal** para visualizar a lista completa de idiomas disponíveis. Se for necessário, clique em cada uma das listas **Idiomas secundários** para selecionar um idioma secundário.
    
    > [!NOTE]
    > Os idiomas primário e secundários que oferecem suporte são listados. A ordem na qual você selecioná-los nas listas será a ordem dos idiomas apresentados aos chamadores. 
  
4. Clique em **Salvar**.
    
## <a name="want-else-should-i-know"></a>O que mais devo saber?

- Para ver a lista de idiomas com suporte para Audioconferência, consulte [Idiomas com suporte para Audioconferência](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Os idiomas podem ser definidos para números de telefone dedicados, mas não para números compartilhados.
    
- Para ver uma lista de países/regiões onde a Audioconferência no Office 365 usando a Microsoft como provedor está disponível, consulte [Números de telefone para AudioConferência](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Você deseja usar o Windows PowerShell?

Para automatizar essa etapa, você pode usar os cmdlets [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) e [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684).
  
Para saber mais, confira [Como usar o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar Audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
