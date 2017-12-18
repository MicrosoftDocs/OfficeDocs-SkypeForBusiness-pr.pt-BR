---
title: "Definir os números de telefone de conferência de áudio para organizadores incluídas na convites de reunião"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
description: "Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. "
---

# Definir os números de telefone de conferência de áudio para organizadores incluídas na convites de reunião

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Audioconferência no Office 365 permite que os usuários em sua organização criar um Skype para reuniões de negócios e Teams da Microsoft e, em seguida, permitir que os usuários discam-lo usando um telefone. No Office 365, você tem a opção de usar uma ponte de conferência de áudio da Microsoft ou usar uma ponte de conferência de áudio de terceiros que está hospedada por um provedor de audioconferência aprovados (ACP).
  
Uma ponte de conferência oferece um conjunto de números de discagem para sua organização. Todos esses números podem ser usados para ingressar nas reuniões que o organizador da reunião criou, mas você pode selecionar quais serão incluídos nos convites da reunião.
  
> [!NOTE]
> Pode haver um máximo de chamada um Tarifada e um número de telefone de chamada gratuita no convite da reunião para o organizador da reunião, mas também há um link localizado na parte inferior de cada convite de reunião que abre a lista completa de todos os números de discagem que pode ser usado para ingressar em uma reunião. 
  
## Definindo o número de discagem padrão para o organizador da reunião

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Escolha **Centros de administração** > **Skype for Business**. 
    
3. Escolha **Usuários**.
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Escolha quais usuários você deseja editar: 
    
  - Para selecionar um único usuário, escolha o nome dele.
    
  - Para selecionar todos os usuários na página, marque a caixa de seleção próximo a **Nome para exibição** na parte superior da lista.
    
  - Para selecionar vários usuários, mantenha a tecla Ctrl pressionada e escolha os usuários.
    
5. No painel direito, escolha **Editar**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. No menu suspenso de **provedor** para baixo, escolha o provedor do usuário. Dependendo do provedor, complete as seguintes caixas.
    
  - **Microsoft é o provedor**: use o **número de Chamada Tarifada padrão** e **número de chamada gratuita padrão** listas para selecionar os números de padrão para o usuário.
    
    > [!NOTE]
    > Pelo menos um número de chamada gratuita deve ser atribuído à sua ponte de conferência antes que ele possa ser definido como o número de chamada gratuita padrão de um usuário. Para obter um número de chamada gratuita, veja [Obtendo números telefônicos de serviço do Skype for Business](../what-is-phone-system-in-office-365/getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md). 
  
  - **Um terceiro é o provedor**: use os campos **Número de chamada tarifada** e **Número de chamada gratuita** para inserir os números do usuário.
    
## Redefinir números de telefone de conferência de áudio

1. No **Centro de administração do Skype for Business**, escolha **conferências de áudio**.
    
2. Na parte superior da página, escolha **usuários de discagem**.
    
3. Escolha os usuários que você deseja redefinir e, em seguida, selecione **Limpar**. 
    
    ![Choose Clear to reset phone numbers.](../images/28664b62-0d6f-42e1-960b-fdb1c6c14020.png)
  
Por padrão, quando você altera as configurações de conferência de um usuário, emails são enviados aos usuários. Para alterar isso, consulte [Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md).
  
> [!IMPORTANT]
> Quando você altera as configurações de conferência de áudio de um usuário, recorrente e futura Skype para reuniões de negócios e Teams Microsoft deve ser atualizado e enviado aos participantes. 
  
## Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) .
    
- Use o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para alterar a chamada Tarifada padrão ou o número de chamada gratuita para usuários específicos.
    
    Para mudar o número de chamada gratuita padrão de um usuário, execute:
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Use o cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** para mudar o número de chamada tarifada ou gratuita padrão de usuários com base no número padrão original ou no local.
    
    > [!NOTE]
    > Para saber qual é o BridgeID, use **Get-CsOnlineDialInConferencingBridge**.
  
  ```
  
  ```

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Para definir o número de chamada gratuita padrão para todos os usuários sem uma para +18005551234, execute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Para alterar o número de chamada gratuita padrão de todos os usuários que possuem +18005551234 como seus números de chamada gratuita padrão para +18005551239, execute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Para definir o número de chamada gratuita padrão de todos os usuários localizados nos EUA para +18005551234, execute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Para alterar o número de chamada gratuita padrão de todos os usuários que têm +18005551234 como seus números de chamada gratuita padrão para +18005551239 e reagendar todas as reuniões com novo número de chamada gratuita, execute:
    
  -     > [!NOTE]
    > O local usado acima deve corresponder às informações de contato dos usuários definidas no centro de administração do Office 365. 
  
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
  

