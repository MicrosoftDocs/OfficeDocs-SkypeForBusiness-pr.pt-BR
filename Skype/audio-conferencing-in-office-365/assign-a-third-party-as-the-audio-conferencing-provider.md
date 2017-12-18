---
title: "Atribuir um terceiro como provedor de audioconferência"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/22/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
description: "Learn how to set up a third-party as your dial-in conferencing provider with Skype for Business. "
---

# Atribuir um terceiro como provedor de audioconferência

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Um provedor de audioconferência fornece a  *ponte de conferência*  . A ponte de conferência fornece o número de discagem, pinos e IDs de conferência para reuniões que são criados. Você só precisa atribuir um provedor de audioconferência para as pessoas que estiverem indo para agendar ou conduzir reuniões de Teams da Microsoft ou Skype for Business.
  
> [!NOTE]
> Para Teams da Microsoft, um usuário não pode usar um provedor de audioconferência terceirizado, eles devem usar audioconferência no Office 365, que define o provedor de audioconferência à Microsoft. 
  
## Etapas para fazer antes de atribuir um provedor de audioconferência terceirizado

1. Dependendo do plano do Office 365, talvez seja necessário comprar licenças do suplemento de **Conferência de áudio** para as pessoas em sua organização que pretende agendar ou cliente potencial Skype para empresas ou Teams Microsoft reuniões usando conferências de áudio. Para saber mais, consulte[Skype para Business e Teams Microsoft complemento licenciamento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. Se você adquiriu licenças do suplemento de **Conferência de áudio**, atribuí-las com as pessoas em sua organização estão indo para agendar ou conduzir reuniões que usam a conferência de áudio. Consulte [Atribuir Skype para Business e Teams Microsoft licenças](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
    
    > [!NOTE]
    > Se você atribuir uma licença de **Conferência de áudio** para alguém **depois** que você atribuir um provedor de audioconferência terceirizado, essa pessoa será definida automaticamente para usar a Microsoft como seu provedor de conferência de áudio, em vez disso! Se isso acontecer, você precisará primeiro remover Microsoft como provedor de conferência de áudio antes de atribuir um provedor de audioconferência terceirizado a elas.
  
3. Encontre um provedor de audioconferência terceirizado no [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530). Contate-los e descubra como fazer as coisas configurar com eles.
    
    Ele lhe fornecerá: 
    
  - **Números de discagem (Chamada Tarifada)** e números de chamada gratuita se eles estiverem disponíveis.
    
  - **IDs de conferência** que são usadas para cada pessoa que agenda reuniões. Alguns ACPs as chamam de senhas de conferência.
    
    > [!NOTE]
    > Se você tiver feito a inicial configurar para um ACP de terceiros, mas agora, você precisa fazer alterações, na parte inferior da página de **Ponte da Microsoft**, **clique aqui para configurar um provedor de audioconferência terceirizado**. 
  
    > [!NOTE]
    > Quando você ativar uma pessoa para conferência de áudio e atribuí-las um provedor de audioconferência terceirizado, os números de áudio e IDs de conferência (senhas) são adicionadas automaticamente a qualquer **nova** reuniões Skype for Business Online que criam.
  
## Como atribuir um provedor de conferência de áudio de terceiros a um usuário

1. No **Centro de administração do Skype for Business**, escolha **Usuários**. Selecione o usuário na lista e clique em **Editar** no painel de ações.
    
2. Na página de propriedades do usuário, clique em **conferência de áudio** e insira estas informações:
    
  - **Nome do provedor**: selecione o provedor terceiro na lista.
    
  - **Número de Chamada Tarifada padrão** Isso é necessário.
    
  - **Número de chamada gratuito padrão** Isso não é necessário.
    
  - **ID de conferência** Isso é fornecido pelo seu provedor de audioconferência.
    
3. Clique em **Salvar**.
    
4. Envie o PIN que você recebeu do provedor de audioconferência para cada pessoa. O PIN pode ser necessário ligar como o organizador de chamada em conferência ou líder.
    
    > [!NOTE]
    > Quando você usa um provedor de audioconferência terceirizado, não há uma maneira para ver ou definir pinos em nome de organizadores de reuniões. 
  
## Como atribuir um provedor de audioconferência terceirizado a muitas pessoas ao mesmo tempo

1. No **Centro de administração do Skype for Business**, escolha **audioconferência** > **ponte da Microsoft**. Na parte inferior da página, clique no link no **se você gostaria de configurar um provedor de conferência de áudio de terceiro em vez disso, clique aqui**.
    
    > [!NOTE]
    > Se você tiver feito a inicial configurar para um ACP de terceiros, mas agora, você precisa fazer alterações, na parte inferior da página de **Ponte da Microsoft**, **clique aqui para configurar um provedor de audioconferência terceirizado**. 
  
2. Na página **Configurar um provedor de audioconferência de terceiros**, em **usuários de importação e exportação**, clique em **Assistente de exportação** e siga as etapas no **Assistente para exportar usuários**. Quando terminar, você terá um arquivo que lista as pessoas que você deseja configurar para conferência de áudio.
    
3. Envie o arquivo que você criou para seu provedor de audioconferência terceirizado. Irão adicionar informações de conferência de áudio para as pessoas listadas no arquivo e, em seguida, retornar o arquivo para você.
    
4. Verifique se o arquivo retornado contém as informações certas. Ouvimos falar de casos em que nem todas as pessoas listadas no arquivo obtiveram as informações certas. 
    
5. Em **Configurar uma página de provedor de serviços de audioconferência terceirizado**, em **usuários de importação e exportação**, clique em **Assistente de importação** e siga as etapas no **Assistente de importação de usuários**
    
6. Envie o PIN que você recebeu do provedor de audioconferência para cada pessoa. O PIN pode ser necessário ligar como o organizador de chamada em conferência ou líder.
    
    > [!NOTE]
    > Quando você usa um provedor de audioconferência terceirizado, não há uma maneira para ver ou definir pinos em nome de organizadores de reuniões. 
  
## Quando usar um provedor de audioconferência terceirizado

Se você estiver em um país ou região onde audioconferência no Office 365 não está disponível, a qualidade do serviço não é ótima devido a sua localização, ou você tem um contrato existente com um provedor de audioconferência terceirizado, recomendamos o uso de um áudio de terceiros provedor de conferência. Caso contrário, é recomendável usar a Microsoft como seu provedor de audioconferência.
  
## Automatizar a atribuição do provedor de audioconferência de terceiros usando o Windows PowerShell

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851).
    
    > [!NOTE]
    > Para alterar o provedor de áudio da Microsoft para um provedor de audioconferência terceirizado, você deve remover o Microsoft como provedor de audioconferência. Para fazer isso, use o cmdlet [Desativar-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) .
  
- Para saber mais sobre como usar o Windows PowerShell, veja [Usar o Windows PowerShell para realizar tarefas de gerenciamento comuns do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).
    
## O que mais preciso saber?

Uma pessoa em sua organização só pode usar um provedor de audioconferência. Para alterar o provedor de conferência de áudio de uma pessoa para a Microsoft, consulte [Movendo o provedor de audioconferência de um usuário para Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) ou[Atribuir a Microsoft como provedor de audioconferência](assign-microsoft-as-the-audio-conferencing-provider.md).
  
## Tópicos Relacionados

[Configurar conferência de áudio para o Skype for Business e Teams da Microsoft](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

