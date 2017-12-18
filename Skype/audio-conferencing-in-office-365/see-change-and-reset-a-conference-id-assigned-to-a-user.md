---
title: "Consulte, alterar e redefina um ID de conferência atribuído a um usuário"
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
- Strat_SB_PSTN
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
---

# Consulte, alterar e redefina um ID de conferência atribuído a um usuário

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Um ID de conferência é automaticamente atribuído a uma Skype para empresas ou Teams Microsoft usuário quando eles estão configurados para conferência de áudio no Office 365 e usam a Microsoft como provedor de audioconferência. A ID de conferência atribuída pode ser estáticas ou dinâmicas e é enviada no convite da reunião quando a reunião está agendada.
  
Identificações estáticas são usadas quando as pessoas em sua organização não desejam se lembrar de um número aleatório; ele poderá selecionar um determinado número ou use uma que seja fácil de lembrar. Quando IDs de conferência dinâmicos forem usados, cada reunião que um cronogramas do usuário serão obter atribuída uma ID de conferência exclusivo. Se você quiser atribuir dinâmico em vez de conferência estático IDs, [Usando IDs de dinâmico de conferência de áudio em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Embora um ID de conferência estático será automaticamente criada e atribuída a um usuário, pode haver ocasiões quando um usuário não quer usar este e deseja defini-lo para um determinado número, ou quando os usuários não lembra ou tem perdido sua ID de conferência. Você pode usar o **Skype para o Centro de administração de negócios** e o Windows PowerShell para exibir, alterar e redefinir a sua ID de conferência.
  
Um email será enviado para o usuário com a ID de conferência e os números de telefone de conferência de áudio padrão ou se você redefinir o ID de conferência um email diferente será enviado que incluirá a ID de conferência, mas não um PIN.
  
## Exibir e alterar as IDs de conferência

### Para exibir a ID de conferência

Você pode exibir seu ID de conferência e enviá-lo aos usuários.
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Centro de administração do Skype for Business**> **audioconferência** > **usuários**, selecione o usuário que precisa ID de conferência.
    
4. Na página ação, procure em **ID de conferência**.
    
    > [!TIP]
    > Você pode enviar todas as informações de conferência para o usuário em um email que inclui a ID de conferência e números de telefone áudio clicando no link **Enviar informações de conferência via email** após selecionar o usuário na página **usuários**. 
  
    Você pode usar o Windows PowerShell para exibir a ID de conferência para um usuário. Para fazer isso, execute:
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    Consulte [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) para saber mais sobre o cmdlet.
    
### Para atribuir ou alterar a ID de conferência

Você pode atribuir ou alterar um ID de conferência para um usuário se, por exemplo, alguém quer um ID de conferência que seja fácil de lembrar.
  
> [!NOTE]
> O Skype para o Centro de administração de negócios não pode ser usado para editar um ID de conferência que foi criado automaticamente, mas você pode usar o Windows PowerShell para editar ou alterar um ID de conferência que você definiu. 
  
> Para editar ou alterar a ID de conferência de um usuário, execute:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

    > [!TIP]
    > Um ID de conferência deve conter 7 dígitos, e você não pode alterá-lo no Skype para o Centro de administração de negócios ou usando o Windows PowerShell. 
  
### Para redefinir a ID de conferência

Você pode redefinir a ID de conferência para um usuário se, por exemplo, ele a esqueceu.
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Centro de administração do Skype for Business**> **audioconferência** > **usuários**, no painel ação em **ID de conferência**, clique em **Redefinir**.
    
4. No **Redefinir o ID de conferência?** janela, clique em **Sim**. Uma conferência que ID será criado automaticamente e um email enviado para o usuário com a nova ID de conferência.
    
    Você pode redefinir a ID de conferência de um usuário com o Windows PowerShell. Para fazer isso, execute:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## O que mais você deve saber?

-     > [!IMPORTANT]
    >  Depois de uma nova ID de conferência é criada ou um for redefinido, a ID de conferência antigo não pode ser usada por chamadores. Você deve notificar os usuários reagendar seus convites para garantir que a conferência nova que identificação é adicionada aos convites de reunião existente. Os usuários podem usar o Skype for Business ferramenta de migração de reunião para atualizar suas reuniões existentes. Para ver como baixar, instalar e executar a ferramenta, consulte:> [Skype for Business (Lync) Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)> [Skype for Business Online, ferramenta de migração de reuniões (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)> [Skype for Business Online, a ferramenta de migração de reunião (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
  
- Consulte [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) para saber mais sobre o cmdlet.
    
- A ID de conferência deve atender o comprimento em dígitos definidos na ponte de conferência de áudio. Você não pode usar caracteres alfabéticos ou especiais em conferência IDs; apenas os números podem ser usados.
    
- A ID de conferência para todos os seus usuários de conferência de áudio será 7 dígitos por padrão e o número de dígitos não pode ser alterado.
    
- Se o usuário é movido da Microsoft como provedor de audioconferência para um provedor de audioconferência terceirizado ou o provedor de conferência de áudio está definido como **Nenhum**, a ID de conferência deixarão de funcionar. Consulte [Atribuir um terceiro como provedor de audioconferência](assign-a-third-party-as-the-audio-conferencing-provider.md) ou[Movendo o provedor de audioconferência de um usuário para Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md).
    
## Quer saber como gerenciar com o Windows PowerShell?

- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos para usar o Windows PowerShell para gerenciar o Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## Tópicos Relacionados

[Configurar conferência de áudio para o Skype for Business e Teams da Microsoft](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

