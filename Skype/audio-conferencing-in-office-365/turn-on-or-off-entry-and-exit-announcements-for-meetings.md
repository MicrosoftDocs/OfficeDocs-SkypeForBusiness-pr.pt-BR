---
title: "Ativar ou desativar anúncios de entrada e de saída para reuniões"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/22/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
description: "Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. "
---

# Ativar ou desativar anúncios de entrada e de saída para reuniões

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Quando você estiver configurando audioconferência no Office 365, você obterá uma ponte de conferência de áudio. Uma ponte de conferência pode conter um ou mais números de telefone que as pessoas usarão para ligar para um Skype para empresas ou Teams Microsoft reunião.
  
A ponte de conferência responde a uma chamada para um usuário que está discando em uma reunião usando um telefone. A ponte de conferência responde o chamador com prompts de voz de um atendedor automático da conferência e, em seguida, dependendo das suas configurações, pode reproduzir notificações, peça aos chamadores gravarem o nome e configurar a segurança PIN. Um PIN é fornecido a uma Skype para empresas ou Teams Microsoft organizador da reunião e permite-las iniciar uma reunião se eles não podem começar a reunião usando um Skype para Business ou Microsoft Teams o aplicativo. Você pode configurá-no entanto, para que não é necessário um PIN para iniciar uma reunião.
  
## Definir as opções de participação da reunião

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **conferência de áudio** > **configurações de ponte da Microsoft**.
    
4. Em **experiência de participar da reunião**, marque ou desmarque **Ativar entrada de reunião e sair notificações para ser ativado**. Isso é selecionado por padrão. Se você desmarcá-la, os usuários que já ingressou na reunião não serão notificados quando alguém entra ou sai da reunião.
    
5. Em **tipo de anúncio de entrada/saída**, selecione **os nomes ou números de telefone** ou **tons**.
    
6. Marque ou desmarque **os chamadores Ask gravem o nome antes de ingressar na reunião**.
    
7. Depois de fazer suas alterações, clique em **Salvar**.
    
## Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .
    
- Quando se trata de Windows PowerShell, Skype for Business Online é tudo sobre gerenciamento de usuários e o que os usuários são permitidos ou não fazer. Com o Windows PowerShell, você pode gerenciar Office 365 usando um único ponto de administração que pode simplificar o seu trabalho diário quando você tem várias tarefas a fazer. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem várias vantagens em velocidade, simplicidade e produtividade sobre usando somente o Centro de administração do Office 365, como quando você estiver fazendo alterações nas configurações para vários usuários ao mesmo tempo. Saiba mais sobre estas vantagens nos tópicos a seguir:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > O módulo do Windows PowerShell para Skype for Business Online permite criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, aceito somente em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft, em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). 
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  
## Consulte Também
<a name="MT_Footer"> </a>

#### 

[Conferência discada no Office 365](../misctopics/dial-in-conferencing-in-office-365.md)

