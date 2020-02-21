---
title: 'Lync Server 2013: criar objetos de contato para UM do Exchange hospedado'
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
ms.openlocfilehash: c783a79c6d3ed3cd0af47d53d136a47585cb94d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="8946b-102">Criar objetos de contato para a UM do Exchange hospedado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8946b-102">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8946b-103">_**Última modificação do tópico:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="8946b-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="8946b-104">O procedimento a seguir explica como criar objetos de contato no AA (Atendedor Automático) ou no SA (Acesso do Assinante) para o serviço de UM (Unificação de Mensagens) do Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="8946b-104">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="8946b-105">Para obter detalhes, consulte [Hosted Exchange Contact Object Management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="8946b-105">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="8946b-106">Para obter detalhes sobre como configurar objetos de contato, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="8946b-106">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="8946b-107">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="8946b-107">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="8946b-108">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="8946b-108">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="8946b-109">Para que os objetos de contato do Lync Server 2013 possam ser habilitados para UM do Exchange hospedado, uma política de correio de voz hospedada que se aplica a eles deve ser implantada.</span><span class="sxs-lookup"><span data-stu-id="8946b-109">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="8946b-110">Para obter detalhes, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail Policies in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8946b-110">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="8946b-111">Para criar objetos de contato no AA ou SA para a UM do Exchange hospedado</span><span class="sxs-lookup"><span data-stu-id="8946b-111">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="8946b-112">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8946b-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8946b-p102">Execute o cmdlet New-CsExUmContact para criar objetos de contato obrigatórios para a sua implantação. Por exemplo, para criar um objeto de contato no AA e um no SA, execute:</span><span class="sxs-lookup"><span data-stu-id="8946b-p102">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment. For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="8946b-115">Estes exemplos definem os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="8946b-115">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="8946b-116">**SipAddress** especifica o endereço SIP do objeto de contato.</span><span class="sxs-lookup"><span data-stu-id="8946b-116">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="8946b-117">Este deve ser um endereço que ainda não tenha sido usado para configurar um objeto de contato ou de usuário nos Serviços de Domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8946b-117">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="8946b-118">Esse valor deve estar no formato "SIP:\<*endereço*\>SIP", conforme mostrado nos exemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="8946b-118">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="8946b-119">**RegistrarPool** especifica o nome de domínio totalmente qualificado (FQDN) do pool em que o serviço do Registrador Avançado está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="8946b-119">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="8946b-120">Os objetos de contato de UM do Exchange não podem ser movidos para pools que fazem parte de implantações do Lync Server 2013 antes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8946b-120">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="8946b-121">**OU** especifica a unidade organizacional do Active Directory em que este objeto de contato estará localizado.</span><span class="sxs-lookup"><span data-stu-id="8946b-121">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="8946b-p104">**DisplayNumber** especifica o número de telefone do objeto de contato. O número de telefone para cada objeto de contato deve ser único.</span><span class="sxs-lookup"><span data-stu-id="8946b-p104">**DisplayNumber** specifies the telephone number of the contact object. The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="8946b-p105">**AutoAttendant** especifica se o objeto de Contato é um Atendedor Automático. O Atendedor Automático fornece um conjunto de prompts de voz que permite aos chamadores navegar no sistema telefônico e alcançar a pessoa que desejam contatar. O valor **False** (o padrão) para este parâmetro indica um objeto de contato de Acesso do Assinante.</span><span class="sxs-lookup"><span data-stu-id="8946b-p105">**AutoAttendant** specifies whether the Contact object is an Auto Attendant. Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact. A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

