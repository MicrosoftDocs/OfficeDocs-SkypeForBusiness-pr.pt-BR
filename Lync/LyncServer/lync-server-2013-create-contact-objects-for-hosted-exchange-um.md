---
title: 'Lync Server 2013: criar objetos de contato para UM do Exchange hospedado'
description: 'Lync Server 2013: criar objetos de contato para UM do Exchange hospedado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9760e2a39b5182f9b5194e364e059bddc6a63d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562297"
---
# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="50544-103">Criar objetos de contato para a UM do Exchange hospedado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50544-103">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50544-104">_**Última modificação do tópico:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="50544-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="50544-105">O procedimento a seguir explica como criar objetos de contato no AA (Atendedor Automático) ou no SA (Acesso do Assinante) para o serviço de UM (Unificação de Mensagens) do Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="50544-105">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="50544-106">Para obter detalhes, consulte [Hosted Exchange Contact Object Management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="50544-106">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="50544-107">Para obter detalhes sobre como configurar objetos de contato, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="50544-107">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="50544-108">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="50544-108">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="50544-109">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="50544-109">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="50544-110">Para que os objetos de contato do Lync Server 2013 possam ser habilitados para UM do Exchange hospedado, uma política de correio de voz hospedada que se aplica a eles deve ser implantada.</span><span class="sxs-lookup"><span data-stu-id="50544-110">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="50544-111">Para obter detalhes, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail Policies in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="50544-111">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="50544-112">Para criar objetos de contato no AA ou SA para a UM do Exchange hospedado</span><span class="sxs-lookup"><span data-stu-id="50544-112">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="50544-113">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="50544-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="50544-p102">Execute o cmdlet New-CsExUmContact para criar objetos de contato obrigatórios para a sua implantação. Por exemplo, para criar um objeto de contato no AA e um no SA, execute:</span><span class="sxs-lookup"><span data-stu-id="50544-p102">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment. For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="50544-116">Estes exemplos definem os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="50544-116">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="50544-117">**SipAddress** especifica o endereço SIP do objeto de contato.</span><span class="sxs-lookup"><span data-stu-id="50544-117">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="50544-118">Este deve ser um endereço que ainda não tenha sido usado para configurar um objeto de contato ou de usuário nos Serviços de Domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="50544-118">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="50544-119">Esse valor deve estar no formato "SIP: \<*SIP address*\> " conforme mostrado nos exemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="50544-119">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="50544-120">**RegistrarPool** especifica o nome de domínio totalmente qualificado (FQDN) do pool em que o serviço do Registrador Avançado está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="50544-120">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="50544-121">Os objetos de contato de UM do Exchange não podem ser movidos para pools que fazem parte de implantações do Lync Server 2013 antes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="50544-121">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="50544-122">**OU** especifica a unidade organizacional do Active Directory em que este objeto de contato estará localizado.</span><span class="sxs-lookup"><span data-stu-id="50544-122">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="50544-p104">**DisplayNumber** especifica o número de telefone do objeto de contato. O número de telefone para cada objeto de contato deve ser único.</span><span class="sxs-lookup"><span data-stu-id="50544-p104">**DisplayNumber** specifies the telephone number of the contact object. The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="50544-p105">**AutoAttendant** especifica se o objeto de Contato é um Atendedor Automático. O Atendedor Automático fornece um conjunto de prompts de voz que permite aos chamadores navegar no sistema telefônico e alcançar a pessoa que desejam contatar. O valor **False** (o padrão) para este parâmetro indica um objeto de contato de Acesso do Assinante.</span><span class="sxs-lookup"><span data-stu-id="50544-p105">**AutoAttendant** specifies whether the Contact object is an Auto Attendant. Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact. A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

