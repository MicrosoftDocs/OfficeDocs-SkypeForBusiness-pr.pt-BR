---
title: Definir idiomas do atendedor automático para conferência de áudio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Consulte como selecionar idiomas atendedor automático serviços de audioconferência para um número de conferência de áudio.
ms.openlocfilehash: e7c4adb2129a737ec34e5641a9724bdab665cd23
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2018
---
# <a name="set-auto-attendant-languages-for-audio-conferencing"></a>Definir idiomas do atendedor automático para conferência de áudio

O atendedor automático de conferência de áudio para Skype para Teams da Microsoft e de negócios pode saudar chamadores áudio em um número de diferentes idiomas quando ingressarem em uma reunião.
  
Escolher um idioma principal e até quatro idiomas secundários. O idioma principal que você definiu será usado pela primeira vez e os idiomas secundários serão usados pelo atendedor automático que você selecionar. 
  
> [!NOTE]
>  Você pode configurar os idiomas em apenas números de telefone de acesso de áudio domésticas.
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Definir a conferência idiomas de atendedor automático

Você deve ser um [administrador global do Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) ou [Skype para negócios administrador](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para executar esta etapa.
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio**e, em seguida, clique em **Microsoft ponte**.
    
4. Selecione o número de telefone de conferência de áudio na lista e, no painel de ações, clique em **definir idiomas**. 
    
5. Na página **conjunto** de idiomas, clique na lista de **idioma principal** para exibir a lista completa de idiomas disponíveis. Se for necessário, clique em cada uma das listas **idiomas secundários** para selecionar um idioma secundário.
    
    > [!NOTE]
    > [!OBSERVAçãO] Os idiomas primário e secundários aceitos são listados. A ordem na qual você selecionar listas de será a ordem dos idiomas apresentados aos chamadores. 
  
6. Clique em **Salvar**.
    
## <a name="want-else-should-i-know"></a>O que mais devo saber?

- Para ver a lista de idiomas com suporte para conferência de áudio, consulte [idiomas com suporte de conferência de áudio](audio-conferencing-supported-languages.md).
    
- Idiomas podem ser definidos para dedicado, mas não para números de telefone compartilhado.
    
- Para ver uma lista de países/regiões na qual a conferência de áudio no Office 365 usando o Microsoft como o provedor está disponível, consulte [números de telefone de conferência de áudio](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Você deseja usar o Windows PowerShell?

Para automatizar essa etapa, você pode usar os cmdlets [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) e [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) .
  
Para saber mais, consulte [Usando o Windows PowerShell para fazer Skype comuns para tarefas de gerenciamento de negócios Online](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
