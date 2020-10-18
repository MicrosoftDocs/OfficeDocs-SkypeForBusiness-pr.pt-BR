---
title: 'Lync Server 2013: testar serviços do Lync Server'
description: 'Lync Server 2013: testar serviços do Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f04cf5e0c098c671b6fb126d4607f3cdba107712
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575217"
---
# <a name="testing-lync-server-services-in-lync-server-2013"></a><span data-ttu-id="7eecc-103">Testando serviços do Lync Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7eecc-103">Testing Lync Server services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7eecc-104">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="7eecc-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7eecc-105">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="7eecc-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7eecc-106">Diariamente</span><span class="sxs-lookup"><span data-stu-id="7eecc-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eecc-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="7eecc-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7eecc-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7eecc-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eecc-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="7eecc-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7eecc-110">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7eecc-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7eecc-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="7eecc-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsComputer cmdlet.</span></span> <span data-ttu-id="7eecc-112">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7eecc-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7eecc-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="7eecc-113">Description</span></span>

<span data-ttu-id="7eecc-114">Test-CsComputer verifica o status de todos os serviços do Lync Server 2013 que estão em execução no computador local.</span><span class="sxs-lookup"><span data-stu-id="7eecc-114">Test-CsComputer verifies the status of all the Lync Server 2013 services that are running on the local computer.</span></span> <span data-ttu-id="7eecc-115">(Test-CsComputer pode ser executado localmente, ele não pode ser executado a partir de uma instância remota do Windows PowerShell.) O cmdlet também verifica se as portas de firewall apropriadas estão abertas no computador e determina se os grupos do Active Directory que foram criados quando você instalou o Lync Server 2013 foram adicionados aos grupos locais correspondentes.</span><span class="sxs-lookup"><span data-stu-id="7eecc-115">(Test-CsComputer can only be run locally, it cannot be run from a remote instance of Windows PowerShell.) The cmdlet also checks whether the appropriate firewall ports are opened on the computer, and determines whether the Active Directory groups that were created when you installed Lync Server 2013 were added to the corresponding local groups.</span></span> <span data-ttu-id="7eecc-116">Por exemplo, Test-CsComputer verificará se o grupo do Active Directory RTCUniversalUserAdmins foi adicionado ao grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="7eecc-116">For example, Test-CsComputer will verify that the Active Directory group RTCUniversalUserAdmins was added to the Administrators group.</span></span>

<span data-ttu-id="7eecc-117">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .</span><span class="sxs-lookup"><span data-stu-id="7eecc-117">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7eecc-118">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="7eecc-118">Running the test</span></span>

<span data-ttu-id="7eecc-119">O cmdlet Test-CsComputer só pode ser executado no computador local, não é possível chamar Test-CsComputer de uma instância remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7eecc-119">The Test-CsComputer cmdlet can only be run on the local computer, you can't call Test-CsComputer from a remote instance of Windows PowerShell.</span></span> <span data-ttu-id="7eecc-120">Por padrão, Test-CsComputer exibe muito pouca saída na tela, em vez disso, as informações retornadas pelo cmdlet são gravadas em um arquivo HTML.</span><span class="sxs-lookup"><span data-stu-id="7eecc-120">By default, Test-CsComputer displays very little output on-screen, instead information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="7eecc-121">Por isso, recomendamos que você inclua o parâmetro Verbose e o parâmetro Report sempre que executar Test-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="7eecc-121">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsComputer.</span></span> <span data-ttu-id="7eecc-122">O parâmetro Verbose fornecerá uma saída mais detalhada na tela enquanto o cmdlet é executado.</span><span class="sxs-lookup"><span data-stu-id="7eecc-122">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="7eecc-123">O parâmetro Report permite que você especifique um caminho de arquivo e um nome de arquivo para o arquivo HTML gerado por Test-CsComputer.</span><span class="sxs-lookup"><span data-stu-id="7eecc-123">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsComputer.</span></span> <span data-ttu-id="7eecc-124">Se você não incluir o parâmetro Report, o arquivo HTML será automaticamente salvo na pasta usuários e receberá um nome semelhante a este: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span><span class="sxs-lookup"><span data-stu-id="7eecc-124">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="7eecc-125">O seguinte comando de exemplo é executado Test-CsComputer e salva a saída em um arquivo chamado C: \\ Logs \\ComputerTest.html:</span><span class="sxs-lookup"><span data-stu-id="7eecc-125">The following sample command runs Test-CsComputer and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="7eecc-126">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) .</span><span class="sxs-lookup"><span data-stu-id="7eecc-126">For more information, see the Help documentation for the [Test-CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7eecc-127">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="7eecc-127">Determining success or failure</span></span>

