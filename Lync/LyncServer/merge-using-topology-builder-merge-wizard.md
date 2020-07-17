---
title: Mesclar usando o assistente de mesclagem do construtor de topologia
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4760dcd8810d12b112c3bb042e0f28a039683a08
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a><span data-ttu-id="54966-102">Mesclar usando o assistente de mesclagem do construtor de topologia</span><span class="sxs-lookup"><span data-stu-id="54966-102">Merge using Topology Builder Merge wizard</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54966-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="54966-103">_**Topic Last Modified:** 2012-10-02_</span></span>

1.  <span data-ttu-id="54966-104">Baixar a implantação existente utilizando o Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="54966-104">Download the existing deployment using Topology Builder.</span></span>

2.  <span data-ttu-id="54966-105">No menu **Ação**, selecione **Mesclar o Office Communications Server 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="54966-105">From the **Action** menu, select **Merge Office Communications Server 2007 R2**.</span></span>

3.  <span data-ttu-id="54966-106">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="54966-106">Click **Next**.</span></span>

4.  <span data-ttu-id="54966-107">Em **Especificar Configuração de Borda**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="54966-107">In **Specify Edge Setup**, click **Add**.</span></span>
    
    <span data-ttu-id="54966-108">![Assistente de topologia de mesclagem, especificar página de configuração de borda](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Assistente de topologia de mesclagem, especificar página de configuração de borda")</span><span class="sxs-lookup"><span data-stu-id="54966-108">![Merge Topology Wizard, Specify Edge Setup page](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="54966-p101">Em **Especificar Versão de Borda**, insira o tipo de configuração do Servidor de Borda e clique em **Avançar**. Esse exemplo usa a opção **Servidor de Borda Único**.</span><span class="sxs-lookup"><span data-stu-id="54966-p101">In **Specify Edge Type**, enter the type of Edge Server configuration, and then click **Next**. This example uses the **Single Edge Server** option.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="54966-p102"><STRONG>Implantação de Borda Expandida</STRONG> não é uma configuração suportada. Um <STRONG>Servidor de Borda Expandida</STRONG> deve primeiro ser convertido em um <STRONG>Servidor de Borda Único</STRONG> ou em um Servidor <STRONG>Implantação de Borda Consolidada Balanceada</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="54966-p102"><STRONG>Expanded Edge deployment</STRONG> is not a supported configuration. An <STRONG>Expanded Edge Server</STRONG> must first be converted to a <STRONG>Single Edge Server</STRONG> or a <STRONG>Load-balanced consolidated Edge</STRONG> Server.</span></span>

    
    </div>

6.  <span data-ttu-id="54966-113">Em **especificar configurações de borda interna** , insira as informações relevantes para o FQDN interno e as portas do seu pool de borda conforme necessário e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="54966-113">In **Specify Internal Edge Settings** , enter the relevant information for your Edge pool’s internal FQDN and ports as needed, and then click **Next**.</span></span>
    
    <span data-ttu-id="54966-114">![Caixa de diálogo especificar configurações de borda interna](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Caixa de diálogo especificar configurações de borda interna")</span><span class="sxs-lookup"><span data-stu-id="54966-114">![Specify Internal Edge Settings dialog](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Specify Internal Edge Settings dialog")</span></span>  

7.  <span data-ttu-id="54966-115">Em **Especificar Borda Externa**, insira as informações de FQDN de conferência da Web do seu Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="54966-115">In **Specify External Edge**, enter the web conferencing FQDN information for your Edge Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="54966-p103">Antes de clicar em <STRONG>Avançar</STRONG>, realize a próxima etapa deste procedimento. É muito importante que você não pule esta etapa.</span><span class="sxs-lookup"><span data-stu-id="54966-p103">Before you click <STRONG>Next</STRONG>, do the next step in this procedure. It is very important that you do not miss this step.</span></span>

    
    </div>

8.  <span data-ttu-id="54966-118">Marque a caixa de seleção **este pool de borda é usado para Federação e conectividade de im pública** se você planeja usar o servidor de borda do Office Communications Server 2007 R2 herdado para Federação.</span><span class="sxs-lookup"><span data-stu-id="54966-118">Check the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use the legacy Office Communications Server 2007 R2 Edge Server for federation.</span></span> <span data-ttu-id="54966-119">Se você possui vários Servidores de Borda implantados, somente um deles ficará habilitado para federação.</span><span class="sxs-lookup"><span data-stu-id="54966-119">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="54966-120">Se você não marcar essa caixa e depois decidir que quer habilitar a federação, deve executar o assistente de Mesclagem de Construtor de Topologia novamente e depois publicar sua topologia novamente.</span><span class="sxs-lookup"><span data-stu-id="54966-120">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard and publish your topology again.</span></span>
    
    <span data-ttu-id="54966-121">![Caixa de diálogo servidor de borda, especificar página de borda externa](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Caixa de diálogo servidor de borda, especificar página de borda externa")</span><span class="sxs-lookup"><span data-stu-id="54966-121">![Edge Server dialog, Specify External Edge page](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edge Server dialog, Specify External Edge page")</span></span>  

9.  <span data-ttu-id="54966-122">Em **Especificar próximo salto**, insira o FQDN do próximo salto em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="54966-122">In **Specify Next Hop**, enter the fully qualified domain name (FQDN) of the next hop location in your environment.</span></span> <span data-ttu-id="54966-123">Clique em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="54966-123">Click **Finish**.</span></span>
    
    <span data-ttu-id="54966-124">![Caixa de diálogo servidor de borda, especificar página de próximo salto](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Caixa de diálogo servidor de borda, especificar página de próximo salto")</span><span class="sxs-lookup"><span data-stu-id="54966-124">![Edge Server dialog, Specify Next Hop page](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edge Server dialog, Specify Next Hop page")</span></span>  

10. <span data-ttu-id="54966-125">Em **especificar configuração de borda**, se todos os servidores de borda do Office Communications Server 2007 R2 tiverem sido adicionados, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="54966-125">In **Specify Edge Setup**, if all your Office Communications Server 2007 R2 Edge Servers have been added, click **Next**.</span></span> <span data-ttu-id="54966-126">Se você tiver mais servidores de borda do Office Communications Server 2007 R2 para adicionar, repita este procedimento a partir da etapa 4.</span><span class="sxs-lookup"><span data-stu-id="54966-126">If you have more Office Communications Server 2007 R2 Edge Servers to add, repeat this procedure starting at step 4.</span></span>

11. <span data-ttu-id="54966-127">Em **especificar porta SIP interna** , selecione a configuração padrão (ou seja, se você não modificou a porta SIP padrão).</span><span class="sxs-lookup"><span data-stu-id="54966-127">In **Specify Internal SIP port** , select the default setting (that is, if you did not modify the default SIP port).</span></span> <span data-ttu-id="54966-128">Faça as alterações conforme seja apropriado se você não estiver usando uma porta padrão de 5061 e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="54966-128">Change as appropriate if you are not using a default port of 5061, and then click **Next**.</span></span>

12. <span data-ttu-id="54966-129">Em **Resumo**, clique em **Avançar** para começar a mesclar as topologias.</span><span class="sxs-lookup"><span data-stu-id="54966-129">In **Summary**, click **Next** to begin merging the topologies.</span></span>

13. <span data-ttu-id="54966-130">A página do assistente verifica se a mesclagem das topologias foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="54966-130">The wizard page verifies that the merging of the topologies was successful.</span></span>

14. <span data-ttu-id="54966-131">Na coluna **Status**, verifique se o valor é **Êxito** e clique em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="54966-131">In the **Status** column, verify that the value is **Success**, and then click **Finish**.</span></span>

15. <span data-ttu-id="54966-132">No painel esquerdo do construtor de topologia, você deve ver agora o **BackCompatSite**, que indica que seu ambiente do Office Communications Server 2007 R2 foi mesclado com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54966-132">In the left pane of Topology Builder, you should now see the **BackCompatSite**, which indicates that your Office Communications Server 2007 R2 environment has been merged with Lync Server 2013.</span></span>
    
    <span data-ttu-id="54966-133">![Construtor de topologia mostrando uma topologia mesclada](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Construtor de topologia mostrando uma topologia mesclada")</span><span class="sxs-lookup"><span data-stu-id="54966-133">![Topology Builder showing a merged topology](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder showing a merged topology")</span></span>  

16. <span data-ttu-id="54966-134">No painel **Ações**, no menu **Publicar topologia** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="54966-134">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

17. <span data-ttu-id="54966-135">Quando o **Assistente de publicação** for concluído, clique em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="54966-135">When the **Publishing wizard** completes, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54966-136">É importante que você conclua o próximo tópico, <A href="import-policies-and-settings.md">importar políticas e configurações</A>, para garantir que as configurações da política herdada sejam importadas para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54966-136">It’s important that you complete the next topic, <A href="import-policies-and-settings.md">Import policies and settings</A>, to ensure that the legacy policy settings are imported into Lync Server 2013.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

