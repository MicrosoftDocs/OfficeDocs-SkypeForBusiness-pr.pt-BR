---
title: "Emails que são automaticamente enviados aos usuários quando alterar suas configurações de conferência de áudio"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
description: "Learn about what information is sent automatically to users by email when their dial-in conferencing settings change. "
---

# Emails que são automaticamente enviados aos usuários quando alterar suas configurações de conferência de áudio

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Emails serão enviados automaticamente aos usuários que estão [Configurar conferência de áudio para o Skype for Business e Teams da Microsoft](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md) usando o Microsoft como provedor de audioconferência.
  
Por padrão, há quatro tipos de email que será enviada para os usuários que estão habilitados para conferência de áudio. No entanto, se você quiser limitar o número de emails enviados para usuários, você pode desativá-la. Audioconferência no Office 365 enviará emails para seus usuários de email quando:
  
- **Uma licença de conferência de áudio é atribuída a eles ou quando você está alterando o provedor de audioconferência à Microsoft.**
    
    Este email inclui a ID de conferência, o número de telefone de conferência padrão para as reuniões, a conferência de áudio PIN para o usuário e as instruções e link usar o Skype for Business Online reunião Update Tool que é usado para atualizar reuniões existentes para o usuário. Consulte [Atribuir Skype para Business e Teams Microsoft licenças](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou[Atribuir a Microsoft como provedor de audioconferência](assign-microsoft-as-the-audio-conferencing-provider.md).
    
    > [!NOTE]
    > Se sua organização tiver sido habilitada para IDs de conferência dinâmicos, todas as reuniões de um usuário que eles agendarem terá IDs de conferência exclusivo. Você pode configurar [Usando IDs de dinâmico de conferência de áudio em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Aqui está um exemplo desse email:
    
     ![Skype for Business Verify License](../images/17913e03-8b4a-4563-b58d-2f09b65fbcaa.png)
  
    Você pode encontrar mais informações sobre o Skype para Business licenciamento, conferindo [Skype para Business e Teams Microsoft complemento licenciamento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **A ID de conferência ou número de telefone de conferência padrão de um usuário for alterado.**
    
    Este email contém a ID de conferência, número de telefone de conferência padrão e as instruções e link para usar o Skype for Business Online reunião Update Tool que é usado para atualizar reuniões existentes para o usuário. Mas esse e-mail não incluir conferência de áudio PIN do usuário. Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > Se sua organização tiver sido habilitada para IDs de conferência dinâmicos, todas as reuniões de um usuário que eles agendarem terá IDs de conferência exclusivo. Você pode configurar [Usando IDs de dinâmico de conferência de áudio em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Aqui está um exemplo desse email:
    
     ![As informações sobre conferência discada foram alteradas.](../images/d6d3e028-d9fb-48c4-97c0-a73d6ade5ea3.png)
  
- **A PIN de um usuário audioconferência é redefinida.**
    
    Este e-mail contém audioconferência do organizador PIN, a ID de conferência existente e número de telefone de conferência padrão para o usuário. Consulte [Redefinir o PIN de conferência de áudio para um usuário](reset-the-audio-conferencing-pin-for-a-user.md).
    
    > [!NOTE]
    > Se sua organização tiver sido habilitada para IDs de conferência dinâmicos, todas as reuniões de um usuário que eles agendarem terá IDs de conferência exclusivo. Você pode configurar [Usando IDs de dinâmico de conferência de áudio em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Aqui está um exemplo desse email:
    
     ![PIN para conferência discada alterado.](../images/df8df4f8-d11f-41b8-9187-99e66a88831b.png)
  
- **Licença de um usuário é removida ou quando o provedor de audioconferência muda da Microsoft para outro provedor ou nenhum.**
    
    Isso acontece quando a licença de **Conferência de áudio** é removida de um usuário ou ao alterar o provedor de conferência de áudio de um usuário da Microsoft para um provedor de audioconferência terceirizado ou ao definir o provedor de **Nenhum**. Este e-mail contém as instruções e informações para o usuário usar o Skype for Business Online Meeting Update Tool para remover informações específicas de conferência de áudio, como o padrão ID da conferência telefone número ou conferência.
    
    Consulte [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) ou[Atribuir um terceiro como provedor de audioconferência](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
    Aqui está um exemplo desse email:
    
     ![A conferência discada está desativada.](../images/4ebc8ae6-b516-452e-8d27-6177e145daba.png)
  
## Alterar as mensagens de email enviadas a eles

Você pode fazer alterações para o email que será automaticamente enviado para usuários incluindo o endereço de email e o nome de exibição que está incluído  *de*  informações de contato. Por padrão, o remetente dos emails será do Office 365, mas você pode alterar o endereço de email e nome para exibição usando o Windows PowerShell e o cmdlet[Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Para fazer alterações ao endereço de email que está enviando o email para os usuários, faça o seguinte:
  
- Digite o endereço de email no parâmetro  _SendEmailFromAddress_.
    
- Digite o nome exibido no email no parâmetro  _SendEmailFromDisplayName_.
    
- Defina o parâmetro  _SendEmailOverride_ como _True_.
    
Você pode fazer alterações aos emails enviados para usuários, como o endereço de email que o email é enviado da e o nome de exibição para email, executando:
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
> Se você quiser alterar as informações do endereço de email, deve verificar se as políticas de recebimento de email de seu ambiente permitem emails dos endereços de origem personalizados especificados. > Se você decidir substituir as informações de contato  *De*  , deve verificar se os emails foram enviados corretamente aos usuários. Para isso, faça um teste com um usuário de sua organização.
  
Você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações de sua organização, incluindo email.
  
## E se você não quiser que eles recebam emails?

Quando você desabilita o envio de emails para os usuários, o email não será enviado mesmo quando um usuário obtém uma licença atribuído. Neste caso, a ID de conferência, número de telefone de conferência padrão e, mais importante, seu PIN de conferência de áudio não será enviada para o usuário. Quando isso acontece, você deve saber o usuário enviando-lhes um e-mail separado ou chamando-los.
  
Por padrão, os emails serão enviados aos usuários, mas se você quiser impedir que está recebendo emails para conferência de áudio, você pode usar o Skype para o Centro de administração de negócios ou o Windows PowerShell.
  
 **Usando o Skype para o Centro de administração de negócios**
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **conferência de áudio** > **configurações de ponte da Microsoft**.
    
4. Na página **configurações de ponte da Microsoft**, marque ou desmarque **Enviar automaticamente os emails para os usuários se alterar suas configurações de conferência de áudio**.
    
5. Clique em **Salvar**.
    
 **Usando o Windows PowerShell**
  
1. Execute os seguintes procedimentos para desabilitar o envio de email a todos os seus usuários:
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

Você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações de sua organização, incluindo email.
  
## O que mais devo saber sobre esse email?

- Para ativar em mais e desativando automaticamente enviando emails para seus usuários, consulte [Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md).
    
- Às vezes, os usuários perdem suas informações de áudio e você precisa ser capaz de enviá-las todas as suas informações de áudio para eles. Você pode fazer isso usando o Skype para o Centro de administração de negócios e clicando em **Enviar informações de conferência via email** sob as propriedades de audioconferência para um usuário. Consulte[Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-audio-conferencing-information.md). No entanto, essa informação não inclui o PIN de conferência de áudio.
    
    Este é um exemplo de email que será enviado a eles:
    
     ![Email para conferência discada](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## Quer saber como gerenciar com o Windows PowerShell?

- Por padrão, o remetente dos emails será do Office 365, mas você pode alterar o endereço de email e nome para exibição usando o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .
    
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

[Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md)
  
[Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-audio-conferencing-information.md)

