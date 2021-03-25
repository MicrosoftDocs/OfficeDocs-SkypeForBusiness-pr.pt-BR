---
title: Consulte uma lista de números de Audioconferência no Skype for Business Online
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
description: 'Saiba como procurar seus números de conferência discada no Skype for Business Online. '
ms.openlocfilehash: f7343010cfdc34325d2f164b5560c542af0551ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114147"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Consulte uma lista de números de Audioconferência no Skype for Business Online

> [!NOTE]
> Para obter informações sobre números de Audioconferência no Microsoft Teams, consulte Uma lista de números de [Audioconferência no Microsoft Teams](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams).

Ao configurar a Audioconferência para usuários do Skype for Business, você pode exibir os números de telefone disponíveis para eles para audioconferência. Esta lista terá todos os números de telefone de audioconferência que estão disponíveis para sua organização.
  
 **Quer saber os preços?** Consulte [Preços para Audioconferência](https://products.office.com/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **Não há um recurso que contenha uma lista de todos os números de discagem para Audioconferência.** Se você estiver procurando para ver se há números de telefone discados disponíveis em sua área ou país/região, vá para o Centro de administração do **Skype for Business** Voice Phone Numbers , clique em Adicionar e clique em Novos Números de  >    >   **Serviço**.  Use as listas para País/região, **Estado/região** e **Cidade** para filtrar sua pesquisa. Além disso, se você estiver procurando por números de serviço gratuito, selecione **Gratuito** na lista **Estado/Região.**
  
Se houver somente um número de telefone disponível para sua organização, ele será usado como número padrão para todos os seus usuários. Quando vários números de telefone estiverem disponíveis, você pode selecionar o número de telefone padrão para cada usuário. Esse número padrão será incluído nos convites de reunião do Skype for Business.
  
Você pode ver [Definir os números de telefone incluídos](set-the-phone-numbers-included-on-invites.md) em convites para alterar o número de telefone discado para um único usuário.
  
> [!NOTE]
> [!OBSERVAçãO] Números de discagem locais são dedicados à sua organização e são os únicos que podem ser definidos como números de telefone padrão. No entanto, números de discagem internacionais podem ser compartilhados entre várias organizações. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Para exibir seus números de telefone de audioconferência

1. Entre com sua conta de trabalho ou de estudante.
    
2. Vá para o centro de administração > **Skype for Business**.
    
3. No Centro de administração do **Skype for Business**, na navegação à esquerda, vá para a ponte da Microsoft de **audioconferência**  >  e, em seguida:
    
   - Você pode exibir os números de telefone disponíveis para audioconferência.
    
   - Você também pode exibir o local e os idiomas primários e secundários que serão usados pelo atendimento automático de audioconferência.
    
> [!NOTE]
> Você pode ir para Usuários de **Audioconferência** e selecionar as propriedades do usuário para alterar o número padrão escolhendo um novo número na lista de números disponíveis  >   em sua organização. Consulte [Definir os números de telefone incluídos em convites](set-the-phone-numbers-included-on-invites.md). 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Get-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Get-CsOnlineDialInConferencingServiceNumber).
    
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar o Microsoft 365 ou o Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimente ou compre Audioconferência no Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
