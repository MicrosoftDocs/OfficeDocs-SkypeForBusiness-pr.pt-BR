---
title: 'Lync Server 2013: definir e configurar uma topologia no construtor de topologias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 597f331ba95ee563155fdabc6b95d35367d12080
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a><span data-ttu-id="e3496-102">Definir e configurar uma topologia no construtor de topologias para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3496-102">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3496-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e3496-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e3496-104">Executar o construtor de topologias para definir uma nova topologia ou modificar uma topologia existente não requer a associação a um administrador local ou um grupo de domínio privilegiado.</span><span class="sxs-lookup"><span data-stu-id="e3496-104">Running Topology Builder to define a new topology or to modify an existing topology does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="e3496-105">O construtor de topologias orienta você pelas etapas necessárias para definir sua topologia para um pool de front-ends Enterprise Edition ou Standard Edition, com base em seus requisitos de configuração.</span><span class="sxs-lookup"><span data-stu-id="e3496-105">Topology Builder guides you through the steps necessary to define your topology for an Enterprise Edition Front End pool or a Standard Edition, based on your configuration requirements.</span></span>

<span data-ttu-id="e3496-106">Você deve usar o construtor de topologias para concluir e publicar a topologia antes de poder instalar o Lync Server 2013 em servidores.</span><span class="sxs-lookup"><span data-stu-id="e3496-106">You must use Topology Builder to complete and publish the topology before you can install Lync Server 2013 on servers.</span></span> <span data-ttu-id="e3496-107">O procedimento a seguir inclui as etapas necessárias para definir uma nova topologia.</span><span class="sxs-lookup"><span data-stu-id="e3496-107">The following procedure includes the steps required to define a new topology.</span></span>

<div>

## <a name="to-define-a-topology"></a><span data-ttu-id="e3496-108">Para definir uma topologia</span><span class="sxs-lookup"><span data-stu-id="e3496-108">To define a topology</span></span>

1.  <span data-ttu-id="e3496-109">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e3496-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="e3496-110">No construtor de topologias, selecione **nova topologia**.</span><span class="sxs-lookup"><span data-stu-id="e3496-110">In Topology Builder, select **New Topology**.</span></span> <span data-ttu-id="e3496-111">Você será solicitado a fornecer um local e um nome de arquivo para salvar a topologia.</span><span class="sxs-lookup"><span data-stu-id="e3496-111">You are prompted for a location and file name for saving the topology.</span></span> <span data-ttu-id="e3496-112">Dê ao arquivo de topologia um nome significativo e aceite a extensão padrão de. tbxml.</span><span class="sxs-lookup"><span data-stu-id="e3496-112">Give the topology file a meaningful name and accept the default extension of .tbxml.</span></span> <span data-ttu-id="e3496-113">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3496-113">Click **OK**.</span></span>

3.  <span data-ttu-id="e3496-114">Navegue até o local onde deseja salvar o novo arquivo XML de topologia, insira um nome para o arquivo e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="e3496-114">Navigate to the location where you want to save the new topology XML file, enter a name for the file, and then click **Save**.</span></span>

4.  <span data-ttu-id="e3496-115">Na página **definir o domínio primário** , digite o nome do domínio SIP principal da sua organização e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e3496-115">On the **Define the primary domain** page, enter the name of the primary SIP domain for your organization, and then click **Next**.</span></span>

5.  <span data-ttu-id="e3496-116">Na página **especificar domínios com suporte adicional** , insira os nomes de domínios adicionais, se houver, e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e3496-116">On the **Specify additional supported domains** page, enter the names of additional domains, if any, and then click **Next**.</span></span>

6.  <span data-ttu-id="e3496-117">Na página **definir o primeiro site** , digite um nome e uma descrição para o primeiro site e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e3496-117">On the **Define the first site** page, enter a name and a description for the first site, and then click **Next**.</span></span>

7.  <span data-ttu-id="e3496-118">Na página **especificar detalhes do site** , insira as informações de local para o site e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e3496-118">On the **Specify site details** page, enter the location information for the site, and then click **Next**.</span></span>

8.  <span data-ttu-id="e3496-119">Na página **nova topologia definida com êxito** , certifique-se de que a caixa de seleção **abrir o assistente de novo front-end quando este assistente for fechado** esteja marcada e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="e3496-119">On the **New topology was successfully defined** page, make sure the **Open the New Front End Wizard when this wizard closes** check box is selected, and then click **Finish**.</span></span>

<span data-ttu-id="e3496-120">Depois de definir e salvar a topologia, use o assistente de novo front-end para definir um pool de front-ends ou servidor Standard Edition para o site.</span><span class="sxs-lookup"><span data-stu-id="e3496-120">After you’ve defined and saved the topology, use the New Front End Wizard to define a Front End pool or Standard Edition server for your site.</span></span> <span data-ttu-id="e3496-121">Para obter detalhes, consulte [define and configure a front end pool or Standard Edition Server in Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="e3496-121">For details, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

