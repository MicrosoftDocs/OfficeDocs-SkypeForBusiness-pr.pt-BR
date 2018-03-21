---
title: "Atribuir um terceiro como um provedor de serviços de audioconferência"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to set up a third-party as your dial-in conferencing provider with Skype for Business. '
ms.openlocfilehash: b765e064558e9ef3a2bfaa4af2a3b6200c03f5bd
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2018
---
# <a name="assign-a-third-party-as-the-audio-conferencing-provider"></a>Atribuir um terceiro como um provedor de serviços de audioconferência

Um provedor de serviços de audioconferência fornece a *ponte de conferência*. A ponte de conferência fornece o número de telefone de discagem, os PINs e as IDs de conferência para as reuniões criadas. Você precisará atribuir um provedor de serviços de audioconferência para pessoas que estão indo para agendar ou liderança Skype para reuniões de negócios ou Teams da Microsoft.
  
> [!NOTE]
> For Microsoft Teams, um usuário não é possível usar um provedor de serviços de audioconferência de terceiros, eles deverão usar os serviços de audioconferência no Office 365, que define o provedor de serviços de audioconferência à Microsoft. 
  
## <a name="steps-to-do-before-you-can-assign-a-third-party-audio-conferencing-provider"></a>Etapas para se fazer antes de designar um provedor de serviços de audioconferência de terceiros

1. Dependendo do seu plano do Office 365, você talvez precise adquirir licenças de complemento de **Conferência de áudio** para as pessoas na sua organização que estão indo para agendar ou liderança Skype para reuniões de negócios ou Microsoft Teams usando a conferência de áudio. Para saber mais, consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. Se você adquiriu licenças de complemento de **Conferência de áudio** , atribua as pessoas na sua organização que estão indo para agendar ou liderança reuniões que utilizam o áudio da conferência. Consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
    
    > [!NOTE]
    > Se você atribuir uma licença de **Serviços de audioconferência** para alguém **depois** que você atribua um provedor de serviços de audioconferência de terceiros, essa pessoa será automaticamente definida para usar o Microsoft como seu provedor de serviços de audioconferência em vez disso! Se isso ocorrer, você precisará remover primeiro a Microsoft como um provedor de serviços de audioconferência antes de designar um provedor de serviços de audioconferência de terceiros para acessá-los.
  
