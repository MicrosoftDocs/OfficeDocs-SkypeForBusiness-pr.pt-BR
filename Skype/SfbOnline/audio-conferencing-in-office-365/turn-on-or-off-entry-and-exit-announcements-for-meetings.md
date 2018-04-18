---
title: Ativar ou desativar anúncios de entrada e de saída para reuniões
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
description: 'Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. '
ms.openlocfilehash: a9c3788db6b5742b4f2b41961c3843b4939c315b
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2018
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a>Ativar ou desativar anúncios de entrada e de saída para reuniões

Quando você estiver configurando a conferência de áudio no Office 365, você receberá uma ponte de conferência de áudio. Uma ponte de conferência pode conter um ou mais números de telefone que as pessoas usarão para efetuar uma chamada para um Skype para reunião de negócios ou Teams da Microsoft. 
  
A ponte de conferência atende uma chamada feita por um usuário que discou para uma reunião utilizando um telefone. A ponte de conferência respostas do chamador com prompts de voz de um atendedor automático de conferência e, em seguida, dependendo das suas configurações, pode reproduzir notificações, peça aos chamadores registrar seu nome e configurar a segurança PIN. Um PIN é fornecido para um Skype para negócios ou Microsoft Teams organizador da reunião e permite que eles iniciar uma reunião se eles não é possível iniciar a reunião usando um Skype para aplicativo de negócios ou Teams da Microsoft. Você pode, no entanto, defini-lo para que não é necessário um PIN para iniciar uma reunião.
  
## <a name="setting-meeting-join-options"></a>Definir as opções de participação da reunião

**Usando equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**. 

2. Na parte superior da página **Pontes de conferência** , clique em **Configurações de ponte**. 

3. No painel de **configurações de ponte** , habilitar ou desabilitar a **Habilitar a entrada da reunião e sair notificações para ser ativado**. Esta opção é selecionada por padrão. Se você desmarcar a ele, os usuários que já tenham ingressado na reunião não serão notificados quando alguém entra ou sai da reunião.
    
4. Em **tipo de anúncio de entrada/saída**, selecione **nomes ou números de telefone** ou **tons**.
    
5. Habilitar ou desabilitar **os chamadores Ask registrar seus nomes antes de ingressar na reunião**.
    
6. Depois de fazer as alterações, clique em **Aplicar**.

**Usando o Skype para o Centro de administração de negócios**
    
1. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.
    
2. Sob a **experiência de participação da reunião**, marque ou desmarque **Habilitar a entrada da reunião e sair notificações para ser ativado**. Esta opção é selecionada por padrão. Se você desmarcar a ele, os usuários que já tenham ingressado na reunião não serão notificados quando alguém entra ou sai da reunião.
    
3. Em **tipo de anúncio de entrada/saída**, selecione **nomes ou números de telefone** ou **tons**.
    
4. Marque ou desmarque **os chamadores Ask registrar seus nomes antes de ingressar na reunião**.
    
5. Depois de fazer suas alterações, clique em **Salvar**.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ).
    
-  No que diz respeito ao Windows PowerShell, o Skype for Business Online gerencia os usuários e o que eles podem ou não fazer. No Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar o trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações nas configurações de muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Perguntas comuns sobre a audioconferência](audio-conferencing-common-questions.md)
