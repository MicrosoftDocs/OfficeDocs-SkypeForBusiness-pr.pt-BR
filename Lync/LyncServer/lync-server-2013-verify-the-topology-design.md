---
title: 'Lync Server 2013: Verificar o design de topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85266477df342c16ed69c0507813b905c608745c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="5ab7d-102">Verificar o design de topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ab7d-102">Verify the topology design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ab7d-103">_**Tópico da última modificação:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="5ab7d-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="5ab7d-104">O construtor de topologias verifica automaticamente a topologia.</span><span class="sxs-lookup"><span data-stu-id="5ab7d-104">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="5ab7d-105">Qualquer erro de topologia é identificado como um erro de validação, indicado pelo ícone de erro de validação ao lado da função do servidor.</span><span class="sxs-lookup"><span data-stu-id="5ab7d-105">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="5ab7d-106">Também é importante verificar se a topologia representa corretamente a topologia para a implantação.</span><span class="sxs-lookup"><span data-stu-id="5ab7d-106">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="5ab7d-107">Para verificar a topologia antes da publicação</span><span class="sxs-lookup"><span data-stu-id="5ab7d-107">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="5ab7d-108">Verifique se todas as URLs simples estão configuradas corretamente.</span><span class="sxs-lookup"><span data-stu-id="5ab7d-108">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="5ab7d-109">Verifique se o servidor baseado em SQL Server está online e disponível para o computador no qual o Construtor de Topologias está instalado, incluindo quaisquer regras de firewall necessárias.</span><span class="sxs-lookup"><span data-stu-id="5ab7d-109">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="5ab7d-110">Confirme se o compartilhamento de arquivos está disponível e se tem as permissões adequadas definidas.</span><span class="sxs-lookup"><span data-stu-id="5ab7d-110">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="5ab7d-111">Verifique se as funções de servidor corretas que atendem aos requisitos de implantação estão definidas na topologia.</span><span class="sxs-lookup"><span data-stu-id="5ab7d-111">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="5ab7d-112">Verifique se os servidores existem nos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5ab7d-112">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="5ab7d-113">Isso ocorrerá automaticamente se você tiver ingressado nos servidores do domínio.</span><span class="sxs-lookup"><span data-stu-id="5ab7d-113">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="5ab7d-114">Após a verificação da topologia, se não houver erros de validação, você estará pronto para publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="5ab7d-114">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="5ab7d-115">Se houver erros de validação, você deve corrigi-los para poder publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="5ab7d-115">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="5ab7d-116">Para obter detalhes sobre como publicar sua topologia, consulte [publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="5ab7d-116">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

