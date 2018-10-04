---
title: Ver uma lista de números de conferência de áudio no Skype para Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Saiba como procurar seus números de conferência discada de dentro do Skype para negócios Online. '
ms.openlocfilehash: 557aef5e85cdd176e2d95e1cd946ed23e00764a0
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372883"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Ver uma lista de números de conferência de áudio no Skype para Business Online

> [!NOTE]
> Para obter informações sobre números de conferência de áudio em Teams da Microsoft, consulte [ver uma lista de números de conferência de áudio em equipes da Microsoft](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams).

Quando você configura serviços de audioconferência para Skype para usuários comerciais, você pode exibir os números de telefone disponíveis para acessá-los para serviços de audioconferência. Esta lista terá que todos os números de telefone de conferência de áudio que estão disponíveis para sua organização.
  
 **Quer saber os preços?** Consulte [os preços dos serviços de audioconferência](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **Não há um recurso com uma listagem de todos os números de discagem para a Audioconferência.** Se você estiver procurando para ver se existem números de telefone de discagem disponíveis na sua área ou país/região, vá para **Skype para centro de administração de negócios** > **voz** > **Números de telefone**, clique em **Adicionar**e, em seguida, clique em **novo serviço Números**. Use as listas de **País/Região**, **Estado/Região** e **Cidade** para filtrar sua pesquisa. Além disso, se você estiver procurando por números gratuitos de serviço, selecione **chamada gratuita** do **estado/região** lista.
  
Se houver somente um número de telefone disponível para sua organização, ele será usado como número padrão para todos os seus usuários. Quando vários números de telefone estiverem disponíveis, você pode selecionar o número de telefone padrão para cada usuário. Esse número padrão será incluído no Skype para convites de reunião de negócios.
  
Você pode ver a [definir o telefone convidam números incluídos em](set-the-phone-numbers-included-on-invites.md) para alterar o número de telefone de discagem de um único usuário.
  
> [!NOTE]
> [!OBSERVAçãO] Números de discagem locais são dedicados à sua organização e são os únicos que podem ser definidos como números de telefone padrão. No entanto, números de discagem internacionais podem ser compartilhados entre várias organizações. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Para exibir seus números de telefone de conferência de áudio

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **ponte da Microsoft**e, em seguida:
    
   - Você pode exibir os números de telefone disponíveis para conferência de áudio.
    
   - Você também pode exibir a localização e os idiomas principais e secundários que serão usados pelos serviços de audioconferência atendedor automático.
    
> [!NOTE]
> Você pode ir para a **conferência de áudio** > **usuários** e selecione Propriedades do usuário para alterar o padrão de número, escolhendo um novo número da lista de números disponíveis em sua organização. Consulte [Definir convidam números incluídos no telefone](set-the-phone-numbers-included-on-invites.md). 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691).
    
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações de configuração de muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
