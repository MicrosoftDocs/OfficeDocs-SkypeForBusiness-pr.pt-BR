---
title: Permitir que usuários gravem o nome ao ingressar em uma reunião
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: 'Learn how to enable or disable whether your users can record their names when they join a meeting '
ms.openlocfilehash: f01d9457fee181615b8a30467ec558eb36a32e7a
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2018
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a>Permitir que usuários gravem o nome ao ingressar em uma reunião

Quando você estiver configurando a conferência de áudio no Office 365, você receberá números de telefone e o que é chamado uma ponte de conferência de áudio. Uma ponte de conferência pode conter um ou mais números de telefone.
  
A ponte de conferência atende uma chamada feita por um usuário que discou para uma reunião utilizando um telefone. A ponte de conferência respostas do chamador com prompts de voz de um atendedor automático e, em seguida, dependendo das suas configurações, pode reproduzir notificações, peça aos chamadores registrar seu nome e configurar a segurança PIN para organizadores de reunião. PINs são fornecidas aos organizadores de reuniões para permitir que eles iniciar uma reunião. Entretanto, você pode configurar a reunião sem a necessidade de um PIN para começar.
  
## <a name="set-whether-callers-should-record-their-name"></a>Definir se os chamadores devem gravar o nome

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.
    
4. Sob a **experiência de participação da reunião**, consulte a caixa de seleção **Habilitar a entrada da reunião e sair notificações para ser ativado**.
    
  - **Selecionado** Os chamadores serão solicitados a registrar seu nome antes que eles entrem na reunião. Esta opção é selecionada por padrão.
    
  - **Desmarcada** Os chamadores não ser solicitados a registrar seus nomes antes que eles entrem na reunião.
    
5. Depois de fazer suas alterações, clique em **Salvar**.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
-  Windows PowerShell é tudo sobre o gerenciamento de usuários e quais usuários têm permissão para fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações de configuração de muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Como usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Como usar o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
