---
title: Permitir que os usuários registrar seus nomes quando eles ingressam em uma reunião em Skype para negócios Online
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Aprenda a habilitar ou desabilitar se seus usuários podem registrar seus nomes quando eles ingressam em uma reunião em Skype para negócios Online.
ms.openlocfilehash: 0e330d5efdd7325a8db48aa679d6ecbb9264c345
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884717"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>Permitir que os usuários registrar seus nomes quando eles ingressam em uma reunião em Skype para negócios Online

> [!Note]
> Se você quiser permitir que os usuários registrem seus nomes no Teams, consulte [Permitir que os usuários registrem seus nomes quando ingressam em uma reunião no Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).

Quando você estiver configurando a conferência de áudio no Office 365, você receberá números de telefone e o que é chamado uma ponte de conferência de áudio. Uma ponte de conferência pode conter um ou mais números de telefone.
  
A ponte de conferência atende uma chamada feita por um usuário que discou para uma reunião utilizando um telefone. A ponte de conferência respostas do chamador com prompts de voz de um atendedor automático e, em seguida, dependendo das suas configurações, pode reproduzir notificações, peça aos chamadores registrar seu nome e configurar a segurança PIN para organizadores de reunião. PINs são fornecidas aos organizadores de reuniões para permitir que eles iniciar uma reunião. Entretanto, você pode configurar a reunião sem a necessidade de um PIN para começar.

## <a name="set-whether-callers-should-record-their-name"></a>Definir se os chamadores devem gravar o nome
    
1. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.
    
2. Em **Experiência de participação da reunião**, veja a caixa de seleção **Habilitar a ativação de notificações de entrada e saída na reunião**.
    
  - **Selecionado** Os chamadores serão solicitados a registrar seu nome antes que eles entrem na reunião. Esta opção é selecionada por padrão.
    
  - **Desmarcada** Os chamadores não ser solicitados a registrar seus nomes antes que eles entrem na reunião.
    
3. Depois de fazer suas alterações, clique em **Salvar**.
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
-  Windows PowerShell é tudo sobre o gerenciamento de usuários e quais usuários têm permissão para fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
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
