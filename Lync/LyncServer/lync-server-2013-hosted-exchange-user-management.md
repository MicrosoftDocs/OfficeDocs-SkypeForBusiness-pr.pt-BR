---
title: 'Lync Server 2013: gerenciamento de usuário do Exchange hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4a54c4a7a3833fdd31999d7613659f9a35f9732
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504198"
---
# <a name="hosted-exchange-user-management-in-lync-server-2013"></a><span data-ttu-id="64501-102">Gerenciamento de usuários do Exchange hospedado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64501-102">Hosted Exchange user management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64501-103">_**Última modificação do tópico:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="64501-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="64501-104">Para fornecer serviços de caixa postal para os usuários do Lync Server 2013 cujas caixas de correio estão localizadas em um serviço do Exchange hospedado, você deve habilitar suas contas de usuário para caixa postal hospedada.</span><span class="sxs-lookup"><span data-stu-id="64501-104">To provide voice mail services for Lync Server 2013 users whose mailboxes are located on a hosted Exchange service, you must enable their user accounts for hosted voice mail.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="64501-105">Antes que um usuário do Lync Server 2013 possa ser habilitado para caixa postal hospedada, uma política de caixa postal hospedada que se aplica à conta de usuário correspondente deve ser implantada.</span><span class="sxs-lookup"><span data-stu-id="64501-105">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to the corresponding user account must be deployed.</span></span> <span data-ttu-id="64501-106">A política pode ser global, site ou por usuário no escopo, contanto que se aplique ao usuário que você deseja habilitar.</span><span class="sxs-lookup"><span data-stu-id="64501-106">The policy can be global, site, or per-user in scope, as long as it applies to the user whom you want to enable.</span></span> <span data-ttu-id="64501-107">Para obter detalhes, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail Policies in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="64501-107">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a><span data-ttu-id="64501-108">O atributo msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="64501-108">The msExchUCVoiceMailSettings Attribute</span></span>

<span data-ttu-id="64501-109">O Lync Server 2013 introduz um novo atributo de usuário chamado **msExchUCVoiceMailSettings**, que é criado como parte da preparação do esquema do Active Directory 2013 do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="64501-109">Lync Server 2013 introduces a new user attribute named **msExchUCVoiceMailSettings**, which is created as part of the Lync Server 2013 Active Directory schema preparation.</span></span> <span data-ttu-id="64501-110">Este atributo com vários valores contém as configurações de caixa postal que são compartilhadas pelo Lync Server 2013 e o serviço do Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="64501-110">This multivalued attribute holds voice mail settings that are shared by Lync Server 2013 and the hosted Exchange service.</span></span>

<span data-ttu-id="64501-111">O serviço do Exchange hospedado pode, em alguns casos, definir o valor do atributo msExchUCVoiceMailSettings no processo de habilitar a UM do Exchange, ou durante o processo de transferência de caixas de correio para um servidor Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="64501-111">The hosted Exchange service may in some cases set the value of the msExchUCVoiceMailSettings attribute in the process of enabling Exchange UM, or during the process of transferring mailboxes to a hosted Exchange Server.</span></span> <span data-ttu-id="64501-112">Se esse atributo não for definido pelo Exchange, o administrador do Lync Server 2013 deverá defini-lo executando o cmdlet Set-CsUser, conforme descrito anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="64501-112">If this attribute is not set by Exchange, the Lync Server 2013 administrator must set it by running the Set-CsUser cmdlet, as described earlier in this topic.</span></span>

