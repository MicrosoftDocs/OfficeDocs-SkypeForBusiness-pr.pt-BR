---
title: "Redefinir o PIN de conferência de áudio para um usuário"
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
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
description: "Find out what you should know about PINs and how to reset them for your users. "
---

# Redefinir o PIN de conferência de áudio para um usuário

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Um PIN é um código constituído em números que são criados para cada Skype para Business e Teams Microsoft usuário que está habilitado para conferência de áudio. Audioconferência pinos são usados pelo organizadores de reunião para identificar se eles são o organizador da reunião e permitir que ele iniciar uma reunião por telefone. Se usarem o Skype para Business ou Microsoft Teams o aplicativo para iniciar a reunião, um PIN não é necessário. Se os usuários esquecem seu PIN e eles não é possível encontrá-lo no email que foi enviado quando eles foram habilitados para conferência de áudio, um administrador precisará redefinir seu PIN. Um usuário não pode redefinir sua próprias PIN.
  
Reuniões podem ser iniciados quando um usuário autenticado ingressa usando uma Skype para o aplicativo de negócios ou Teams Microsoft ou quando o organizador entre com seu PIN por telefone. Quando uma reunião exige um PIN para iniciar, os usuários que ingressar por telefone será colocada na lobby e será ouvir música em espera até que a reunião é iniciado. Se o organizador de uma reunião não exige um PIN iniciar a reunião por telefone, chamadores não ser solicitados a fornecer um PIN quando eles ingressar na reunião.
  
## Redefinir o PIN de um organizador da conferência

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**e no painel de navegação esquerdo, clique em **conferência de áudio**
    
3. Clique em **usuários**, selecione o usuário que você deseja redefinir o PIN.
    
4. No painel ação, em **PIN**, clique em **Redefinir**.
    
## O que mais você deve saber sobre PINs?

- Para fins de segurança, o PIN é mostrado somente para um administrador logon uma vez, quando o PIN é redefinido. Depois que o PIN é redefinido por um administrador, o PIN será listado como ***** no **Skype para o Centro de administração de negócios** e nos resultados quando usarem Get-CsCsOnlineDialInConfencingUser no Windows PowerShell.
    
- Enviando emails automaticamente aos usuários é ativada por padrão e os usuários receberão um email com seu PIN quando estão habilitados para conferência de áudio ou quando o PIN é redefinido. Mas se você desativou automaticamente enviando emails, um email de redefinição PIN não será enviado para um usuário e você precisará enviar manualmente as informações de PIN para o usuário.
    
- Quando uma reunião for iniciada, todos os usuários do lobby serão conectados automaticamente. Por exemplo, se dois participantes tentarem participar de uma reunião antes que ela seja iniciada, eles serão colocados no lobby e esperarão ouvindo música. Quando o organizador da reunião participar usando o PIN por telefone, a reunião será iniciada e os participantes do lobby entrarão na reunião.
    
- A configuração padrão para não permitir uma reunião ser iniciado por chamadores anônimos.
    
- Quando você habilita um usuário para conferência de áudio, por padrão, eles são enviados emails que incluem informações de conferência e seu PIN. O usuário deve ter uma caixa de correio do Office 365, porque quando um PIN é redefinido, um novo PIN será enviado para o usuário no email para o seu endereço SMTP principal (alias) que é definido para o usuário.
    
- Ao configurar conferência de áudio, defina os dígitos necessários para os pinos em sua organização. Pinos podem ter de 4 a 12 dígitos - o padrão é 5. Se você alterar a configuração de comprimento PIN, a configuração será aplicada apenas nos pinos recentemente gerados e não é aplicada para a configuração de PIN para usuários existentes que estão habilitados para conferência de áudio. Consulte [Definir o tamanho do PIN para reuniões de conferência de áudio](set-the-length-of-the-pin-for-audio-conferencing-meetings.md).
    
- O email por padrão será definido como o endereço SMTP principal do Office 365 do usuário. Você pode enviar um email para um endereço não - Office 365 como uma conta do Hotmail ou o endereço de email do MSN. Você pode substituir o endereço de email padrão usando o Windows PowerShell. Isso é útil se os usuários não tem uma caixa de correio do Exchange no Office 365.
    
- Para substituir o endereço de usuário padrão onde o email é enviado, o administrador de locatários pode usar o seguinte cmdlet: Set-CsOnlineDialInConferencingUser-amos.marble - ResetLeaderPIN - EnviarEmail - SendEmailToAddress "u@hotmail.com". O parâmetro EnviarEmail é necessário para substituir o endereço de email do usuário.
    
## Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) .
    
- Você pode definir o PIN de Amos Marble com:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell é tudo sobre gerenciamento de usuários e o que os usuários são permitidos ou não fazer. Com o Windows PowerShell, você pode gerenciar Office 365 usando um único ponto de administração que pode simplificar o seu trabalho diário quando você tem várias tarefas a fazer. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
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
  

