---
title: Configurando o Lync Server 2013 para trabalhar com o servidor do Office Web Apps
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ba6926af243b15449c5b8baa4b29706a2ec8ade
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a><span data-ttu-id="d09dc-102">Configurando o Lync Server 2013 para trabalhar com o servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="d09dc-102">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d09dc-103">_**Tópico da última modificação:** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="d09dc-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="d09dc-104">Antes de poder configurar o Lync Server 2013 para usar o Office Web Apps Server, o Office Web Apps Server deve ser implantado e configurado.</span><span class="sxs-lookup"><span data-stu-id="d09dc-104">Before you can configure Lync Server 2013 to use Office Web Apps Server, Office Web Apps Server must be deployed and configured.</span></span> <span data-ttu-id="d09dc-105">Consulte o guia do documento **para implantar o Office Web Apps Server e os Office Web Apps** para obter informações detalhadas sobre como instalar e configurar um único servidor do Office Web Apps ou para obter informações sobre como instalar e configurar um Office Web Apps Server farm para alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="d09dc-105">See the document **Guide to Deploying Office Web Apps Server and Office Web Apps** for detail information on how to install and configure a single Office Web Apps Server, or for information on how to install and configure an Office Web Apps Server Farm for high availability.</span></span>

<span data-ttu-id="d09dc-106">Após a instalação bem-sucedida do Office Web Apps Server e sua Web farm configurada corretamente, você deve configurar o Lync Server para se comunicar com o novo servidor; Isso é feito adicionando-se a URL de descoberta do servidor do Office Web Apps à sua topologia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d09dc-106">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Lync Server to communicate with the new server; this is done by adding the Office Web Apps Server discovery URL to your Lync Server topology.</span></span> <span data-ttu-id="d09dc-107">Para adicionar o Servidor do Office Web Apps à sua topologia, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="d09dc-107">To add Office Web Apps Server to your topology, complete the following steps:</span></span>

1.  <span data-ttu-id="d09dc-108">Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d09dc-108">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="d09dc-109">Na caixa de diálogo **Construtor de Topologias**, selecione **Baixar topologia da implantação existente** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d09dc-109">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="d09dc-p103">Na caixa de diálogo  **Salvar Topologia como**, digite um nome para o documento de topologia (por exemplo, **PreWebAppsServerTopology**) na caixa  **Nome do arquivo** e clique em **Salvar**. Posteriormente, essa topologia poderá ser recuperada e publicada novamente se houver problemas com a nova topologia.</span><span class="sxs-lookup"><span data-stu-id="d09dc-p103">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**. This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>

4.  <span data-ttu-id="d09dc-112">No construtor de topologias, expanda o **Lync Server 2013**, expanda o nome do seu site, expanda Pools de **front-end do Enterprise Edition**, clique com o botão direito do mouse no nome de um dos seus pools e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d09dc-112">In Topology Builder, expand **Lync Server 2013**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>

5.  <span data-ttu-id="d09dc-113">Na caixa de diálogo **Editar Propriedades**, na guia **Geral**, encontre o cabeçalho **Associar Servidor do Office Web Apps** e clique em **Novo** (ou selecione um Servidor do Office Web Apps existente na lista suspensa).</span><span class="sxs-lookup"><span data-stu-id="d09dc-113">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

6.  <span data-ttu-id="d09dc-114">Na caixa de diálogo **Definir Novo Servidor do Office Web Apps**, digite o FQDN (nome de domínio totalmente qualificado) do computador do Servidor do Office Web Apps na caixa **FQDN do Servidor do Office Web Apps**. Quando você fizer isso, a URL de descoberta de seu Servidor do Office Web Apps deverá ser inserida automaticamente na caixa **Office Web URL de descoberta de Servidor do Office Web Apps**.</span><span class="sxs-lookup"><span data-stu-id="d09dc-114">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="d09dc-115">Se o Office Web Apps Server estiver instalado no local e na mesma zona de rede do Lync Server 2013, a opção **Office Web Apps Server será implantada em uma rede externa (isto é, perímetro/Internet)** não deve ser selecionada.</span><span class="sxs-lookup"><span data-stu-id="d09dc-115">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="d09dc-116">Se o Servidor do Office Web Apps for implantado fora do seu firewall interno, seleciona a opção **O Servidor do Office Web Apps é implantado em uma rede externa (ou seja, de perímetro/Internet)**.</span><span class="sxs-lookup"><span data-stu-id="d09dc-116">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>

7.  <span data-ttu-id="d09dc-117">Na caixa de diálogo **Definir Novo Servidor Office Web Apps**, clique em **OK** e em **OK** na caixa de diálogo **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d09dc-117">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box.</span></span> <span data-ttu-id="d09dc-118">A URL de descoberta do Office Web Apps será então listada como uma das associações do pool.</span><span class="sxs-lookup"><span data-stu-id="d09dc-118">The Office Web Apps discovery URL will then be listed as one of the pool's Associations.</span></span>

<span data-ttu-id="d09dc-119">Você precisará repetir esse processo para cada pool que precisar ser associado ao seu Servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="d09dc-119">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>

<span data-ttu-id="d09dc-120">Depois de adicionar a URL de descoberta à topologia, você deve publicar essa topologia atualizada.</span><span class="sxs-lookup"><span data-stu-id="d09dc-120">After you have added the discovery URL to the topology you must then publish this updated topology.</span></span> <span data-ttu-id="d09dc-121">Para isso, no Construtor de Topologias:</span><span class="sxs-lookup"><span data-stu-id="d09dc-121">To do that in Topology Builder:</span></span>

1.  <span data-ttu-id="d09dc-122">Clique em **Ação** e depois em **Publicar Topologia**.</span><span class="sxs-lookup"><span data-stu-id="d09dc-122">Click **Action** and then click **Publish Topology**.</span></span>

2.  <span data-ttu-id="d09dc-123">No assistente Publicar topologia, na página **Publicar a Topologia**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d09dc-123">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="d09dc-124">Na página **Assistente de publicação concluído**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="d09dc-124">On the **Publishing wizard complete** page, click **Finish**.</span></span>

4.  <span data-ttu-id="d09dc-125">Feche o Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="d09dc-125">Close Topology Builder.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

