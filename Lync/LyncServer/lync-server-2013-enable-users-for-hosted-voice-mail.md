---
title: 'Lync Server 2013: habilitar usuários para caixa postal hospedada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7287f31a4dc0e43b0108ce666e9c65f51f75f2d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a><span data-ttu-id="cd0b0-102">Habilitar usuários para caixa postal hospedada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd0b0-102">Enable users for hosted voice mail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd0b0-103">_**Última modificação do tópico:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="cd0b0-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="cd0b0-104">Siga o procedimento para habilitar os usuários do Lync Server 2013 para caixa postal em um serviço de UM (Unificação de mensagens) do Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="cd0b0-104">Follow the procedure to enable Lync Server 2013 users for voice mail on a hosted Exchange Unified Messaging (UM) service.</span></span>

<span data-ttu-id="cd0b0-105">Para obter detalhes, consulte [Hosted Exchange User Management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="cd0b0-105">For details, see [Hosted Exchange user management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="cd0b0-106">Para obter detalhes sobre o cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) , consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cd0b0-106">For details about the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cd0b0-107">Antes que um usuário do Lync Server 2013 possa ser habilitado para caixa postal hospedada, uma política de caixa postal hospedada que se aplica à sua conta de usuário deve ser implantada.</span><span class="sxs-lookup"><span data-stu-id="cd0b0-107">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to their user account must be deployed.</span></span> <span data-ttu-id="cd0b0-108">Para obter detalhes, consulte <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail Policies in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cd0b0-108">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a><span data-ttu-id="cd0b0-109">Para habilitar usuários para caixa postal hospedada</span><span class="sxs-lookup"><span data-stu-id="cd0b0-109">To enable users for hosted voice mail</span></span>

1.  <span data-ttu-id="cd0b0-110">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cd0b0-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cd0b0-p102">Execute o cmdlet Set-CsUser para configurar a conta de usuário para a caixa postal hospedada. Por exemplo, execute:</span><span class="sxs-lookup"><span data-stu-id="cd0b0-p102">Run the Set-CsUser cmdlet to configure the user account for hosted voice mail. For example, run:</span></span>
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    <span data-ttu-id="cd0b0-113">O exemplo anterior define os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="cd0b0-113">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="cd0b0-114">\*\*HostedVoiceMail \*\* permite que as chamadas de caixa postal do usuário sejam roteadas para o UM do Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="cd0b0-114">**HostedVoiceMail** enables a user’s voice mail calls to be routed to hosted Exchange UM.</span></span> <span data-ttu-id="cd0b0-115">Ele também sinaliza o Microsoft Lync 2013 para acelerar o indicador "Call de caixa postal".</span><span class="sxs-lookup"><span data-stu-id="cd0b0-115">It also signals Microsoft Lync 2013 to light up the “call voice mail” indicator.</span></span>
    
      - <span data-ttu-id="cd0b0-p104">**Identidade** especifica a conta de usuário a ser modificada. O valor de Identidade pode ser especificado usando qualquer um dos seguintes formatos:</span><span class="sxs-lookup"><span data-stu-id="cd0b0-p104">**Identity** specifies the user account to be modified. The Identity value can be specified using any of the following formats:</span></span>
        
          - <span data-ttu-id="cd0b0-118">O endereço SIP do usuário</span><span class="sxs-lookup"><span data-stu-id="cd0b0-118">The user's SIP address</span></span>
        
          - <span data-ttu-id="cd0b0-119">O nome UPN do Active Directory do usuário</span><span class="sxs-lookup"><span data-stu-id="cd0b0-119">The user's Active Directory User-Principal-Name</span></span>
        
          - <span data-ttu-id="cd0b0-120">O nome de logon\\do domínio do usuário (por exemplo\\, contoso kenmyer)</span><span class="sxs-lookup"><span data-stu-id="cd0b0-120">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
        
          - <span data-ttu-id="cd0b0-121">O Nome de exibição de serviços de domínio do Active Directory do usuário (por exemplo, Ken Myer).</span><span class="sxs-lookup"><span data-stu-id="cd0b0-121">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="cd0b0-122">Se estiver usando o nome de exibição como o valor de identidade, você poderá usar o\*caractere curinga asterisco ().</span><span class="sxs-lookup"><span data-stu-id="cd0b0-122">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="cd0b0-123">Por exemplo, a identidade "\* Smith" retorna todos os usuários que têm um nome de exibição que termina com o valor de cadeia de caracteres "Smith".</span><span class="sxs-lookup"><span data-stu-id="cd0b0-123">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cd0b0-124">O Nome de conta SAM do Active Directory do usuário não pode ser usado como o valor de Identidade, pois o Nome de conta SAM não é necessariamente exclusivo na floresta.</span><span class="sxs-lookup"><span data-stu-id="cd0b0-124">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

