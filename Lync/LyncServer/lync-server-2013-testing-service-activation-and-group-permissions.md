---
title: 'Lync Server 2013: testar a ativação do serviço e permissões de grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38bc988ec1fdfeb0c4fd5714f31342902fe45821
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a><span data-ttu-id="6ae89-102">Testando a ativação de serviços e permissões de grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ae89-102">Testing service activation and group permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ae89-103">_**Última modificação do tópico:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="6ae89-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ae89-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="6ae89-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6ae89-105">Diariamente</span><span class="sxs-lookup"><span data-stu-id="6ae89-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ae89-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="6ae89-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6ae89-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ae89-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ae89-108">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="6ae89-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6ae89-109">Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6ae89-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6ae89-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="6ae89-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTopology cmdlet.</span></span> <span data-ttu-id="6ae89-111">Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6ae89-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6ae89-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="6ae89-112">Description</span></span>

<span data-ttu-id="6ae89-113">O cmdlet Test-CsTopology permite verificar se o Lync Server 2013 está funcionando corretamente em um escopo global.</span><span class="sxs-lookup"><span data-stu-id="6ae89-113">The Test-CsTopology cmdlet enables you to verify that Lync Server 2013 is functioning correctly at a global scope.</span></span> <span data-ttu-id="6ae89-114">Por padrão, o cmdlet verifica toda a infraestrutura do Lync Server, verificando se os serviços necessários estão em execução e se as permissões apropriadas estão definidas para esses serviços e para os grupos de segurança universal criados quando você instala o Lync Server .</span><span class="sxs-lookup"><span data-stu-id="6ae89-114">By default, the cmdlet checks your whole Lync Server infrastructure, verifying that the required services are running and that the appropriate permissions are set for these services and for the universal security groups that are created when you install Lync Server.</span></span>

<span data-ttu-id="6ae89-115">Além de verificar a validade da instalação do Lync Server, o Test-CsTopology também permite verificar a validade de um serviço específico.</span><span class="sxs-lookup"><span data-stu-id="6ae89-115">In addition to verifying the validity of the Lync Server installation, Test-CsTopology also lets you check the validity of a specific service.</span></span> <span data-ttu-id="6ae89-116">Por exemplo, este comando verifica o estado do Servidor de Conferência A/V no pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="6ae89-116">For example, this command checks the state of the A/V Conferencing Server on the pool atl-cs-001.litwareinc.com:</span></span>

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6ae89-117">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="6ae89-117">Running the test</span></span>

<span data-ttu-id="6ae89-118">Por padrão, Test-CsTopology exibe uma saída muito pequena na tela.</span><span class="sxs-lookup"><span data-stu-id="6ae89-118">By default, Test-CsTopology displays very little output on-screen.</span></span> <span data-ttu-id="6ae89-119">Em vez disso, as informações retornadas pelo cmdlet são gravadas em um arquivo HTML.</span><span class="sxs-lookup"><span data-stu-id="6ae89-119">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="6ae89-120">O parâmetro Report permite que você especifique um caminho de arquivo e um nome de arquivo para o arquivo HTML gerado por Test-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="6ae89-120">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsTopology.</span></span> <span data-ttu-id="6ae89-121">Se você não incluir o parâmetro Report, o arquivo HTML será automaticamente salvo na pasta usuários e receberá um nome semelhante a este: ce84964a-c4da-4622-ad34-c54ff3ed361f. html.</span><span class="sxs-lookup"><span data-stu-id="6ae89-121">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="6ae89-122">O seguinte comando de exemplo executa Test-CsTopology e salva a saída em um arquivo chamado C:\\logs\\ComputerTest. html:</span><span class="sxs-lookup"><span data-stu-id="6ae89-122">The following sample command runs Test-CsTopology and saves the output to a file that is named C:\\Logs\\ComputerTest.html:</span></span>

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

<span data-ttu-id="6ae89-123">Para obter mais informações, consulte a documentação de ajuda para o cmdlet [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) .</span><span class="sxs-lookup"><span data-stu-id="6ae89-123">For more information, see the Help documentation for the [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6ae89-124">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="6ae89-124">Determining success or failure</span></span>

<span data-ttu-id="6ae89-125">Ao contrário da maioria dos cmdlets de teste, Test-CsTopology relata êxito ou falha.</span><span class="sxs-lookup"><span data-stu-id="6ae89-125">Unlike most of the test cmdlets, Test-CsTopology does report back Success or Failure.</span></span> <span data-ttu-id="6ae89-126">Em parte, isso ocorre devido ao grande número de verificações de verificação que o cmdlet deve fazer sempre que for executado.</span><span class="sxs-lookup"><span data-stu-id="6ae89-126">In part, that’s due to the large number of verification checks that the cmdlet must make every time that it runs.</span></span> <span data-ttu-id="6ae89-127">Em vez disso, os dados são salvos em um relatório HTML que pode ser visualizado usando o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="6ae89-127">Instead, data is saved to an HTML report that can then be viewed by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6ae89-128">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="6ae89-128">Reasons why the test might have failed</span></span>

<span data-ttu-id="6ae89-129">Aqui estão alguns motivos comuns pelos quais Test-CsTopology pode falhar:</span><span class="sxs-lookup"><span data-stu-id="6ae89-129">Here are some common reasons why Test-CsTopology might fail:</span></span>

  - <span data-ttu-id="6ae89-130">A replicação pode não estar atualizada no computador de teste.</span><span class="sxs-lookup"><span data-stu-id="6ae89-130">Replication might not be up-to-date on the test computer.</span></span> <span data-ttu-id="6ae89-131">Você pode verificar o status de replicação atual de um computador executando o cmdlet Get-CsManagementStoreReplicationStatus:</span><span class="sxs-lookup"><span data-stu-id="6ae89-131">You can check the current replication status for a computer by running the Get-CsManagementStoreReplicationStatus cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="6ae89-132">Se o status de replicação não estiver atualizado, você poderá forçar a replicação a ocorrer manualmente usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="6ae89-132">If the replication status is not up-to-date, you can manually force replication to occur by using a command similar to this:</span></span>
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - <span data-ttu-id="6ae89-133">A topologia pode ter que ser ativada.</span><span class="sxs-lookup"><span data-stu-id="6ae89-133">The topology might have to be enabled.</span></span> <span data-ttu-id="6ae89-134">Se você alterar a topologia do Lync Server (alterações que possam afetar o computador local), deverá habilitar a nova topologia.</span><span class="sxs-lookup"><span data-stu-id="6ae89-134">If you change the Lync Server topology (changes that might affect the local computer), then you must enable the new topology.</span></span> <span data-ttu-id="6ae89-135">Você pode habilitar a topologia a qualquer momento executando este comando:</span><span class="sxs-lookup"><span data-stu-id="6ae89-135">You can enable the topology at any time by running this command:</span></span>
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

