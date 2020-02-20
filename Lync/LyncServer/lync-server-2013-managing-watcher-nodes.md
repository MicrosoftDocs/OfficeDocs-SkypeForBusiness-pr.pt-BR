---
title: 'Lync Server 2013: Gerenciando nós do Inspetor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6422754da81aa17d6a746f6539258b3f6ae0d2c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="675de-102">Gerenciando nós do Inspetor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="675de-102">Managing watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="675de-103">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="675de-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="675de-104">Além de modificar as transações sintéticas que são executadas em um nó do Inspetor, os administradores também podem usar o cmdlet **set-CsWatcherNodeConfiguration** para executar duas outras tarefas importantes: habilitar e desabilitar o nó do Inspetor e configurar o nó do inspetor para usar URLs internas ou externas ao executar seus testes.</span><span class="sxs-lookup"><span data-stu-id="675de-104">In addition to modifying the synthetic transactions that are executed on a watcher node, administrators can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal URLs or external URLs when running its tests.</span></span>

<span data-ttu-id="675de-105">Por padrão, os nós do Inspetor foram projetados para executar periodicamente todas as suas transações sintéticas habilitadas.</span><span class="sxs-lookup"><span data-stu-id="675de-105">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="675de-106">Às vezes, no entanto, talvez seja necessário suspender essas transações.</span><span class="sxs-lookup"><span data-stu-id="675de-106">Sometimes, however, you may need to suspend those transactions.</span></span> <span data-ttu-id="675de-107">Por exemplo, se o nó do Inspetor estiver desconectado temporariamente da rede, não haverá motivo para executar as transações sintéticas.</span><span class="sxs-lookup"><span data-stu-id="675de-107">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="675de-108">Sem conectividade de rede, essas transações são garantidas de falhar.</span><span class="sxs-lookup"><span data-stu-id="675de-108">Without network connectivity, those transactions are guaranteed to fail.</span></span> <span data-ttu-id="675de-109">Se você quiser desabilitar temporariamente um nó do Inspetor, execute um comando semelhante a este no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="675de-109">If you want to temporarily disable a watcher node, run a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

<span data-ttu-id="675de-110">Este comando desabilitará a execução de transações sintéticas no nó do Inspetor ATL-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="675de-110">This command will disable the execution of synthetic transactions on the watcher node atl-watcher- 001.litwareinc.com.</span></span> <span data-ttu-id="675de-111">Para retomar a execução das transações sintéticas, defina a propriedade Enabled de volta como true ($True):</span><span class="sxs-lookup"><span data-stu-id="675de-111">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> <span data-ttu-id="675de-112">A propriedade Enabled pode ser usada para ativar ou desativar os nós do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="675de-112">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="675de-113">Se você quiser excluir permanentemente um nó do Inspetor, use o cmdlet <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> :</span><span class="sxs-lookup"><span data-stu-id="675de-113">If you want to permanently delete a watcher node, use the <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet:</span></span><BR><span data-ttu-id="675de-114">Remove-CsWatcherNodeConfiguration – Identity "atl-watcher-001.litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="675de-114">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span></span><BR><span data-ttu-id="675de-115">Esse comando Remove todas as definições de configuração do nó do observador do computador especificado, o que impede que o computador execute transações sintéticas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="675de-115">That command removes all the watcher node configuration settings from the specified computer, which prevents the computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="675de-116">No entanto, o comando não desinstala os arquivos do agente do System Center ou os arquivos de sistema do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="675de-116">However, the command does not uninstall the System Center agent files or the Lync Server 2013 system files.</span></span>



</div>

<span data-ttu-id="675de-117">Por padrão, os nós do Inspetor usam as URLs externas de uma organização ao conduzir seus testes.</span><span class="sxs-lookup"><span data-stu-id="675de-117">By default, watcher nodes use an organization's external URLs when conducting their tests.</span></span> <span data-ttu-id="675de-118">No entanto, os nós do Inspetor também podem ser configurados para usar as URLs internas da organização.</span><span class="sxs-lookup"><span data-stu-id="675de-118">However, watcher nodes can also be configured to use the organization's internal URLs.</span></span> <span data-ttu-id="675de-119">Isso permite que os administradores verifiquem o acesso à URL para usuários localizados dentro da rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="675de-119">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="675de-120">Para configurar um nó do inspetor para usar URLs internas em vez de URLs externas, defina a propriedade UseInternalWebUrls como true ($True):</span><span class="sxs-lookup"><span data-stu-id="675de-120">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebUrls property to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

<span data-ttu-id="675de-121">Se você redefinir essa propriedade para o valor padrão false ($False), o Inspetor usará as URLs externas:</span><span class="sxs-lookup"><span data-stu-id="675de-121">If you reset this property to the default value of False ($False), the watcher will then use the external URLs:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

