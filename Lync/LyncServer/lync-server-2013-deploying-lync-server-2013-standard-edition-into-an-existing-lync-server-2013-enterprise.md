---
title: 'Lync Server 2013: Implantando o Lync Server 2013 Standard Edition em um Lync Server 2013 Enterprise existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76d7183e60c09729758d7297fd3b6db2cd6622d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a><span data-ttu-id="dc6d8-102">Implantando o Lync Server 2013 Standard Edition em um Lync Server 2013 Enterprise existente</span><span class="sxs-lookup"><span data-stu-id="dc6d8-102">Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc6d8-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="dc6d8-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="dc6d8-104">A implantação de um servidor Standard Edition em uma implantação existente do Enterprise Edition é semelhante à implantação de funções de servidor adicionais.</span><span class="sxs-lookup"><span data-stu-id="dc6d8-104">Deploying a Standard Edition server into an existing Enterprise Edition deployment is similar to deploying additional server roles.</span></span> <span data-ttu-id="dc6d8-105">Um servidor Standard Edition pode ser implantado em outro site, permitindo que os usuários desse site sejam hospedados no servidor Standard Edition, e não no pool de front-ends em uma rede de longa distância (WAN).</span><span class="sxs-lookup"><span data-stu-id="dc6d8-105">A Standard Edition server might be deployed to another site, allowing for users in that site to be homed on the Standard Edition server rather than the Front End pool across a wide area network (WAN).</span></span> <span data-ttu-id="dc6d8-106">Os procedimentos para instalar o novo site e os servidores desse site já estão definidos em outras seções da documentação [implantando o Lync Server 2013](lync-server-2013-deploying-lync-server.md) .</span><span class="sxs-lookup"><span data-stu-id="dc6d8-106">The procedures for installing the new site and servers in that site are already defined in other sections of the [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) documentation.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="dc6d8-107">**Para definir um novo site**</span><span class="sxs-lookup"><span data-stu-id="dc6d8-107">**To define a new site**</span></span>

1.  <span data-ttu-id="dc6d8-108">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="dc6d8-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="dc6d8-109">Na árvore do console, clique com o botão direito do mouse em **Lync Server 2013**e, em seguida, clique em **novo site central**.</span><span class="sxs-lookup"><span data-stu-id="dc6d8-109">In the console tree, right-click **Lync Server 2013**, and then click **New Central Site**.</span></span>

3.  <span data-ttu-id="dc6d8-110">Na página **Identificar o site**, nomeie o site e insira uma descrição (opcional).</span><span class="sxs-lookup"><span data-stu-id="dc6d8-110">On the **Identify the site** page, give a name to the site and optionally enter a description.</span></span>

4.  <span data-ttu-id="dc6d8-111">Siga os procedimentos para definir o restante da topologia do site.</span><span class="sxs-lookup"><span data-stu-id="dc6d8-111">Follow the procedures for defining the rest of the site topology.</span></span> <span data-ttu-id="dc6d8-112">Para obter detalhes, consulte [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="dc6d8-112">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

5.  <span data-ttu-id="dc6d8-113">Publique a topologia atualizada.</span><span class="sxs-lookup"><span data-stu-id="dc6d8-113">Publish the updated topology.</span></span> <span data-ttu-id="dc6d8-114">Para obter detalhes, consulte [publish the Topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="dc6d8-114">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

6.  <span data-ttu-id="dc6d8-115">Configurar e instalar um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="dc6d8-115">Set up and install a Standard Edition server.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="dc6d8-116">Se você tiver implantado um ambiente com apenas um servidor Standard Edition, você terá iniciado o processo de instalação do assistente de implantação do Lync Server usando o link <STRONG>preparar primeiro servidor Standard Edition</STRONG> para instalar os arquivos de banco de dados iniciais no novo servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="dc6d8-116">If you have deployed an environment with only a Standard Edition server, you would have begun the setup process from the Lync Server Deployment Wizard by using the <STRONG>Prepare first Standard Edition server</STRONG> link to install the initial database files to the new Standard Edition server.</span></span> <span data-ttu-id="dc6d8-117"><STRONG>Não</STRONG> siga esse processo ao instalar um servidor Standard Edition em uma implantação existente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc6d8-117"><STRONG>Do not</STRONG> follow that process when installing a Standard Edition server into an existing Lync Server 2013 deployment.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

