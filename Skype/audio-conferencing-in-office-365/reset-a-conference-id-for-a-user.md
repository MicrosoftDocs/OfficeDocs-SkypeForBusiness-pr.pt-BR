---
title: "Redefinir o ID de conferência de um usuário"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- httpsfix
- Strat_SB_PSTN
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
---

# Redefinir o ID de conferência de um usuário

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Quando as organizações ainda não foi habilitado para IDs de conferência dinâmicos, um ID de conferência estático é criada automaticamente quando uma Skype para empresas ou Teams Microsoft usuário está habilitado para conferência de áudio usando o Microsoft como provedor. Esta ID de conferência está incluído na parte inferior da reunião convites junto com os números de discagem que podem ser usados por chamadores para ligar para uma reunião. Quando o usuário discar o número de telefone, o atendedor automático para a reunião perguntará o chamador insira esta ID de conferência para que eles podem participar da reunião.
  
> [!NOTE]
> Se seu provedor de conferência Microsoft, IDs de conferência de seus usuários são definidas como dinâmico somente por padrão. Infelizmente, você não poderá alterá-la no Skype para o Centro de administração de negócios ou usando o Windows Powershell. Será necessário entrar em contato com o suporte da Microsoft. 
  
Identificações estáticas são usadas quando as pessoas em sua organização não desejam se lembrar de um número aleatório; ele poderá selecionar um determinado número ou use uma que seja fácil de lembrar. Quando IDs de conferência dinâmicos forem usados, cada reunião que um cronogramas do usuário serão obter atribuída uma ID de conferência exclusivo. Se você quiser atribuir dinâmico em vez de conferência estático IDs, [Usando IDs de dinâmico de conferência de áudio em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
IDs de conferência automaticamente apenas são definidas somente para o Skype para Business e Teams Microsoft usuários habilitados para conferência de áudio usando o Microsoft como seu provedor de audioconferência. Se você precisar redefinir um ID de conferência para um usuário que está usando um provedor de terceiros audioconferência (ACP), você precisará inserir manualmente um ID de conferência na página Propriedades do usuário.
  
## Redefinir o ID de conferência para um usuário

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Centro de administração do Skype for Business**, clique em **conferência de áudio** > **usuários**, selecione um usuário e clique em **Redefinir** no painel ação em **ID de conferência**.
    
4. No **Redefinir o ID de conferência?** janela, clique em **Sim**. Uma conferência que ID será criado automaticamente e um email enviado para o usuário com a nova ID de conferência. Por padrão, emails são enviados aos usuários, mas isso pode ser desativado.
    
    > [!NOTE]
    > Depois de redefinir a ID de conferência, um email com a nova ID de conferência será enviado para o usuário. Esse email será enviado para o endereço de email primário do usuário. Em muitos casos, para a caixa de correio do Office 365. O email contém a nova ID de conferência, o(s) número(s) de telefone padrão de discagem e as instruções de como usar a Ferramenta de Atualização de Reunião do Skype for Business para atualizar reuniões existentes. 
  
## O que mais devo saber?

- Você pode enviar todas as informações de conferência para o usuário em um email que inclui o ID de conferência e os números de discagem clicando em **Enviar informações de conferência via email** para o usuário no painel ação. Ele não envia o PIN.
    
- Um ID de conferência conterá 7 dígitos, e não é possível alterar seu tamanho no Skype para o Centro de administração de negócios ou usando o Windows PowerShell.
    
- Depois que for redefinido, o novo ID de conferência será listado em **ID de Conferência**.
    
- A ID de conferência para um usuário para conferência de áudio pode ser visualizada na parte inferior do painel ação em **conferência de áudio** quando você selecionar o usuário na página **usuários**.
    
- Após uma nova ID de conferência é criada, a ID de conferência antigo não pode ser usada por chamadores. Você deve notificar os usuários reagendar seus convites para garantir que a conferência nova que identificação é adicionada aos convites de reunião existente. Os usuários podem usar Skype for Business ferramenta de reunião para atualizar suas reuniões existentes. Para ver como baixar, instalar e executar o Skype para Business ferramenta de atualização de reunião, consulte:
    
  - [Skype for Business (Lync) Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business Online, a ferramenta de migração de reunião (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business Online, a ferramenta de migração de reunião (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## Quer saber como gerenciar com o Windows PowerShell?

- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos para usar o Windows PowerShell para gerenciar o Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

