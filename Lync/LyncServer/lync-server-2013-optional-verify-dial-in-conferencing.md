---
title: 'Lync Server 2013: (opcional) verificar conferência discada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48183941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebfebd5dceff50d7d4b7647c7709bb88b7c1fa8e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530768"
---
# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="02e6b-102">Opcion Verificar a conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02e6b-102">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02e6b-103">_**Última modificação do tópico:** 2011-01-21_</span><span class="sxs-lookup"><span data-stu-id="02e6b-103">_**Topic Last Modified:** 2011-01-21_</span></span>

<span data-ttu-id="02e6b-104">Para verificar se a página da Web de Configurações de Conferência Discada e os números de acesso discado funcionam corretamente, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="02e6b-104">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>

  - <span data-ttu-id="02e6b-105">Entre na URL simples para testar a página da Web Configurações de Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="02e6b-105">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>

  - <span data-ttu-id="02e6b-p101">Teste se os números de acesso funcionam corretamente para um pool específico executando o script posteriormente neste tópico. Esse script simula chamadas para números de acesso. Você precisa do endereço SIP e das credenciais de um cliente de UC (comunicações unificadas) que esteja hospedado no pool específico para usar esse script.</span><span class="sxs-lookup"><span data-stu-id="02e6b-p101">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>

<span data-ttu-id="02e6b-109">Esta etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="02e6b-109">This step is optional.</span></span>

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="02e6b-110">Para testar os números de acesso de um pool específico</span><span class="sxs-lookup"><span data-stu-id="02e6b-110">To test access numbers for a specific pool</span></span>

1.  <span data-ttu-id="02e6b-111">Efetue logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **Cs-ServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="02e6b-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="02e6b-112">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="02e6b-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="02e6b-113">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="02e6b-113">Run the following at the command prompt:</span></span>
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    <span data-ttu-id="02e6b-p102">O relatório resultante mostra êxito ou falha, juntamente com informações de diagnóstico específicas. O sinalizador –Verbose fornece informações mais detalhadas sobre quantos números de acesso foram encontrados e detalhes sobre eles.</span><span class="sxs-lookup"><span data-stu-id="02e6b-p102">The resulting report shows either Success or Failure, along with specific diagnostic information. The –Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

