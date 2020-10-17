---
title: 'Lync Server 2013: Configurando a Unificação de mensagens do Microsoft Exchange Server 2013 para Lync Server 2013 caixa postal'
description: 'Lync Server 2013: Configurando a Unificação de mensagens do Microsoft Exchange Server 2013 para Lync Server 2013 caixa postal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57576981e419f96734e4bd2ed62a7d203f7b683c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570747"
---
# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a><span data-ttu-id="cd5fa-103">Configurando a Unificação de mensagens do Microsoft Exchange Server 2013 para o Microsoft Lync Server 2013 voice mail</span><span class="sxs-lookup"><span data-stu-id="cd5fa-103">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd5fa-104">_**Última modificação do tópico:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="cd5fa-104">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="cd5fa-105">O Microsoft Lync Server 2013 permite que você tenha mensagens de caixa postal armazenadas no Microsoft Exchange Server 2013; essas mensagens de voz serão exibidas como mensagens de email nas caixas de entrada dos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="cd5fa-105">Microsoft Lync Server 2013 enables you to have voicemail messages stored in Microsoft Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> <span data-ttu-id="cd5fa-106">Esse recurso também foi encontrado nas edições 2010 do Lync Server e no Exchange; no entanto, o processo de configuração dessa "Unificação de mensagens" foi simplificado nas edições 2013 graças à introdução do componente roteador de chamadas de UM.</span><span class="sxs-lookup"><span data-stu-id="cd5fa-106">This capability was also found in the 2010 editions of Lync Server and Exchange; however, the process of configuring this "unified messaging" has been simplified in the 2013 editions thanks to the introduction of the UM Call Router component.</span></span> <span data-ttu-id="cd5fa-107">Esse componente é instalado no servidor de acesso para cliente do Exchange 2013, e todas as chamadas para a Unificação de mensagens do Exchange (como uma caixa postal) são roteadas primeiro pelo roteador de chamada e, em seguida, são redirecionadas para o servidor de caixa de correio apropriado.</span><span class="sxs-lookup"><span data-stu-id="cd5fa-107">This component is installed on the Exchange 2013 Client Access server, and all calls to Exchange unified messaging (such as a voicemail) are first routed through the Call Router and then are redirected to the appropriate Mailbox server.</span></span>

<span data-ttu-id="cd5fa-108">Se você já configurou a autenticação de servidor para servidor entre o Lync Server 2013 e o Exchange 2013, você está pronto para configurar a Unificação de mensagens.</span><span class="sxs-lookup"><span data-stu-id="cd5fa-108">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you are ready to setup unified messaging.</span></span> <span data-ttu-id="cd5fa-109">Para fazer isso, você deve primeiro criar e atribuir um novo plano de discagem de Unificação de mensagens no seu servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="cd5fa-109">To do so, you must first create and assign a new unified messaging dial plan on your Exchange server.</span></span> <span data-ttu-id="cd5fa-110">Por exemplo, esses dois comandos (executados de dentro do Shell de gerenciamento do Exchange) configuram um novo plano de discagem de 3 dígitos para o Exchange:</span><span class="sxs-lookup"><span data-stu-id="cd5fa-110">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="cd5fa-p103">O primeiro comando no exemplo, o parâmetro VoIPSecurity e o valor de parâmetro "Secured" indica que o canal de sinalização é criptografado usando TLS. O URIType "SipName" indica que as mensagens serão enviadas e recebidas usando o protocolo SIP e o CountryOrRegionCode de 1 indica que o plano de discagem se aplica aos EUA.</span><span class="sxs-lookup"><span data-stu-id="cd5fa-p103">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS). The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>