3. Encontre um provedor de serviços de audioconferência de terceiros no [Microsoft identifique](https://go.microsoft.com/fwlink/?LinkId=797530). Entre em contato com ele para saber como fazer a configuração.
    
    Ele lhe fornecerá:
    
  - **Números de discagem (Chamada Tarifada)** e números para ligações gratuitas se eles estiverem disponíveis.
    
  - **IDs de conferência** que são usadas para cada pessoa que agenda reuniões. Alguns ACPs as chamam de senhas de conferência.
    
    > [!NOTE]
    > Se você fez a inicial configurar um ACP de terceiros, mas agora você precisa fazer alterações, na parte inferior da página **Microsoft Bridge** **clique aqui para configurar um provedor de serviços de audioconferência de terceiros**. 
  
    > [!NOTE]
    > Quando você habilitar uma pessoa para conferência de áudio e atribuí-las um provedor de serviços de audioconferência de terceiros, os números de áudio e as IDs de conferência (códigos de acesso) são adicionados automaticamente a qualquer **novo** Skype para reuniões Online de negócios que eles criam.
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-a-user"></a>Como atribuir um provedor de serviços de audioconferência de terceiros a um usuário

1. No **Centro de administração do Skype for Business**, escolha **Usuários**. Selecione o usuário na lista e clique em **Editar** no painel de ações.
    
2. Na página de propriedades do usuário, clique em **conferência de áudio** e insira essas informações:
    
  - **Nome do provedor** Selecione o provedor de terceiros da lista.
    
  - **Número de Chamada Tarifada padrão** Isso é necessário.
    
  - **Número de chamada gratuito padrão** Isso não é necessário.
    
  - **ID de conferência** Isso é fornecido pelo seu provedor de serviços de audioconferência.
    
3. Clique em **Salvar**.
    
4. Envie a cada pessoa o PIN que você recebeu do provedor de serviços de audioconferência. Talvez seja necessário o PIN a ser chamado na como o organizador da chamada em conferência ou líder.
    
    > [!NOTE]
    > Quando você usa um provedor de serviços de audioconferência de terceiros, não há uma maneira de ver ou definir PINs em nome organizadores de reuniões. 
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-many-people-at-the-same-time"></a>Como atribuir um provedor de serviços de audioconferência de terceiros para muitas pessoas ao mesmo tempo

1. No **Skype para centro de administração de negócios**, escolha **audioconferências** > **ponte da Microsoft**. Na parte inferior da página, clique no link na **se você gostaria de configurar um provedor de serviços de audioconferência de terceiros em vez disso, clique aqui**.
    
    > [!NOTE]
    > Se você fez a inicial configurar um ACP de terceiros, mas agora você precisa fazer alterações, na parte inferior da página de **Ponte da Microsoft** , **clique aqui para configurar um provedor de serviços de audioconferência de terceiros**. 
  
2. Na página **Configurar um provedor de serviços de audioconferência de terceiros** , em **usuários de importação e exportação**, clique em **Assistente para exportar**e siga as etapas no **Assistente para exportação de usuários**. Quando terminar, você terá um arquivo que lista as pessoas que você deseja configurar para conferência de áudio.
    
3. Envie o arquivo que você criou para seu provedor de serviços de audioconferência de terceiros. Eles serão adicionar informações de conferência de áudio para as pessoas listadas no arquivo e, em seguida, retornar o arquivo para você.
    
4. Verifique se o arquivo retornado contém as informações certas. Ouvimos falar de casos em que nem todas as pessoas listadas no arquivo obtiveram as informações certas.
    
5. Na página **Configurar um provedor de serviços de audioconferência terceiro**, em **Importar e exportar usuários**, clique em **Assistente de importação** e siga as etapas do **Assistente para importar usuários**.
    
6. Envie a cada pessoa o PIN que você recebeu do provedor de serviços de audioconferência. O PIN pode ser necessário para a chamada como organizador ou líder de chamada em conferência.
    
    > [!NOTE]
    > Quando você usa um provedor de serviços de audioconferência de terceiros, não há uma maneira de ver ou definir PINs em nome organizadores de reuniões. 
  
## <a name="when-to-use-a-third-party-audio-conferencing-provider"></a>Quando usar um provedor de serviços de audioconferência de terceiros

Se você estiver em um país ou região onde os serviços de audioconferência no Office 365 não está disponível, a qualidade de serviço não é ótima devido a seu local ou você tiver um contrato existente com um provedor de serviços de audioconferência de terceiros, recomendamos o uso de um áudio de terceiros provedor de conferência. Caso contrário, é recomendável usar o Microsoft como seu provedor de serviços de audioconferência.
  
## <a name="automate-assigning-the-third-party-audio-conferencing-provider-by-using-windows-powershell"></a>Automatizar a atribuição do provedor de audioconferência de terceiros usando o Windows PowerShell

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851).
    
    > [!NOTE]
    > Para alterar o provedor de áudio da Microsoft para um provedor de serviços de audioconferência de terceiros, você deve remover o Microsoft como um provedor de serviços de audioconferência. Para isso, use o cmdlet [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ).
  
- Para saber mais sobre como usar o Windows PowerShell, veja [Usar o Windows PowerShell para realizar tarefas de gerenciamento comuns do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).
    
## <a name="what-else-do-i-need-to-know"></a>O que mais eu preciso saber?

Uma pessoa em sua organização só pode usar um provedor de serviços de audioconferência. Para alterar o provedor de serviços de audioconferência de uma pessoa para a Microsoft, consulte [Mover o provedor de serviços de audioconferência do usuário à Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) ou [Atribuir Microsoft como um provedor de serviços de audioconferência](assign-microsoft-as-the-audio-conferencing-provider.md).
  
## <a name="related-topics"></a>Tópicos Relacionados

[Configurar conferência de áudio para o Skype for Business e Teams da Microsoft](set-up-audio-conferencing.md)
  
[Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

