---
title: 'Lync Server 2013: Verificando sua implantação de mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verifying your mobility deployment
ms:assetid: 72f9b4d3-57b0-4705-9480-cfdca313a70c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690024(v=OCS.15)
ms:contentKeyID: 48184477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b38e87a8266763085c74bf7119cc996f793ca93
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-your-mobility-deployment-in-lync-server-2013"></a><span data-ttu-id="5ad3f-102">Verificando sua implantação de mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ad3f-102">Verifying your mobility deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ad3f-103">_**Tópico da última modificação:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="5ad3f-103">_**Topic Last Modified:** 2013-02-12_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="5ad3f-104">Depois de implantar o serviço de mobilidade do Lync Server e o serviço de descoberta automática do Lync Server, execute uma transação de teste para verificar se sua implantação funciona corretamente.</span><span class="sxs-lookup"><span data-stu-id="5ad3f-104">After you deploy the Lync Server Mobility Service and Lync Server Autodiscover Service, run a test transaction to verify that your deployment works correctly.</span></span> <span data-ttu-id="5ad3f-105">Você pode executar **Test-CsUcwaConference** para testar a capacidade de dois usuários que estão usando clientes móveis do Lync 2013 para criar, ingressar e se comunicar em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="5ad3f-105">You can run **Test-CsUcwaConference** to test the ability of two users who are using Lync 2013 Mobile clients to create, join and communicate in a conference.</span></span> <span data-ttu-id="5ad3f-106">Para usar essa transação de teste, você precisa de dois usuários reais ou usuários de teste e suas credenciais completas.</span><span class="sxs-lookup"><span data-stu-id="5ad3f-106">To use this test transaction, you need two actual users or test users, and their full credentials.</span></span>

<span data-ttu-id="5ad3f-107">Use **Test-CsMcxP2PIM** para testar o envio de uma mensagem instantânea entre dois usuários que estão usando o Lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="5ad3f-107">You use **Test-CsMcxP2PIM** to test sending an instant message between two users who are using Lync 2010 Mobile.</span></span> <span data-ttu-id="5ad3f-108">Semelhante a **Test-CsUcwaConference**, você usa dois usuários reais ou dois usuários de teste predefinidos.</span><span class="sxs-lookup"><span data-stu-id="5ad3f-108">Similar to **Test-CsUcwaConference**, you use two actual users or two predefined test users.</span></span>

<div>

## <a name="to-test-conferencing-for-lync-2013-mobile-clients"></a><span data-ttu-id="5ad3f-109">Para testar a conferência para clientes móveis do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="5ad3f-109">To test conferencing for Lync 2013 Mobile clients</span></span>

1.  <span data-ttu-id="5ad3f-110">Faça logon como membro da função CsAdministrator em qualquer computador onde o Shell de Gerenciamento do Lync Server e o Ocscore estiverem instalados.</span><span class="sxs-lookup"><span data-stu-id="5ad3f-110">Log on as a member of the CsAdministrator role on any computer where Lync Server Management Shell and Ocscore are installed.</span></span>

2.  <span data-ttu-id="5ad3f-111">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5ad3f-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5ad3f-112">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="5ad3f-112">At the command line, type:</span></span>
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    <span data-ttu-id="5ad3f-113">Você pode definir credenciais em um script e passá-las para o cmdlet de teste.</span><span class="sxs-lookup"><span data-stu-id="5ad3f-113">You can set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="5ad3f-114">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5ad3f-114">For example:</span></span>
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

</div>

<div>

## <a name="to-test-person-to-person-instant-messaging-im-for-lync-2010-mobile"></a><span data-ttu-id="5ad3f-115">Para testar o sistema de mensagens instantâneas de pessoa para pessoa (IM) para o Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="5ad3f-115">To test person-to-person instant messaging (IM) for Lync 2010 Mobile</span></span>

1.  <span data-ttu-id="5ad3f-116">Faça logon como membro da função CsAdministrator em qualquer computador onde o Shell de Gerenciamento do Lync Server e o Ocscore estiverem instalados.</span><span class="sxs-lookup"><span data-stu-id="5ad3f-116">Log on as a member of the CsAdministrator role on any computer where Lync Server Management Shell and Ocscore are installed.</span></span>

2.  <span data-ttu-id="5ad3f-117">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5ad3f-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5ad3f-118">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="5ad3f-118">At the command line, type:</span></span>
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    <span data-ttu-id="5ad3f-119">Você pode definir credenciais em um script e passá-las para o cmdlet de teste.</span><span class="sxs-lookup"><span data-stu-id="5ad3f-119">You can set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="5ad3f-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5ad3f-120">For example:</span></span>
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5ad3f-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="5ad3f-121">See Also</span></span>


[<span data-ttu-id="5ad3f-122">Test-CsMcxP2PIM</span><span class="sxs-lookup"><span data-stu-id="5ad3f-122">Test-CsMcxP2PIM</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM)  
[<span data-ttu-id="5ad3f-123">Test-CsUcwaConference</span><span class="sxs-lookup"><span data-stu-id="5ad3f-123">Test-CsUcwaConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

