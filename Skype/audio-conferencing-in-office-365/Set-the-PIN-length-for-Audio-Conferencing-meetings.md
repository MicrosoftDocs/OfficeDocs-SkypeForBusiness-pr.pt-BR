---
title: "Definir o tamanho do PIN para reuniões de conferência de áudio"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/15/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
description: "Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business."
---

# Definir o tamanho do PIN para reuniões de conferência de áudio

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Quando você estiver configurando audioconferência do Skype for Business ou Teams da Microsoft, você obterá uma ponte de conferência de áudio. Uma ponte de conferência pode conter um ou mais números de telefone. O número de telefone que você definir será incluído nos convites da reunião do Skype para os aplicativos de negócios e Teams da Microsoft.
  
A ponte de conferência de áudio responde a uma chamada para as pessoas que discam para uma reunião usando um telefone. Ele responde o chamador com prompts de voz de um atendedor automático e, em seguida, dependendo das suas configurações, pode reproduzir notificações e peça aos chamadores gravarem o nome. **Configurações de ponte da Microsoft** permitem que você altere as configurações para notificações de reunião e a reunião ingressar experiência e definir o comprimento dos pinos que são usadas pelo organizadores da reunião. Organizadores de reunião usam pinos para começar reuniões se eles não é possível ingressar na reunião usando o Skype para Business ou Microsoft Teams o aplicativo.
  
## Configurar o tamanho do PIN

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **conferência de áudio** > **configurações de ponte da Microsoft**.
    
4. Em **segurança** > **tamanho do PIN**, selecione o número de dígitos desejado para o PIN e clique em **Salvar**.
    
> [!NOTE]
> Um PIN é diferente de um ID de conferência. IDs de conferência são usados pelos chamadores quando eles participam da reunião. São usados para identificar a reunião. O PIN é usado para autenticar um chamador como organizador da reunião. 
  
## Quer saber mais sobre as configurações de PIN?

- Pinos podem ter de 4 a 12 dígitos; o padrão é 5. Números são usados somente ao criar pinos. Letras e caracteres especiais não são usados.
    
- Um PIN só é necessário para o organizador da reunião quando um usuário de Teams da Microsoft ou Skype for Business já não começou a reunião. Se todos é discando para a reunião, o PIN é necessário para o organizador da reunião iniciar a reunião.
    
- Configurações de segurança PIN são aplicadas a todos os números de telefone que estão associados uma ponte da Microsoft. Elas serão aplicadas a todas as reuniões que usam os números de telefone associados a uma ponte de determinado.
    
## Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
- Para definir o número de dígitos do PIN como 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell é tudo sobre gerenciamento de usuários e o que os usuários são permitidos ou não fazer. Com o Windows PowerShell, você pode gerenciar Office 365 usando um único ponto de administração que pode simplificar o seu trabalho diário quando você tem várias tarefas a fazer. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem várias vantagens em velocidade, simplicidade e produtividade sobre usando somente o Centro de administração do Office 365, como quando você estiver fazendo alterações nas configurações para vários usuários ao mesmo tempo. Saiba mais sobre estas vantagens nos tópicos a seguir:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
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

[Configurar conferência de áudio para o Skype for Business e Teams da Microsoft](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)

