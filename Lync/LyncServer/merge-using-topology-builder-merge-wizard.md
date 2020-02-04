---
title: Mesclar usando o assistente de mesclagem do construtor de topologia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61981ae875fef9976377644a9b67f0a329581a90
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a><span data-ttu-id="963ce-102">Mesclar usando o assistente de mesclagem do construtor de topologia</span><span class="sxs-lookup"><span data-stu-id="963ce-102">Merge using Topology Builder Merge wizard</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="963ce-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="963ce-103">_**Topic Last Modified:** 2012-10-02_</span></span>

1.  <span data-ttu-id="963ce-104">Baixe a implantação existente usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="963ce-104">Download the existing deployment using Topology Builder.</span></span>

2.  <span data-ttu-id="963ce-105">No menu **ação** , selecione **mesclar o Office communications Server 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="963ce-105">From the **Action** menu, select **Merge Office Communications Server 2007 R2**.</span></span>

3.  <span data-ttu-id="963ce-106">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="963ce-106">Click **Next**.</span></span>

4.  <span data-ttu-id="963ce-107">Em **especificar a configuração de borda**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="963ce-107">In **Specify Edge Setup**, click **Add**.</span></span>
    
    <span data-ttu-id="963ce-108">![Assistente de topologia de mesclagem, especificar a página de configuração de borda](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Assistente de topologia de mesclagem, especificar a página de configuração de borda")</span><span class="sxs-lookup"><span data-stu-id="963ce-108">![Merge Topology Wizard, Specify Edge Setup page](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="963ce-109">Em **especificar tipo de borda**, insira o tipo de configuração do servidor de borda e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="963ce-109">In **Specify Edge Type**, enter the type of Edge Server configuration, and then click **Next**.</span></span> <span data-ttu-id="963ce-110">Este exemplo usa a opção **servidor de borda única** .</span><span class="sxs-lookup"><span data-stu-id="963ce-110">This example uses the **Single Edge Server** option.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="963ce-111">A <STRONG>implantação de borda expandida</STRONG> não é uma configuração com suporte.</span><span class="sxs-lookup"><span data-stu-id="963ce-111"><STRONG>Expanded Edge deployment</STRONG> is not a supported configuration.</span></span> <span data-ttu-id="963ce-112">Um <STRONG>servidor de borda expandida</STRONG> deve primeiro ser convertido em um <STRONG>servidor de borda único</STRONG> ou em um servidor de <STRONG>borda consolidada com balanceamento de carga</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="963ce-112">An <STRONG>Expanded Edge Server</STRONG> must first be converted to a <STRONG>Single Edge Server</STRONG> or a <STRONG>Load-balanced consolidated Edge</STRONG> Server.</span></span>

    
    </div>

6.  <span data-ttu-id="963ce-113">Em **especificar as configurações de borda interna** , insira as informações relevantes para o FQDN e as portas internas do seu pool de bordas, conforme necessário, e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="963ce-113">In **Specify Internal Edge Settings** , enter the relevant information for your Edge pool’s internal FQDN and ports as needed, and then click **Next**.</span></span>
    
    <span data-ttu-id="963ce-114">![Especificar a caixa de diálogo Configurações de borda interna](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Especificar a caixa de diálogo Configurações de borda interna")</span><span class="sxs-lookup"><span data-stu-id="963ce-114">![Specify Internal Edge Settings dialog](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Specify Internal Edge Settings dialog")</span></span>  

7.  <span data-ttu-id="963ce-115">Em **especificar borda externa**, insira as informações de FQDN do servidor de Webconferência para o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="963ce-115">In **Specify External Edge**, enter the web conferencing FQDN information for your Edge Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="963ce-116">Antes de clicar em <STRONG>Avançar</STRONG>, siga o próximo passo deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="963ce-116">Before you click <STRONG>Next</STRONG>, do the next step in this procedure.</span></span> <span data-ttu-id="963ce-117">É muito importante que você não perca esta etapa.</span><span class="sxs-lookup"><span data-stu-id="963ce-117">It is very important that you do not miss this step.</span></span>

    
    </div>

8.  <span data-ttu-id="963ce-118">Marque a caixa de seleção **este pool de bordas é usado para a Federação e conectividade de mensagem de chat pública** se você planeja usar o servidor de borda herdado do Office Communications Server 2007 R2 para Federação.</span><span class="sxs-lookup"><span data-stu-id="963ce-118">Check the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use the legacy Office Communications Server 2007 R2 Edge Server for federation.</span></span> <span data-ttu-id="963ce-119">Se você tiver vários servidores de Borda implantados, apenas um deles será habilitado para Federação.</span><span class="sxs-lookup"><span data-stu-id="963ce-119">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="963ce-120">Se você não marcar esta caixa e decidir mais tarde que deseja habilitar a Federação, execute o assistente de mesclagem do construtor de topologias e publique sua topologia novamente.</span><span class="sxs-lookup"><span data-stu-id="963ce-120">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard and publish your topology again.</span></span>
    
    <span data-ttu-id="963ce-121">![Caixa de diálogo servidor de borda, especificar a página de borda externa](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Caixa de diálogo servidor de borda, especificar a página de borda externa")</span><span class="sxs-lookup"><span data-stu-id="963ce-121">![Edge Server dialog, Specify External Edge page](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edge Server dialog, Specify External Edge page")</span></span>  

9.  <span data-ttu-id="963ce-122">Em **especificar próximo salto**, digite o nome de domínio totalmente qualificado (FQDN) do próximo local do salto em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="963ce-122">In **Specify Next Hop**, enter the fully qualified domain name (FQDN) of the next hop location in your environment.</span></span> <span data-ttu-id="963ce-123">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="963ce-123">Click **Finish**.</span></span>
    
    <span data-ttu-id="963ce-124">![Caixa de diálogo servidor de borda, especifique a página de próximo salto](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Caixa de diálogo servidor de borda, especifique a página de próximo salto")</span><span class="sxs-lookup"><span data-stu-id="963ce-124">![Edge Server dialog, Specify Next Hop page](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edge Server dialog, Specify Next Hop page")</span></span>  

10. <span data-ttu-id="963ce-125">Em **especificar a configuração de borda**, se todos os seus servidores do Office Communications Server 2007 R2 Edge tiverem sido adicionados, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="963ce-125">In **Specify Edge Setup**, if all your Office Communications Server 2007 R2 Edge Servers have been added, click **Next**.</span></span> <span data-ttu-id="963ce-126">Se você tiver mais servidores do Office Communications Server 2007 R2 Edge para adicionar, repita esse procedimento começando na etapa 4.</span><span class="sxs-lookup"><span data-stu-id="963ce-126">If you have more Office Communications Server 2007 R2 Edge Servers to add, repeat this procedure starting at step 4.</span></span>

11. <span data-ttu-id="963ce-127">Em **especificar porta SIP interna** , selecione a configuração padrão (ou seja, se você não tiver modificado a porta SIP padrão).</span><span class="sxs-lookup"><span data-stu-id="963ce-127">In **Specify Internal SIP port** , select the default setting (that is, if you did not modify the default SIP port).</span></span> <span data-ttu-id="963ce-128">Altere conforme apropriado se você não estiver usando uma porta padrão do 5061 e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="963ce-128">Change as appropriate if you are not using a default port of 5061, and then click **Next**.</span></span>

12. <span data-ttu-id="963ce-129">Em **Resumo**, clique em **Avançar** para começar a mesclar as topologias.</span><span class="sxs-lookup"><span data-stu-id="963ce-129">In **Summary**, click **Next** to begin merging the topologies.</span></span>

13. <span data-ttu-id="963ce-130">A página do assistente verifica se a mesclagem das topologias foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="963ce-130">The wizard page verifies that the merging of the topologies was successful.</span></span>

14. <span data-ttu-id="963ce-131">Na coluna **status** , verifique se o valor é **êxito**e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="963ce-131">In the **Status** column, verify that the value is **Success**, and then click **Finish**.</span></span>

15. <span data-ttu-id="963ce-132">No painel esquerdo do construtor de topologias, agora você deve ver o **BackCompatSite**, que indica que o ambiente do Office Communications Server 2007 R2 foi mesclado com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="963ce-132">In the left pane of Topology Builder, you should now see the **BackCompatSite**, which indicates that your Office Communications Server 2007 R2 environment has been merged with Lync Server 2013.</span></span>
    
    <span data-ttu-id="963ce-133">![Construtor de topologias mostrando uma topologia mesclada](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Construtor de topologias mostrando uma topologia mesclada")</span><span class="sxs-lookup"><span data-stu-id="963ce-133">![Topology Builder showing a merged topology](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder showing a merged topology")</span></span>  

16. <span data-ttu-id="963ce-134">No menu **ação** , clique em **publicar topologia**e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="963ce-134">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

17. <span data-ttu-id="963ce-135">Quando o **Assistente de publicação** for concluído, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="963ce-135">When the **Publishing wizard** completes, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="963ce-136">É importante que você conclua o próximo tópico, <A href="import-policies-and-settings.md">importar políticas e configurações</A>, para garantir que as configurações de política herdadas sejam importadas para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="963ce-136">It’s important that you complete the next topic, <A href="import-policies-and-settings.md">Import policies and settings</A>, to ensure that the legacy policy settings are imported into Lync Server 2013.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

