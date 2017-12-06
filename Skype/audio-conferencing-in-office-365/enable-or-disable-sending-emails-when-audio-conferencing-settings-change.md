---
title: "Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
description: "Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. "
---

# Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](26ea19d3-e420-4fc1-baa3-2692d17e5e1d.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/26ea19d3-e420-4fc1-baa3-2692d17e5e1d). 
  
Os usuários são automaticamente notificados por email quando estão habilitados para conferência de áudio. Pode haver momentos, porém, quando você deseja reduzir o número de emails que são enviadas para o Skype para o usuário de negócios e Teams da Microsoft. Nesses casos, você pode desativar o envio de emails.
  
Se você desabilitar o envio de emails, emails de conferência de áudio não serão enviadas para os usuários, inclusive emails para quando os usuários estão habilitados ou desabilitados para conferência de áudio, quando seu PIN for redefinido e quando a ID de conferência e a conferência padrão alterações no número de telefone .
  
Aqui está um exemplo de email que é enviado para os usuários quando eles estão habilitados para conferência de áudio:
  
![Email para conferência discada](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## Quando os emails são enviados para seus usuários?

- Há vários emails enviados para usuários de sua organização depois que eles estão habilitados para conferência de áudio:
    
  - Quando uma licença de **Conferência de áudio** é atribuída a elas.
    
  - Quando você redefinir manualmente audioconferência do usuário PIN.
    
  - Quando você redefine manualmente a ID de conferência do usuário.
    
  - Quando a licença de **Conferência de áudio** seja removida deles.
    
  - Quando o provedor de conferência de áudio de um usuário é alterado da Microsoft para outro provedor ou **Nenhum**.
    
  - Quando o provedor de conferência de áudio de um usuário é alterado para Microsoft.
    
## Habilitar ou desabilitar o email sejam enviados aos usuários

Você pode usar o Skype para o Centro de administração de negócios ou o Windows PowerShell para habilitar ou desabilitar emails enviados para os usuários.
  
 **Usando o Skype para o Centro de administração de negócios**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**e no painel de navegação esquerdo, clique em **conferência de áudio**.
    
3. Na página **configurações de ponte da Microsoft**, marque ou desmarque **Enviar automaticamente os emails para os usuários se alterar suas configurações de conferência de áudio**.
    
4. Clique em **Salvar**.
    
    > [!TIP]
    > Você também pode enviar email para um usuário com as configurações de audioconferência indo para **conferência de áudio** > **usuários**, selecionando o usuário e clicando em **Enviar informações de conferência via email**. > Se você fizer isso, um email será enviado que inclui somente o ID de conferência e número de telefone da conferência, mas não o PIN. > Para obter mais informações, consulte [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-audio-conferencing-information.md) .
  
 **Usando o Windows PowerShell**
  
- Execute os seguintes procedimentos para desabilitar o envio de emails: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Para obter ajuda com esse cmdlet, confira [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## O que mais você deve saber?

- Quando emails automáticas estão desativadas, você pode ainda manualmente acionar enviando um email com o número de identificação e telefone de conferência usando o Skype para o Centro de administração de negócios. No entanto, se você fizer isso, o PIN não serão incluído. Se você deseja redefinir o PIN de conferência de áudio e enviar emails estiver desabilitada, você precisará enviá-lo para o usuário de outra maneira.
    
- Por padrão, o remetente dos emails serão do Office 365, mas você pode alterar o endereço de email e exibir nome usando o Windows PowerShell e também usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
    > [!NOTE]
    > Se você quiser alterar as informações do endereço de email, deve verificar se as políticas de recebimento de email de seu ambiente permitem emails dos endereços de origem personalizados especificados. 
  
  - Digite o endereço de email no parâmetro  _SendEmailFromAddress_.
    
  - Digite o nome exibido no email no parâmetro  _SendEmailFromDisplayName_.
    
  - Defina o parâmetro  _SendEmailOverride_ como _True_.
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- O envio de emails a seus usuários pode ser desabilitado usando o Centro de administração do Skype for Business ou o Windows PowerShell.
    
## Quer saber como gerenciar com o Windows PowerShell?

- Você pode usar esses cmdlets para economizar tempo ou automatizar o processo.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remover CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem várias vantagens em velocidade, simplicidade e produtividade sobre usando somente o Centro de administração do Office 365, como quando você estiver fazendo alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre estas vantagens nos tópicos a seguir:
    
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

