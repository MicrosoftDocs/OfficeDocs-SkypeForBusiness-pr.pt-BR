---
title: "Iniciar uma conferência de áudio por telefone sem um PIN"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
description: "Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. "
---

# Iniciar uma conferência de áudio por telefone sem um PIN

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Pode ser frustrante para os usuários que ingressam em uma reunião a ser realizado no lobby da reunião ouvir música porque o Skype for Business ou Teams Microsoft organizador da reunião ainda não começou a reunião.
  
Se o organizador da reunião chamadas em para a reunião, por padrão, é necessário um PIN para iniciar uma reunião. Você pode configurá-lo para que qualquer pessoa pode discar para uma reunião e não ser solicitado a fornecer um PIN iniciar a reunião. Você pode usar o Skype para o Centro de administração de negócios para ativar ou desativar essa configuração para um único usuário.
  
Um PIN não é necessário para o organizador da reunião se alguém começou a reunião de uma Skype para Business ou Microsoft Teams o aplicativo. Um PIN só é necessário quando um reunião organizador entre seus ao longo de um telefone. O PIN para reuniões é enviado para o usuário áudio quando eles são atribuídos a licença de **Conferência de áudio** e estão habilitados para conferência de áudio. Consulte[Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-audio-conferencing-information.md) e[Emails que são automaticamente enviados aos usuários quando alterar suas configurações de conferência de áudio](emails-that-are-automatically-sent-to-users-when-their-audio-conferencing-settin.md).
  
## Habilitar ou desabilitar chamadores anônimos para participar de uma reunião

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **conferência de áudio** > **usuários**.
    
4. Na lista, selecione o usuário e no painel ação, clique em **Editar**.
    
5. Na página de propriedades do usuário, em **Opções de reunião**, marque ou desmarque **Permitir que não autenticado chamadores para ser primeira pessoas em uma reunião. Se não, em seguida, eles serão aguardar no lobby até que um usuário autenticado une**.
    
6. Clique em **Salvar**.
    
 **Para habilitar ou desabilitar chamadores anônimos a todas as reuniões do usuário usando o Windows Powershell**
  
- Execute o seguinte: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## O que mais você deve saber?

- Se você deseja redefinir o PIN, consulte [Redefinir o PIN de conferência de áudio para um usuário](reset-the-audio-conferencing-pin-for-a-user.md).
    
- Se o acesso anônimo ou não exigir um PIN iniciar uma reunião, estiver ativado:
    
  - Se a reunião ainda não começou (há ninguém da reunião ainda): um chamador será solicitado se ele for o organizador; Se ele diz Sim, ele será solicitado para seu PIN e depois ele insere o PIN, a reunião será iniciado e o usuário será ingressar na reunião.
    
  - Se a reunião já iniciou (alguém já está na reunião): um chamador não será avisado se ele for o organizador e ele nunca será solicitado o PIN; a reunião já é iniciada e o chamador ingressarão-lo.
    
- Se o acesso anônimo ou não exigir um PIN iniciar uma reunião, é desativado:
    
  - Se a reunião ainda não começou (há ninguém da reunião ainda): um chamador não será avisado se ela for o organizador, e ela nunca será solicitada o PIN. Como a configuração do organizador está definida para desativado, a reunião será iniciado e os chamadores anônimos ingressará na reunião.
    
  - Se a reunião já iniciou (alguém já está na reunião): um chamador não será avisado se ela for o organizador, e ela nunca será solicitada o PIN, a reunião já é iniciada e o chamador ingressarão-lo.
    
## Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo de mais de um usuário, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) .
    
- Quando se trata de Windows PowerShell, Skype for Business Online é tudo sobre gerenciamento de usuários e o que os usuários são permitidos ou não fazer. Com o Windows PowerShell, você pode gerenciar Office 365 usando um único ponto de administração que pode simplificar o seu trabalho diário quando você tem várias tarefas a fazer. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem várias vantagens em velocidade, simplicidade e produtividade sobre usando somente o Centro de administração do Office 365, como quando você estiver fazendo alterações nas configurações para vários usuários ao mesmo tempo. Saiba mais sobre estas vantagens nos tópicos a seguir:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > O módulo do Windows PowerShell para Skype for Business Online permite criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, aceito somente em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft, em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). 
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

