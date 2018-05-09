---
title: Ver uma lista de números de conferência de áudio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to look up your dial-in conferencing numbers from within Skype for Business. '
ms.openlocfilehash: bccd4a5c02dbb6bc32c27e315b80a39705284429
ms.sourcegitcommit: b93d1a0012aacb164d700db0143683cb6f276bf4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2018
---
# <a name="see-a-list-of-audio-conferencing-numbers"></a>Ver uma lista de números de conferência de áudio

Quando você configura serviços de audioconferência para Skype para usuários empresariais e Teams da Microsoft, você pode exibir os números de telefone disponíveis para acessá-los para serviços de audioconferência. Esta lista terá que todos os números de telefone de conferência de áudio que estão disponíveis para sua organização.
  
 **Quer saber os preços?** Consulte [os preços dos serviços de audioconferência](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **Não há um recurso que contém uma lista de todos os números de discagem para conferência de áudio.** Se você estiver procurando para ver se existem números de telefone de discagem disponíveis na sua área ou país/região, vá para **Skype para centro de administração de negócios** > **voz** > **Números de telefone**, clique em **Adicionar**e, em seguida, clique em **novo serviço Números**. Use as listas de **País/Região**, **Estado/Região** e **Cidade** para filtrar sua pesquisa. Além disso, se você estiver procurando por números gratuitos de serviço, selecione **chamada gratuita** do **estado/região** lista.
  
Se houver somente um número de telefone disponível para sua organização, ele será usado como número padrão para todos os seus usuários. Quando vários números de telefone estiverem disponíveis, você pode selecionar o número de telefone padrão para cada usuário. Esse número padrão será incluído no Skype para convites de reunião de negócios e Teams da Microsoft.
  
Você pode ver a [definir o telefone convidam números incluídos em](set-the-phone-numbers-included-on-invites.md) para alterar o número de telefone de discagem de um único usuário.
  
> [!NOTE]
> [!OBSERVAçãO] Números de discagem locais são dedicados à sua organização e são os únicos que podem ser definidos como números de telefone padrão. No entanto, números de discagem internacionais podem ser compartilhados entre várias organizações. 
  
## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Para exibir seus números de telefone de conferência de áudio

![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, vá para **reuniões** > **pontes de conferência**. 
2.  Exiba os números de telefone disponíveis para conferência de áudio.

- Também é possível exibir o local e o idioma principal que será usado pelo atendedor automático de conferência de áudio.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
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
  
