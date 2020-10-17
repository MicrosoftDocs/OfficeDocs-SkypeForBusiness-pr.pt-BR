---
title: 'Lync Server 2013: verificar o design da topologia'
description: 'Lync Server 2013: Verifique o design de topologia.'
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
ms.openlocfilehash: cb1e65343aacddbc11d3b909dfdff715503cab93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560187"
---
# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="02c23-103">Verificar o design de topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02c23-103">Verify the topology design in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02c23-104">_**Última modificação do tópico:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="02c23-104">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="02c23-105">O construtor de topologia verifica automaticamente a topologia.</span><span class="sxs-lookup"><span data-stu-id="02c23-105">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="02c23-106">Qualquer erro na topologia é identificado como um erro de validação, indicado pelo ícone de erro de validação ao lado da função de servidor.</span><span class="sxs-lookup"><span data-stu-id="02c23-106">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="02c23-107">É importante também verificar se a topologia representa de forma correta a topologia da sua implantação.</span><span class="sxs-lookup"><span data-stu-id="02c23-107">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="02c23-108">Para verificar a topologia antes de publicação</span><span class="sxs-lookup"><span data-stu-id="02c23-108">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="02c23-109">Verifique se todas as URLs simples estão configuradas corretamente.</span><span class="sxs-lookup"><span data-stu-id="02c23-109">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="02c23-110">Confirme se o servidor baseado em SQL Server está online e disponível para o computador onde o construtor de topologias está instalado, incluindo as regras de firewall necessárias.</span><span class="sxs-lookup"><span data-stu-id="02c23-110">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="02c23-111">Confirme se o compartilhamento de arquivos está disponível e tem as permissões adequadas definidas.</span><span class="sxs-lookup"><span data-stu-id="02c23-111">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="02c23-112">Confirme se as funções de servidor corretas que atendem aos requisitos de implantação estão definidas na topologia.</span><span class="sxs-lookup"><span data-stu-id="02c23-112">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="02c23-113">Verifique se os servidores existem nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="02c23-113">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="02c23-114">Isso acontecerá automaticamente se você tiver ingressado os servidores no domínio.</span><span class="sxs-lookup"><span data-stu-id="02c23-114">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="02c23-115">Após a verificação da topologia e se não houver erros de validação, você deverá estar pronto para publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="02c23-115">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="02c23-116">Se houver erros de validação, será necessário corrigi-los antes de publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="02c23-116">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="02c23-117">Para obter detalhes sobre como publicar sua topologia, consulte [publish the Topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="02c23-117">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

