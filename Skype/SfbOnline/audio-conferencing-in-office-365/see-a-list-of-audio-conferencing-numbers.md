---
title: Ver uma lista de números de audioconferência no Skype for Business Online
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Saiba como Pesquisar os números de conferência discada no Skype for Business online. '
ms.openlocfilehash: 48cca375f2039a1cebbd07100a8bcd8d275f55f0
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164680"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Ver uma lista de números de audioconferência no Skype for Business Online

> [!NOTE]
> Para obter informações sobre números de audioconferência no Microsoft Teams, consulte [ver uma lista de números de audioconferência no Microsoft Teams](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams).

Ao configurar a conferência de áudio para usuários do Skype for Business, você pode visualizar os números de telefone que estão disponíveis para conferências de áudio. Esta lista terá todos os números de telefone de conferência de áudio disponíveis para a sua organização.
  
 **Quer saber os preços?** Confira [preços para conferências de áudio](https://products.office.com/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **Não há um recurso que contenha uma lista de todos os números de discagem para Audioconferência.** Se você estiver procurando ver se há números**de telefone de** > discagem disponíveis em sua área ou país/região, acesse o >  **centro de administração do Skype for Business**, clique em **Adicionar**e, em**seguida, clique**em **novos números de serviço**. Use as listas para **** País/região, **Estado/região**e **Cidade** para filtrar sua pesquisa. Além disso, se você estiver procurando números de serviço de chamada gratuita, selecione **gratuito** na lista de **Estados/regiões** .
  
Se houver somente um número de telefone disponível para sua organização, ele será usado como número padrão para todos os seus usuários. Quando vários números de telefone estiverem disponíveis, você pode selecionar o número de telefone padrão para cada usuário. Este número padrão será incluído nos convites para reunião do Skype for Business.
  
Você pode ver [definir os números de telefone incluídos nos convites](set-the-phone-numbers-included-on-invites.md) para alterar o número de telefone de discagem de um único usuário.
  
> [!NOTE]
> [!OBSERVAçãO] Números de discagem locais são dedicados à sua organização e são os únicos que podem ser definidos como números de telefone padrão. No entanto, números de discagem internacionais podem ser compartilhados entre várias organizações. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Para ver os números de telefone da conferência de áudio

1. Entre com sua conta corporativa ou de estudante.
    
2. Vá para o centro de administração > **Skype for Business**.
    
3. No **centro de administração do Skype for Business**, no painel de navegação à esquerda, vá para **conferência** > de áudio**Microsoft Bridge**e, em seguida:
    
   - Você pode ver os números de telefone que estão disponíveis para videoconferências.
    
   - Você também pode exibir o local e os idiomas primário e secundário que serão usados pelo atendedor automático da audioconferência.
    
> [!NOTE]
> Você pode acessar**usuários** de **audioconferência** > e selecionar as propriedades do usuário para alterar o número padrão escolhendo um novo número na lista de números disponíveis em sua organização. Consulte [definir os números de telefone incluídos nos convites](set-the-phone-numbers-included-on-invites.md). 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691).
    
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar o Microsoft 365 ou o Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está realizando alterações de configuração para muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar videoconferências no Microsoft 365 ou no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
