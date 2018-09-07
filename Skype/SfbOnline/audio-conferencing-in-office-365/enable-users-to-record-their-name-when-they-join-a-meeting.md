---
title: Permitir que os usuários registrem seus nomes quando ingressam em uma reunião no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
description: Saiba como ativar ou desativar a opção de seus usuários gravarem seus nomes ao ingressar em uma reunião no Skype for Business Online.
ms.openlocfilehash: 6022d7ebf0e653bc43373cb00faabc207f91562a
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850037"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>Permitir que os usuários registrem seus nomes quando ingressam em uma reunião no Skype for Business Online

> [!Note]
> Se você quiser permitir que os usuários registrem seus nomes no Teams, consulte [Permitir que os usuários registrem seus nomes quando ingressam em uma reunião no Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).

Quando você estiver configurando a Audioconferência no Office 365, você receberá números de telefone e o que é chamado de ponte de audioconferência. Uma ponte de conferência pode conter um ou mais números de telefone, que podem ser um número de telefone dedicado ou compartilhado.
  
A ponte de conferência atende uma chamada feita por um usuário que discou para uma reunião usando o telefone. A ponte de conferência atende o autor da chamada com comandos de voz de um atendedor automático e, dependendo de suas configurações, pode reproduzir notificações, pedir para o autor da chamada gravar o nome dele e configurar a segurança do PIN para os organizadores da reunião. Os PINs são fornecidos aos organizadores de reuniões para permitir que eles iniciem uma reunião. Entretanto, você pode configurá-lo para que não seja necessário um PIN para iniciar uma reunião.

## <a name="set-whether-callers-should-record-their-name"></a>Definir se os autores da chamada devem registrar seu nome
    
1. No **centro de administração do Skype for Business**, no painel de navegação à esquerda, vá até **Audioconferência** > **Configurações de ponte da Microsoft**.
    
2. Em **Experiência de participação da reunião**, veja a caixa de seleção **Habilitar a ativação de notificações de entrada e saída na reunião**.
    
  - Os autores de chamadas **marcados**serão solicitados a gravarem o nome antes de entrarem na reunião. Esta opção é selecionada por padrão.
    
  - Os autores de chamadas **desmarcados**não serão solicitados a gravarem o nome antes de entrarem na reunião.
    
3. Depois de fazer as alterações, clique em **Salvar**.
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757).
    
-  O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- O Windows PowerShell tem muitas vantagens de velocidade, simplicidade e produtividade em comparação com o uso exclusivo do Centro de administração do Office 365, como, por exemplo, ao fazer alterações em configurações para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
