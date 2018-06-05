---
title: Configurar a Unificação de Mensagens do Exchange Server para a caixa postal do Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/19/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Resumo: Configure o Unificação de mensagens do Exchange Server para Skype para caixa postal Business Server.'
ms.openlocfilehash: 5cc8825e04e348004f4105d483eb7a92dd0e5c60
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569219"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-2015-voice-mail"></a><span data-ttu-id="9e98b-103">Configurar a Unificação de Mensagens do Exchange Server para a caixa postal do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9e98b-103">Configure Exchange Server Unified Messaging for Skype for Business Server 2015 voice mail</span></span>
 
<span data-ttu-id="9e98b-104">**Resumo:** Configure Unificação de mensagens do Exchange Server do Skype para caixa postal Business Server.</span><span class="sxs-lookup"><span data-stu-id="9e98b-104">**Summary:** Configure Exchange Server Unified Messaging for Skype for Business Server voice mail.</span></span>
  
<span data-ttu-id="9e98b-105">Skype para Business Server 2015 permite que você tenha mensagens da caixa postal armazenadas no Exchange Server 2016 ou Exchange Server 2013; Essas mensagens de caixa postal aparecerão como mensagens de email nas caixas de entrada dos usuários.</span><span class="sxs-lookup"><span data-stu-id="9e98b-105">Skype for Business Server 2015 enables you to have voicemail messages stored in Exchange Server 2016 or Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> 
  
<span data-ttu-id="9e98b-106">Se você já tiver configurado a autenticação de servidor-para-servidor entre o Skype para Business Server 2015 e Exchange Server 2016 ou Exchange Server 2013, em seguida, você estará pronto para configurar a Unificação de mensagens.</span><span class="sxs-lookup"><span data-stu-id="9e98b-106">If you have already configured server-to-server authentication between Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you are ready to setup unified messaging.</span></span> <span data-ttu-id="9e98b-107">Para fazer isso, você deve primeiro criar e atribuir um novo plano de discagem mensagens unificadas em seu servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="9e98b-107">To do so, you must first create and assign a new unified messaging dial plan on your Exchange Server.</span></span> <span data-ttu-id="9e98b-108">Por exemplo, estes dois comandos (executados de dentro do Shell de gerenciamento do Exchange) configurar um novo plano de discagem de 3 dígitos para o Exchange:</span><span class="sxs-lookup"><span data-stu-id="9e98b-108">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="9e98b-p102">O primeiro comando no exemplo, o parâmetro VoIPSecurity e o valor de parâmetro "Secured" indica que o canal de sinalização é criptografado usando TLS. O URIType "SipName" indica que as mensagens serão enviadas e recebidas usando o protocolo SIP e o CountryOrRegionCode de 1 indica que o plano de discagem se aplica aos EUA.</span><span class="sxs-lookup"><span data-stu-id="9e98b-p102">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS). The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>
  
<span data-ttu-id="9e98b-111">No segundo comando, o valor do parâmetro para o parâmetro ConfiguredInCountryOrRegionGroups especifica os grupos no país que podem ser usados com este plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="9e98b-111">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="9e98b-112">O valor do parâmetro "em qualquer lugar,\*,\*,\*" define o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9e98b-112">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>
  
- <span data-ttu-id="9e98b-113">Nome do grupo ("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="9e98b-113">Group name ("Anywhere")</span></span>
    
- <span data-ttu-id="9e98b-114">AllowedNumberString (\*, um caractere curinga indicando que qualquer sequência numérica é permitida)</span><span class="sxs-lookup"><span data-stu-id="9e98b-114">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>
    
- <span data-ttu-id="9e98b-115">DialNumberString (\*, um caractere curinga indicando que qualquer número discado é permitido)</span><span class="sxs-lookup"><span data-stu-id="9e98b-115">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>
    
- <span data-ttu-id="9e98b-116">TextComment (\*, um caractere curinga indicando que qualquer comando de texto é permitido)</span><span class="sxs-lookup"><span data-stu-id="9e98b-116">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>
    
> [!NOTE]
> <span data-ttu-id="9e98b-117">Criar um novo plano de discagem também criará uma Política de Caixa de Correio Padrão.</span><span class="sxs-lookup"><span data-stu-id="9e98b-117">Creating a new dial plan will also create a Default Mailbox Policy.</span></span> 
  
<span data-ttu-id="9e98b-118">Após criar e configurar o novo plano de discagem, você deve adicionar esse plano ao seu servidor do unificação de mensagens e modificar o modo de inicialização do servidor; em particular, você deve definir o modo de inicialização para "Dual".</span><span class="sxs-lookup"><span data-stu-id="9e98b-118">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="9e98b-119">Você pode executar essas tarefas de dentro do Shell de gerenciamento do Exchange:</span><span class="sxs-lookup"><span data-stu-id="9e98b-119">You can perform both of these tasks from within the Exchange Management Shell:</span></span>
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

<span data-ttu-id="9e98b-120">Após o servidor do unified messaging ter sido configurado, você Avançar deve executar o cmdlet Enable-ExchangeCertificate para garantir que o seu certificado do Exchange é aplicado ao serviço do unified messaging:</span><span class="sxs-lookup"><span data-stu-id="9e98b-120">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

<span data-ttu-id="9e98b-p105">Após o certificado ter sido atribuído corretamente, você deve parar e reiniciar o serviço MsExchangeUM no servidor do unified messaging. Este serviço deve ser parado e reiniciado a qualquer momento que você alterar o modo de inicialização.</span><span class="sxs-lookup"><span data-stu-id="9e98b-p105">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>
  
<span data-ttu-id="9e98b-123">Após finalizar a configuração do servidor do unified messaging, é possível configurar o Roteador de Chamada UM:</span><span class="sxs-lookup"><span data-stu-id="9e98b-123">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

<span data-ttu-id="9e98b-124">Como o modo de inicialização foi alterado, você deve parar e reiniciar o serviço do MsExchangeUMCR no computador hospedando o Roteador de Chamada UM.</span><span class="sxs-lookup"><span data-stu-id="9e98b-124">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>
  
<span data-ttu-id="9e98b-p106">Para concluir a configuração do unified messaging, você precisa criar uma política de caixa de correio do UM e usar essa política para habilitar os usuários para o unified messaging. É possível criar uma política de caixa de correio usando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="9e98b-p106">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

<span data-ttu-id="9e98b-127">E é possível habilitar um usuário para unified messaging utilizando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="9e98b-127">And you can enable a user for unified messaging by using a command similar to this:</span></span>
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

<span data-ttu-id="9e98b-p107">No comando anterior, o parâmetro Extensions representa o número de extensão telefônica do usuário. Neste exemplo, o usuário possui o número de extensão 100.</span><span class="sxs-lookup"><span data-stu-id="9e98b-p107">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>
  
<span data-ttu-id="9e98b-130">Após habilitar esta caixa de correio, o usuário kenmyer@litwareinc.com poderá usar a unificação de mensagens do Exchange.</span><span class="sxs-lookup"><span data-stu-id="9e98b-130">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="9e98b-131">Você pode verificar se o usuário pode se conectar a UM do Exchange executando o cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) do dentro do Skype do Shell de gerenciamento do servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="9e98b-131">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) cmdlet from within the Skype for Business Server Management Shell:</span></span>
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

<span data-ttu-id="9e98b-132">Se você tiver um segundo usuário que tenha sido habilitado para Unificação de mensagens, você pode usar o cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) para verificar se o segundo usuário pode deixar uma mensagem de caixa postal para o primeiro usuário.</span><span class="sxs-lookup"><span data-stu-id="9e98b-132">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```