<span data-ttu-id="7eecc-128">Por causa do número de verificações de verificação que ele realiza, Test-CsComputer não relata um sim simples **, o teste foi bem-sucedido** ou **não, o teste falhou**.</span><span class="sxs-lookup"><span data-stu-id="7eecc-128">Because of the number of verification checks that it performs, Test-CsComputer does not report back a simple **Yes, the test succeeded** or **No, the test failed**.</span></span> <span data-ttu-id="7eecc-129">Em vez disso, você precisa exibir o arquivo HTML gerado usando o Internet Explorer para determinar o sucesso ou a falha de cada teste.</span><span class="sxs-lookup"><span data-stu-id="7eecc-129">Instead, you have to view the generated HTML file by using Internet Explorer to determine the success or failure of each test.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7eecc-130">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="7eecc-130">Reasons why the test might have failed</span></span>

<span data-ttu-id="7eecc-131">Aqui estão alguns motivos comuns para que Test-CsComputer possa falhar:</span><span class="sxs-lookup"><span data-stu-id="7eecc-131">Here are some common reasons why Test-CsComputer might fail:</span></span>

  - <span data-ttu-id="7eecc-132">O computador de teste pode não estar habilitado para uso com o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7eecc-132">The test computer might not be enabled for use with Lync Server.</span></span> <span data-ttu-id="7eecc-133">Isso pode ocorrer se os serviços do Lync Server ou as funções de servidor no computador tiverem sido alteradas e o cmdlet Enable-CsComputer não foi executado.</span><span class="sxs-lookup"><span data-stu-id="7eecc-133">This can occur if the Lync Server services or server roles on the computer have changed and the Enable-CsComputer cmdlet was not run.</span></span> <span data-ttu-id="7eecc-134">Para resolver esse problema, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7eecc-134">To resolve this issue, run the following command:</span></span>
    
        Enable-CsComputer

  - <span data-ttu-id="7eecc-135">A replicação pode não estar atualizada no computador de teste.</span><span class="sxs-lookup"><span data-stu-id="7eecc-135">Replication might not be up to date on the test computer.</span></span> <span data-ttu-id="7eecc-136">Você pode verificar o status de replicação atual de um computador executando o cmdlet Get-CsManagementStoreReplicationStatus:</span><span class="sxs-lookup"><span data-stu-id="7eecc-136">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="7eecc-137">Se o status de replicação não estiver atualizado, você poderá forçar a replicação a ocorrer manualmente, usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="7eecc-137">If the replication status is not up to date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="7eecc-138">A topologia pode ter que ser ativada.</span><span class="sxs-lookup"><span data-stu-id="7eecc-138">The topology might have to be enabled.</span></span> <span data-ttu-id="7eecc-139">Se você alterar a topologia do Lync Server (alterações que possam afetar o computador local), deverá habilitar a nova topologia.</span><span class="sxs-lookup"><span data-stu-id="7eecc-139">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="7eecc-140">Você pode habilitar a topologia a qualquer momento executando este comando:</span><span class="sxs-lookup"><span data-stu-id="7eecc-140">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

