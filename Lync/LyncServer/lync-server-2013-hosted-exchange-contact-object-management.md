---
title: 'Lync Server 2013: gerenciamento de objeto de contato do Exchange hospedado'
description: 'Lync Server 2013: gerenciamento de objeto de contato do Exchange hospedado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 691bcea10d3a4f8b523c6565f384d6c4c9a2a2a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552767"
---
# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a><span data-ttu-id="6be32-103">Gerenciamento de objeto de contato do Exchange hospedado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6be32-103">Hosted Exchange Contact object management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6be32-104">_**Última modificação do tópico:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="6be32-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="6be32-105">Você precisa configurar um objeto de contato para cada número de atendedor automático e número de acesso do assinante em sua implantação entre locais.</span><span class="sxs-lookup"><span data-stu-id="6be32-105">You need to configure a Contact object for each auto-attendant number and subscriber access number in your cross-premises deployment.</span></span>

<span data-ttu-id="6be32-106">Para a integração com a UM do Exchange hospedado, ocsumutil.exe não pode ser usado para gerenciar objetos de contato, pois ele depende das configurações do UM do Exchange Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6be32-106">For integration with hosted Exchange UM, ocsumutil.exe cannot be used to manage Contact objects, because it depends on Active Directory Exchange UM settings.</span></span> <span data-ttu-id="6be32-107">Em uma implantação entre instalações, o Lync Server 2013 e o Exchange hospedado da UM estão instalados em florestas separadas sem nenhuma confiança entre elas.</span><span class="sxs-lookup"><span data-stu-id="6be32-107">In a cross-premises deployment, Lync Server 2013 and hosted Exchange UM are installed in separate forests with no trust between them.</span></span> <span data-ttu-id="6be32-108">Por motivos de segurança, os administradores do Lync Server 2013 não têm acesso direto às configurações do Active Directory da UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6be32-108">For security reasons, Lync Server 2013 administrators have no direct access to Exchange UM Active Directory settings.</span></span> <span data-ttu-id="6be32-109">Como resultado, o Lync Server 2013 fornece um modelo diferente para o gerenciamento de objetos de contato em um *espaço de endereçamento SIP compartilhado* que é acessível para o Lync Server 2013 e para o serviço um do Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="6be32-109">As a result, Lync Server 2013 provides a different model for managing Contact objects in a *shared SIP address space* that is accessible to both Lync Server 2013 and the hosted Exchange UM service.</span></span>

<div>

## <a name="hosted-contact-object-workflow"></a><span data-ttu-id="6be32-110">Fluxo de trabalho do objeto de contato hospedado</span><span class="sxs-lookup"><span data-stu-id="6be32-110">Hosted Contact Object Workflow</span></span>

<span data-ttu-id="6be32-111">Veja a seguir as etapas gerais para trabalhar com seu administrador de locatários do Exchange hospedado para gerenciar objetos de contato:</span><span class="sxs-lookup"><span data-stu-id="6be32-111">The following are the general steps for working with your hosted Exchange tenant administrator to manage contact objects:</span></span>

1.  <span data-ttu-id="6be32-112">O administrador do Exchange solicita números de telefone para o acesso do assinante do UM do Exchange e objetos de contato de atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="6be32-112">The Exchange administrator requests phone numbers for the Exchange UM subscriber access and auto-attendant Contact objects.</span></span>

2.  <span data-ttu-id="6be32-113">O administrador do Lync Server 2013 cria um objeto de contato para cada número de telefone e atribui uma política de caixa postal hospedada a cada objeto de contato.</span><span class="sxs-lookup"><span data-stu-id="6be32-113">The Lync Server 2013 administrator creates a Contact object for each phone number and assigns a hosted voice mail policy to each Contact object.</span></span>

3.  <span data-ttu-id="6be32-114">O administrador do Lync Server 2013 fornece os números de telefone para o administrador do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6be32-114">The Lync Server 2013 administrator provides the phone numbers to the Exchange administrator.</span></span>

