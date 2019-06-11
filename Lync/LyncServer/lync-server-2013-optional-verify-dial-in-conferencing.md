---
title: 'Lync Server 2013: (Opcional) Verificar conferência discada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Verify dial-in conferencing
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48183941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70a0b18ce596e4799c82a2843b5f3a008b5cb285
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="fdbae-102">(Opcional) Verificar conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdbae-102">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdbae-103">_**Tópico da última modificação:** 2011-01-21_</span><span class="sxs-lookup"><span data-stu-id="fdbae-103">_**Topic Last Modified:** 2011-01-21_</span></span>

<span data-ttu-id="fdbae-104">Para verificar se a página da Web de Configurações de Conferência Discada e os números de acesso discado funcionam corretamente, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fdbae-104">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>

  - <span data-ttu-id="fdbae-105">Entre na URL simples para testar a página da Web Configurações de Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="fdbae-105">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>

  - <span data-ttu-id="fdbae-p101">Teste se os números de acesso funcionam corretamente para um pool específico executando o script posteriormente neste tópico. Esse script simula chamadas para números de acesso. Você precisa do endereço SIP e das credenciais de um cliente de UC (comunicações unificadas) que esteja hospedado no pool específico para usar esse script.</span><span class="sxs-lookup"><span data-stu-id="fdbae-p101">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>

<span data-ttu-id="fdbae-109">Esta etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="fdbae-109">This step is optional.</span></span>

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="fdbae-110">Para testar os números de acesso de um pool específico</span><span class="sxs-lookup"><span data-stu-id="fdbae-110">To test access numbers for a specific pool</span></span>

1.  <span data-ttu-id="fdbae-111">Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **cs-ServerAdministrator** ou **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="fdbae-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="fdbae-112">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="fdbae-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="fdbae-113">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="fdbae-113">Run the following at the command prompt:</span></span>
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    <span data-ttu-id="fdbae-p102">O relatório resultante mostra êxito ou falha, juntamente com informações de diagnóstico específicas. O sinalizador -Verbose fornece informações mais detalhadas sobre quantos números de acesso foram encontrados e detalhes sobre eles.</span><span class="sxs-lookup"><span data-stu-id="fdbae-p102">The resulting report shows either Success or Failure, along with specific diagnostic information. The –Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