<span data-ttu-id="cd5fa-113">No segundo comando, o valor do parâmetro para o parâmetro ConfiguredInCountryOrRegionGroups especifica os grupos no país que podem ser usados com este plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="cd5fa-113">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="cd5fa-114">O valor do parâmetro "Anywhere \* , \* \* ", "define o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cd5fa-114">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>

  - <span data-ttu-id="cd5fa-115">Nome do grupo ("Anywhere")</span><span class="sxs-lookup"><span data-stu-id="cd5fa-115">Group name ("Anywhere")</span></span>

  - <span data-ttu-id="cd5fa-116">AllowedNumberString ( \* , um caractere curinga indicando que qualquer sequência numérica é permitida)</span><span class="sxs-lookup"><span data-stu-id="cd5fa-116">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>

  - <span data-ttu-id="cd5fa-117">DialNumberString ( \* , um caractere curinga indicando que qualquer número discado é permitido)</span><span class="sxs-lookup"><span data-stu-id="cd5fa-117">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>

  - <span data-ttu-id="cd5fa-118">Textcomment ( \* , um caractere curinga indicando que qualquer comando de texto é permitido)</span><span class="sxs-lookup"><span data-stu-id="cd5fa-118">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cd5fa-119">Criar um novo plano de discagem também criará uma política de caixa de correio padrão.</span><span class="sxs-lookup"><span data-stu-id="cd5fa-119">Creating a new dial plan will also create a Default Mailbox Policy.</span></span>



</div>

<span data-ttu-id="cd5fa-120">Após criar e configurar o novo plano de discagem, você deve adicionar o novo plano de discagem ao seu servidor do unified messaging e modificar o modo de inicialização do servidor; em particular, você deve definir o modo de inicialização para "Dual".</span><span class="sxs-lookup"><span data-stu-id="cd5fa-120">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="cd5fa-121">Você pode executar essas duas tarefas de dentro do Shell de gerenciamento do Exchange:</span><span class="sxs-lookup"><span data-stu-id="cd5fa-121">You can perform both of these tasks from within the Exchange Management Shell:</span></span>

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

<span data-ttu-id="cd5fa-122">Após a configuração do servidor de Unificação de mensagens, você deve executar o cmdlet Enable-ExchangeCertificate para garantir que seu certificado do Exchange seja aplicado ao serviço de Unificação de mensagens:</span><span class="sxs-lookup"><span data-stu-id="cd5fa-122">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

<span data-ttu-id="cd5fa-p106">Após o certificado ter sido atribuído corretamente, você deve parar e reiniciar o serviço MsExchangeUM no servidor do unified messaging. Este serviço deve ser parado e reiniciado a qualquer momento que você alterar o modo de inicialização.</span><span class="sxs-lookup"><span data-stu-id="cd5fa-p106">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>

<span data-ttu-id="cd5fa-125">Após finalizar a configuração do servidor do unified messaging, é possível configurar o Roteador de Chamada UM:</span><span class="sxs-lookup"><span data-stu-id="cd5fa-125">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

<span data-ttu-id="cd5fa-126">Como o modo de inicialização foi alterado, você deve parar e reiniciar o serviço do MsExchangeUMCR no computador hospedando o Roteador de Chamada UM.</span><span class="sxs-lookup"><span data-stu-id="cd5fa-126">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>

<span data-ttu-id="cd5fa-p107">Para concluir a configuração do unified messaging, você precisa criar uma política de caixa de correio do UM e usar essa política para habilitar os usuários para o unified messaging. É possível criar uma política de caixa de correio usando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="cd5fa-p107">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="cd5fa-129">E é possível habilitar um usuário para unified messaging utilizando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="cd5fa-129">And you can enable a user for unified messaging by using a command similar to this:</span></span>

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

<span data-ttu-id="cd5fa-p108">No comando anterior, o parâmetro Extensions representa o número de extensão telefônica do usuário. Neste exemplo, o usuário possui o número de extensão 100.</span><span class="sxs-lookup"><span data-stu-id="cd5fa-p108">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>

<span data-ttu-id="cd5fa-132">Após habilitar esta caixa de correio, o usuário kenmyer@litwareinc.com deve poder usar o Exchange unified messaging.</span><span class="sxs-lookup"><span data-stu-id="cd5fa-132">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="cd5fa-133">Você pode verificar se o usuário pode se conectar ao UM do Exchange executando o cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) a partir do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="cd5fa-133">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) cmdlet from within the Lync Server Management Shell:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="cd5fa-134">Se você possui um segundo usuário habilitado para unified messaging, é possível usar o cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) para verificar se este segundo usuário pode deixar uma mensagem de caixa postal para o primeiro usuário.</span><span class="sxs-lookup"><span data-stu-id="cd5fa-134">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