<span data-ttu-id="64501-113">Os pares de chave/valor do atributo e seus autores são mostrados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="64501-113">The attribute’s key/value pairs and their authors are shown in the following table.</span></span>

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a><span data-ttu-id="64501-114">Os pares de chave/valor do atributo msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="64501-114">The msExchUCVoiceMailSettings Attribute Key/Value Pairs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64501-115">Valor</span><span class="sxs-lookup"><span data-stu-id="64501-115">Value</span></span></th>
<th><span data-ttu-id="64501-116">Autor</span><span class="sxs-lookup"><span data-stu-id="64501-116">Author</span></span></th>
<th><span data-ttu-id="64501-117">Significado</span><span class="sxs-lookup"><span data-stu-id="64501-117">Meaning</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64501-118">ExchangeHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="64501-118">ExchangeHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="64501-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="64501-119">Exchange</span></span></p></td>
<td><p><span data-ttu-id="64501-120">O usuário foi habilitado para o acesso de UM hospedado pelo Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="64501-120">User has been enabled for hosted UM access by Exchange Server.</span></span> <span data-ttu-id="64501-121">O aplicativo de roteamento de UM do Exchange verificará a política de caixa postal hospedada do usuário para obter detalhes de roteamento.</span><span class="sxs-lookup"><span data-stu-id="64501-121">The Exchange UM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64501-122">ExchangeHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="64501-122">ExchangeHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="64501-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="64501-123">Exchange</span></span></p></td>
<td><p><span data-ttu-id="64501-124">O usuário foi desabilitado para acesso de UM hospedado pelo Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="64501-124">User has been disabled for hosted UM access by Exchange Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64501-125">CsHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="64501-125">CsHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="64501-126">Lync Server</span><span class="sxs-lookup"><span data-stu-id="64501-126">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="64501-127">O usuário foi habilitado para o acesso de UM hospedado pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64501-127">User has been enabled for hosted UM access by Lync Server 2013.</span></span> <span data-ttu-id="64501-128">O aplicativo de roteamento ExUM do Lync Server 2013 fará a verificação da política de caixa postal hospedada do usuário para obter detalhes de roteamento.</span><span class="sxs-lookup"><span data-stu-id="64501-128">The Lync Server 2013 ExUM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64501-129">CsHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="64501-129">CsHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="64501-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="64501-130">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="64501-131">O usuário foi desabilitado para acesso de UM hospedado pelo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64501-131">User has been disabled for hosted UM access by Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="64501-132">Se o atributo já tiver valores diferentes de um dos pares chave/valor do Lync Server 2013 (CSHostedVoiceMail = 0 ou CSHostedVoiceMail = 1), um aviso indicará que o atributo pode ser gerenciado por um aplicativo diferente.</span><span class="sxs-lookup"><span data-stu-id="64501-132">If the attribute already has values other than one of the Lync Server 2013 key/value pairs (CSHostedVoiceMail=0 or CSHostedVoiceMail=1), a warning will indicate that the attribute may be managed by a different application.</span></span> <span data-ttu-id="64501-133">Por exemplo, um aviso será exibido se o par chave/valor ExchangeHostedVoiceMail = 0 ou ExchangeHostedVoiceMail = 1 já estiver presente.</span><span class="sxs-lookup"><span data-stu-id="64501-133">For example, a warning is displayed if the key/value pair ExchangeHostedVoiceMail=0 or ExchangeHostedVoiceMail=1 is already present.</span></span> <span data-ttu-id="64501-134">Nesse caso, você pode alterar o valor editando-o como o Active Directory ou executar o cmdlet a seguir para definir o valor como nulo:</span><span class="sxs-lookup"><span data-stu-id="64501-134">In that case, you can change the value by editing it the Active Directory, or run the following cmdlet to set the value to null:</span></span><BR><span data-ttu-id="64501-135">Set-CsUser – usuário de identidade – HostedVoicemail $null</span><span class="sxs-lookup"><span data-stu-id="64501-135">Set-CsUser –identity user –HostedVoicemail $null</span></span>



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a><span data-ttu-id="64501-136">Habilitando usuários para caixa postal hospedada</span><span class="sxs-lookup"><span data-stu-id="64501-136">Enabling Users for Hosted Voice Mail</span></span>

<span data-ttu-id="64501-137">Para habilitar as chamadas de caixa postal de um usuário para serem encaminhadas para o UM do Exchange hospedado, você deve executar o cmdlet Set-CsUser para definir o valor do parâmetro *HostedVoiceMail* .</span><span class="sxs-lookup"><span data-stu-id="64501-137">To enable a user’s voice mail calls to be routed to hosted Exchange UM, you must run the Set-CsUser cmdlet to set the value of the *HostedVoiceMail* parameter.</span></span> <span data-ttu-id="64501-138">Esse parâmetro também informa ao Lync Server 2013 para acender o indicador "Call de caixa postal".</span><span class="sxs-lookup"><span data-stu-id="64501-138">This parameter also signals Lync Server 2013 to light up the “call voice mail” indicator.</span></span>

  - <span data-ttu-id="64501-139">O exemplo a seguir habilita a conta de usuário de pilar Ackerman para caixa postal hospedada:</span><span class="sxs-lookup"><span data-stu-id="64501-139">The following example enables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    <span data-ttu-id="64501-140">O cmdlet verifica se uma política de caixa postal hospedada (global, no nível do site ou por usuário) se aplica a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="64501-140">The cmdlet verifies that a hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="64501-141">Se nenhuma política for aplicada, o cmdlet falhará.</span><span class="sxs-lookup"><span data-stu-id="64501-141">If no policy applies, the cmdlet fails.</span></span>

  - <span data-ttu-id="64501-142">O exemplo a seguir desabilita a conta de usuário de pilar Ackerman para caixa postal hospedada:</span><span class="sxs-lookup"><span data-stu-id="64501-142">The following example disables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    <span data-ttu-id="64501-143">O cmdlet verifica se nenhuma política de caixa postal hospedada (global, no nível do site ou por usuário) se aplica a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="64501-143">The cmdlet verifies that no hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="64501-144">Se uma política for aplicada, o cmdlet falhará.</span><span class="sxs-lookup"><span data-stu-id="64501-144">If a policy does apply, the cmdlet fails.</span></span>

<span data-ttu-id="64501-145">Para obter detalhes sobre como usar o cmdlet Set-CsUser, consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="64501-145">For details about using the Set-CsUser cmdlet, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