4.  <span data-ttu-id="6be32-115">O administrador do Exchange atribui os números de telefone aos planos de discagem da UM do Exchange apropriados para atendedores automáticos e acesso ao Assinante.</span><span class="sxs-lookup"><span data-stu-id="6be32-115">The Exchange administrator assigns the phone numbers to appropriate Exchange UM dial plans for auto attendants and subscriber access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6be32-116">Não é necessário definir as configurações de plano de discagem do Lync Server 2013 nos objetos de contato como ocorre com implantações locais.</span><span class="sxs-lookup"><span data-stu-id="6be32-116">There is no need to configure any Lync Server 2013 dial plan settings on the Contact objects as there is with on-premises deployments.</span></span>



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a><span data-ttu-id="6be32-117">Configurando objetos de contato hospedados</span><span class="sxs-lookup"><span data-stu-id="6be32-117">Configuring Hosted Contact Objects</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6be32-118">Para que os objetos de contato do Lync Server 2013 possam ser habilitados para UM do Exchange hospedado, uma política de correio de voz hospedada que se aplica a eles deve ser implantada.</span><span class="sxs-lookup"><span data-stu-id="6be32-118">Before Lync Server 2013 Contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="6be32-119">A política pode ser do escopo global, no nível do site ou por usuário, desde que se aplique ao objeto de contato que você deseja habilitar.</span><span class="sxs-lookup"><span data-stu-id="6be32-119">The policy can be of global, site-level, or per-user scope, as long as it applies to the contact object you want to enable.</span></span> <span data-ttu-id="6be32-120">Para obter detalhes, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail Policies in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6be32-120">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="6be32-121">Para configurar objetos de contato hospedados de atendedor automático e de acesso ao assinante em uma implantação entre locais, você deve usar os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6be32-121">To configure hosted auto-attendant and subscriber access Contact objects in a cross-premises deployment, you must use the following cmdlets:</span></span>

  - <span data-ttu-id="6be32-122">**New-CsExUmContact** cria um novo objeto de contato para um hospedado.</span><span class="sxs-lookup"><span data-stu-id="6be32-122">**New-CsExUmContact** creates a new Contact object for hosted UM.</span></span>

  - <span data-ttu-id="6be32-123">**Set-CsExUmContact** modifica um objeto de contato existente para um do Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="6be32-123">**Set-CsExUmContact** modifies an existing Contact object for hosted Exchange UM.</span></span>

<span data-ttu-id="6be32-124">O exemplo a seguir cria um objeto de contato de atendedor automático:</span><span class="sxs-lookup"><span data-stu-id="6be32-124">The following example creates an auto-attendant Contact object:</span></span>

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

<span data-ttu-id="6be32-125">Este exemplo cria um novo objeto de contato do UM do Exchange com o endereço SIP sip:exumaa1@fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="6be32-125">This example creates a new Exchange UM Contact object with the SIP address sip:exumaa1@fabrikam.com.</span></span> <span data-ttu-id="6be32-126">O nome do pool onde o serviço registrador do Lync Server 2013 está sendo executado é o RedmondPool.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="6be32-126">The name of the pool where the Lync Server 2013 Registrar service is running is RedmondPool.litwareinc.com.</span></span> <span data-ttu-id="6be32-127">A unidade organizacional do Active Directory onde essas informações serão armazenadas é OU = ExUmContacts, DC = litwareinc, DC = com.</span><span class="sxs-lookup"><span data-stu-id="6be32-127">The Active Directory organizational unit where this information will be stored is OU=ExUmContacts,DC=litwareinc,DC=com.</span></span> <span data-ttu-id="6be32-128">O número de telefone do objeto de contato é 2065554567.</span><span class="sxs-lookup"><span data-stu-id="6be32-128">The phone number of the Contact object is 2065554567.</span></span> <span data-ttu-id="6be32-129">O parâmetro opcional-AutoAttendant $True especifica que esse objeto é um objeto de contato de atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="6be32-129">The optional -AutoAttendant $True parameter specifies that this object is an auto-attendant Contact object.</span></span> <span data-ttu-id="6be32-130">A configuração do parâmetro-AutoAttendant como false (o padrão) especifica um objeto de contato de acesso ao Assinante.</span><span class="sxs-lookup"><span data-stu-id="6be32-130">Setting the -AutoAttendant parameter to False (the default) specifies a subscriber access Contact object.</span></span>

<span data-ttu-id="6be32-131">Para obter detalhes sobre os cmdlets New-CsExUmContact e Set-CsExUmContact, consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6be32-131">For details about the New-CsExUmContact and Set-CsExUmContact cmdlets, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

