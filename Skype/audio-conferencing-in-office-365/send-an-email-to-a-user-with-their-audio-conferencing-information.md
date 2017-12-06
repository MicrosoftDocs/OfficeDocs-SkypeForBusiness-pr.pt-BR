---
title: "Enviar um email para um usuário com suas informações de conferência de áudio"
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
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
description: "Send your users an email with their dial-in conferencing information."
---

# Enviar um email para um usuário com suas informações de conferência de áudio

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](7440d3e2-1b49-4258-bd2c-79e9072f8c8d.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/7440d3e2-1b49-4258-bd2c-79e9072f8c8d). 
  
Às vezes, talvez seja necessário Skype para usuários de negócios ou Teams Microsoft você envie suas informações de conferência de áudio. Você pode fazer isso usando o **Skype para o Centro de administração de negócios** e clicando em **Enviar informações de conferência via email** sob as propriedades de um usuário. Quando você enviar e-mail, ele irá conter todas as informações de conferência de áudio, incluindo:
  
- O número de telefone ou de discagem da conferência para o usuário.
    
- A ID de conferência do usuário.
    
    > [!NOTE]
    > Identificações estáticas são usadas quando as pessoas em sua organização não desejam se lembrar de um número aleatório; ele poderá selecionar um determinado número ou use uma que seja fácil de lembrar. Quando IDs de conferência dinâmicos forem usados, cada reunião que um cronogramas do usuário serão obter atribuída uma ID de conferência exclusivo. Se você quiser atribuir dinâmico em vez de conferência estático IDs, [Usando IDs de dinâmico de conferência de áudio em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
Aqui está um exemplo de email enviado:
  
![Email para conferência discada](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## Enviar um email com informações de conferência de áudio para um usuário

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**e no painel de navegação esquerdo, clique em **conferência de áudio**.
    
3. Clique em **usuários** e, em seguida, selecione o usuário.
    
4. No painel Ação, clique em **Enviar informações da conferência por email**.
    
> [!TIP]
> Você também pode enviar emails para o usuário com as configurações de audioconferência editando as propriedades do usuário e, em seguida, clicando em **conferência de áudio** > **Enviar informações de conferência via email**. 
  
## O que mais devo saber sobre esse email?

- Há vários emails enviados para usuários de sua organização depois que eles estão habilitados para conferência de áudio:
    
  - Quando uma licença de **Conferência de áudio** é atribuída a elas.
    
  - Quando você redefinir manualmente audioconferência do usuário PIN.
    
  - Quando você redefine manualmente a ID de conferência do usuário.
    
  - Quando uma licença de **Conferência de áudio** seja removida deles.
    
  - Quando o provedor de audioconferência para um usuário é alterado da Microsoft para outro provedor ou **Nenhum**.
    
  - Quando o provedor de audioconferência para um usuário é alterado para Microsoft.
    
- Por padrão, o remetente dos emails serão do Office 365, mas você pode alterar o endereço de email e nome para exibição usando o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) . Para fazer alterações ao endereço de email que está enviando o email para os usuários, faça o seguinte:
    
  - Insira o endereço de email no parâmetro SendEmailFromAddress.
    
  - Defina o parâmetro SendEmailOverride como True.
    
  - Insira o nome de exibição de email no parâmetro SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Se você quiser alterar as informações do endereço de email, deve verificar se as políticas de recebimento de email de sua organização permitem emails do endereço de email personalizado definido. 
  
## Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) .
    
    Para enviar um email para o usuário com suas informações de conferência de áudio, execute o seguinte:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- Quando se trata de Windows PowerShell, Skype for Business Online é tudo sobre gerenciamento de usuários e o que os usuários são permitidos ou não fazer. Com o Windows PowerShell, você pode gerenciar Office 365 usando um único ponto de administração que pode simplificar o seu trabalho diário quando você tem várias tarefas a fazer. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem várias vantagens em velocidade, simplicidade e produtividade sobre usando somente o Centro de administração do Office 365, como quando você estiver fazendo alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre estas vantagens nos tópicos a seguir:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > O módulo do Windows PowerShell para Skype for Business Online permite criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, aceito somente em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft, em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). 
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

