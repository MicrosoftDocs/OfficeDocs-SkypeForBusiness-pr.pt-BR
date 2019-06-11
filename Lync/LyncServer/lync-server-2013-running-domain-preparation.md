---
title: 'Lync Server 2013: Executando preparação de domínio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16fdd01b15fe5858129300c3a9f2f26c3d3de672
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="3a3af-102">Executando preparação de domínio para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a3af-102">Running domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a3af-103">_**Tópico da última modificação:** 2013-04-16_</span><span class="sxs-lookup"><span data-stu-id="3a3af-103">_**Topic Last Modified:** 2013-04-16_</span></span>

<span data-ttu-id="3a3af-104">Você pode usar os cmdlets do Shell de gerenciamento do Lync Server e do setup para preparar domínios.</span><span class="sxs-lookup"><span data-stu-id="3a3af-104">You can use Setup or Lync Server Management Shell cmdlets to prepare domains.</span></span> <span data-ttu-id="3a3af-105">O cmdlet que prepara um domínio é **Enable-CsAdDomain**.</span><span class="sxs-lookup"><span data-stu-id="3a3af-105">The cmdlet that prepares a domain is **Enable-CsAdDomain**.</span></span>

<span data-ttu-id="3a3af-106">Preparação do domínio é a etapa final na preparação dos serviços de domínio Active Directory para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a3af-106">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span>

<div>

## <a name="to-use-setup-to-prepare-domains"></a><span data-ttu-id="3a3af-107">Para usar a configuração para preparar domínios</span><span class="sxs-lookup"><span data-stu-id="3a3af-107">To use Setup to prepare domains</span></span>

1.  <span data-ttu-id="3a3af-108">Faça logon em qualquer servidor do domínio como membro do grupo Domain admins.</span><span class="sxs-lookup"><span data-stu-id="3a3af-108">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="3a3af-109">Na pasta de instalação ou mídia do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3a3af-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="3a3af-110">Clique em **Preparar o Active Directory** e espere que o estado da implantação seja determinado.</span><span class="sxs-lookup"><span data-stu-id="3a3af-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="3a3af-111">Na **Etapa 5: preparar o domínio atual**, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="3a3af-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

5.  <span data-ttu-id="3a3af-112">Na página **preparar domínio** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3a3af-112">On the **Prepare Domain** page, click **Next**.</span></span>

6.  <span data-ttu-id="3a3af-113">Na página **Executando Comandos**, procure por **Status da tarefa: Concluída** e clique em **Exibir Log**.</span><span class="sxs-lookup"><span data-stu-id="3a3af-113">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="3a3af-114">Na coluna **ação** , expanda o **domínio Prep**, procure um \*\* \<resultado\> \*\* de execução de sucesso no final de cada tarefa para verificar se a preparação do domínio foi concluída com êxito, feche o log e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="3a3af-114">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="3a3af-115">Aguarde a conclusão da replicação do Active Directory ou force a replicação para todos os controladores de domínio listados no snap-in sites e serviços do Active Directory do controlador de domínio raiz da floresta.</span><span class="sxs-lookup"><span data-stu-id="3a3af-115">Wait for Active Directory replication to complete or force replication to all the domain controllers listed in the Active Directory Sites and Services snap-in for the forest root domain controller.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a><span data-ttu-id="3a3af-116">Usar cmdlets para preparar o domínio</span><span class="sxs-lookup"><span data-stu-id="3a3af-116">To use cmdlets to prepare the domain</span></span>

1.  <span data-ttu-id="3a3af-117">Faça logon em qualquer servidor do domínio como membro do grupo Domain admins.</span><span class="sxs-lookup"><span data-stu-id="3a3af-117">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="3a3af-118">Instale os componentes principais do Lync Server da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="3a3af-118">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="3a3af-119">Na pasta de instalação ou mídia do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3a3af-119">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="3a3af-120">Se você for solicitado a instalar o Microsoft Visual C++ Redistributable, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="3a3af-120">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="3a3af-121">A caixa de diálogo instalação do Lync Server 2013 solicita um local para instalar os arquivos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3a3af-121">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="3a3af-122">Escolha o local padrão ou **navegue** até um local de sua escolha e clique em **instalar**.</span><span class="sxs-lookup"><span data-stu-id="3a3af-122">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="3a3af-123">Na página contrato de licença, marque **a opção aceito os termos do contrato de licença**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a3af-123">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="3a3af-124">O instalador instala os componentes principais do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a3af-124">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="3a3af-125">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3a3af-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="3a3af-126">Execute:</span><span class="sxs-lookup"><span data-stu-id="3a3af-126">Run:</span></span>
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    <span data-ttu-id="3a3af-127">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3a3af-127">For example:</span></span>
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    <span data-ttu-id="3a3af-128">Se você não especificar o parâmetro Domain, o padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="3a3af-128">If you do not specify the Domain parameter, the default is the local domain.</span></span>

5.  <span data-ttu-id="3a3af-129">Verifique se a preparação do domínio foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="3a3af-129">Verify that domain preparation was successful.</span></span> <span data-ttu-id="3a3af-130">Execute:</span><span class="sxs-lookup"><span data-stu-id="3a3af-130">Run:</span></span>
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    <span data-ttu-id="3a3af-131">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3a3af-131">For example:</span></span>
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3a3af-132">O parâmetro GlobalSettingsDomainController permite que você indique onde as configurações globais são armazenadas.</span><span class="sxs-lookup"><span data-stu-id="3a3af-132">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="3a3af-133">Se as configurações estiverem armazenadas no contêiner do sistema (que é típico com implantações de atualização que não tiveram as configurações globais migradas para o contêiner de configuração), defina um controlador de domínio na raiz da sua floresta do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3a3af-133">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global settings migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="3a3af-134">Se as configurações globais estiverem no contêiner Configuração (o que é normal em implantações novas ou em implantações de atualização nas quais as configurações foram migradas para o contêiner Configuração), defina qualquer controlador de domínio na floresta.</span><span class="sxs-lookup"><span data-stu-id="3a3af-134">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="3a3af-135">Se você não especificar esse parâmetro, o cmdlet pressupõe que as configurações são armazenadas no contêiner de configuração e se refere a qualquer controlador de domínio no&nbsp;AD DS.</span><span class="sxs-lookup"><span data-stu-id="3a3af-135">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>
    
    <span data-ttu-id="3a3af-136">Se você não especificar o parâmetro **Domain** , o padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="3a3af-136">If you do not specify the **Domain** parameter, the default is the local domain.</span></span>
    
    <span data-ttu-id="3a3af-137">Esse cmdlet retorna um valor do **estado\_\_\_DOMAINSETTINGS da LC pronto** se a preparação do domínio tiver sido bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="3a3af-137">This cmdlet returns a value of **LC\_DOMAINSETTINGS\_STATE\_READY** if domain preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3a3af-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="3a3af-138">See Also</span></span>


[<span data-ttu-id="3a3af-139">Usando cmdlets para reverter a preparação do domínio para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a3af-139">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[<span data-ttu-id="3a3af-140">Preparando domínios para Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a3af-140">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

