---
title: 'Lync Server 2013: testando o Exchange para notificações do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Exchange to Lync notifications
ms:assetid: ed2d6325-3cf5-4450-9951-03092bcb0a7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727315(v=OCS.15)
ms:contentKeyID: 63969665
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fba2f5ad22cb4a741192d5e4d51020b8c04cc39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a><span data-ttu-id="18b9b-102">Testando o Exchange para notificações do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18b9b-102">Testing Exchange to Lync notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18b9b-103">_**Tópico da última modificação:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="18b9b-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18b9b-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="18b9b-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="18b9b-105">Diário</span><span class="sxs-lookup"><span data-stu-id="18b9b-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18b9b-106">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="18b9b-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="18b9b-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="18b9b-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18b9b-108">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="18b9b-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="18b9b-109">Quando executado localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="18b9b-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="18b9b-110">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet <strong>Test-CsExStorageNotification</strong> .</span><span class="sxs-lookup"><span data-stu-id="18b9b-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExStorageNotification</strong> cmdlet.</span></span> <span data-ttu-id="18b9b-111">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="18b9b-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="18b9b-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="18b9b-112">Description</span></span>

<span data-ttu-id="18b9b-113">O cmdlet **Test-CsExStorageNotification** é usado para verificar se o serviço de notificação do Microsoft Exchange Server 2013 pode notificar o Lync Server 2013 todas as atualizações de horário são feitas na lista de contatos de um usuário.</span><span class="sxs-lookup"><span data-stu-id="18b9b-113">The **Test-CsExStorageNotification** cmdlet is used to verify that the Microsoft Exchange Server 2013 notification service can notify Lync Server 2013 any time updates are made to a user's Contact List.</span></span> <span data-ttu-id="18b9b-114">Este cmdlet é válido apenas se você estiver usando o repositório de contatos unificado.</span><span class="sxs-lookup"><span data-stu-id="18b9b-114">This cmdlet is valid only if you are using the unified contact store.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="18b9b-115">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="18b9b-115">Running the test</span></span>

<span data-ttu-id="18b9b-116">O comando mostrado no exemplo 1 testa para ver se o serviço de armazenamento do Lync Server pode se conectar ao serviço de notificação de caixa de correio do Microsoft Exchange Server para o usuário do sip:kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="18b9b-116">The command shown in Example 1 tests to see whether the Lync Server Storage Service can connect to the Microsoft Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com.</span></span> <span data-ttu-id="18b9b-117">Neste exemplo, NetNamedPipe é usado como associação do WCF.</span><span class="sxs-lookup"><span data-stu-id="18b9b-117">In this example, NetNamedPipe is used as the WCF binding.</span></span>

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="18b9b-118">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="18b9b-118">Determining success or failure</span></span>

<span data-ttu-id="18b9b-119">Se a integração com o Exchange estiver configurada corretamente, você receberá uma saída semelhante a essa, com a propriedade Result marcada como **Success**:</span><span class="sxs-lookup"><span data-stu-id="18b9b-119">If Exchange integration is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="18b9b-120">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="18b9b-120">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="18b9b-121">Resultado: êxito</span><span class="sxs-lookup"><span data-stu-id="18b9b-121">Result : Success</span></span>

<span data-ttu-id="18b9b-122">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="18b9b-122">Latency : 00:00:00</span></span>

<span data-ttu-id="18b9b-123">Mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="18b9b-123">Error Message :</span></span>

<span data-ttu-id="18b9b-124">Correto</span><span class="sxs-lookup"><span data-stu-id="18b9b-124">Diagnosis :</span></span>

<span data-ttu-id="18b9b-125">Se o usuário especificado não puder receber notificações, o resultado será mostrado como uma falha, e informações adicionais serão gravadas nas propriedades de erro e diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="18b9b-125">If the specified user can't receive notifications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="18b9b-126">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="18b9b-126">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="18b9b-127">Resultado: falha</span><span class="sxs-lookup"><span data-stu-id="18b9b-127">Result : Failure</span></span>

<span data-ttu-id="18b9b-128">Latência: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="18b9b-128">Latency : 00:00:00</span></span>

<span data-ttu-id="18b9b-129">Mensagem de erro: 10060, falha na tentativa de conexão porque a parte conectada</span><span class="sxs-lookup"><span data-stu-id="18b9b-129">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="18b9b-130">Não respondeu corretamente após um período de tempo ou</span><span class="sxs-lookup"><span data-stu-id="18b9b-130">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="18b9b-131">a conexão estabelecida falhou porque o host conectado tem</span><span class="sxs-lookup"><span data-stu-id="18b9b-131">established connection failed because connected host has</span></span>

<span data-ttu-id="18b9b-132">Falha ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="18b9b-132">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="18b9b-133">Exceção interna: falha na tentativa de conexão porque o</span><span class="sxs-lookup"><span data-stu-id="18b9b-133">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="18b9b-134">a parte conectada não respondeu corretamente após um período de</span><span class="sxs-lookup"><span data-stu-id="18b9b-134">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="18b9b-135">falha na hora ou estabelecida a conexão porque o host conectado</span><span class="sxs-lookup"><span data-stu-id="18b9b-135">time, or established connection failed because connected host</span></span>

<span data-ttu-id="18b9b-136">falhou ao responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="18b9b-136">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="18b9b-137">Correto</span><span class="sxs-lookup"><span data-stu-id="18b9b-137">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="18b9b-138">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="18b9b-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="18b9b-139">Aqui estão alguns motivos comuns pelos quais **Test-CsExStorageNotification** pode falhar:</span><span class="sxs-lookup"><span data-stu-id="18b9b-139">Here are some common reasons why **Test-CsExStorageNotification** might fail:</span></span>

  - <span data-ttu-id="18b9b-140">Um valor de parâmetro incorreto foi fornecido.</span><span class="sxs-lookup"><span data-stu-id="18b9b-140">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="18b9b-141">Se usado, os parâmetros opcionais devem ser configurados corretamente ou o teste falhará.</span><span class="sxs-lookup"><span data-stu-id="18b9b-141">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="18b9b-142">Execute o comando novamente sem os parâmetros opcionais e veja se isso é bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="18b9b-142">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="18b9b-143">Esse comando falhará se o Microsoft Exchange Server estiver configurado incorretamente ou ainda não foi implantado.</span><span class="sxs-lookup"><span data-stu-id="18b9b-143">This command will fail if the Microsoft Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="18b9b-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="18b9b-144">See Also</span></span>


[<span data-ttu-id="18b9b-145">Test-CsExStorageConnectivity</span><span class="sxs-lookup"><span data-stu-id="18b9b-145">Test-CsExStorageConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

