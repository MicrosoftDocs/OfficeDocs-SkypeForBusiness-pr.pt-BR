---
title: 'Lync Server 2013: executando preparação de domínio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d22c35f4e1a2b117ffa765446a94c9a7d2b0fd0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="67757-102">Executando a preparação do domínio para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67757-102">Running domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67757-103">_**Última modificação do tópico:** 2013-04-16_</span><span class="sxs-lookup"><span data-stu-id="67757-103">_**Topic Last Modified:** 2013-04-16_</span></span>

<span data-ttu-id="67757-104">Você pode usar os cmdlets de instalação ou do Shell de gerenciamento do Lync Server para preparar domínios.</span><span class="sxs-lookup"><span data-stu-id="67757-104">You can use Setup or Lync Server Management Shell cmdlets to prepare domains.</span></span> <span data-ttu-id="67757-105">O cmdlet que prepara um domínio é **Enable-CsAdDomain**.</span><span class="sxs-lookup"><span data-stu-id="67757-105">The cmdlet that prepares a domain is **Enable-CsAdDomain**.</span></span>

<span data-ttu-id="67757-106">A preparação do domínio é a etapa final da preparação dos serviços de domínio do Active Directory para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67757-106">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span>

<div>

## <a name="to-use-setup-to-prepare-domains"></a><span data-ttu-id="67757-107">Para usar a Instalação para preparar domínios</span><span class="sxs-lookup"><span data-stu-id="67757-107">To use Setup to prepare domains</span></span>

1.  <span data-ttu-id="67757-108">Faça logon em qualquer servidor no domínio como membro do grupo Administradores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="67757-108">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="67757-109">Na pasta ou mídia de instalação do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67757-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="67757-110">Clique em **Preparar Active Directory** e aguarde o estado de implantação ser determinado.</span><span class="sxs-lookup"><span data-stu-id="67757-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="67757-111">Na **Etapa 5: Preparar o Domínio Atual**, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="67757-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

5.  <span data-ttu-id="67757-112">Na página **Preparar Domínio**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="67757-112">On the **Prepare Domain** page, click **Next**.</span></span>

6.  <span data-ttu-id="67757-113">Na página **Executando Comandos**, procure **Status da tarefa: Concluída** e clique em **Exibir Log**.</span><span class="sxs-lookup"><span data-stu-id="67757-113">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="67757-114">Na coluna **ação** , expanda **domínio Prep**, procure um \*\* \<\> \*\* resultado de execução de êxito no final de cada tarefa para verificar se a preparação do domínio foi concluída com êxito, feche o log e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="67757-114">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="67757-115">Aguarde a conclusão da replicação do Active Directory ou force a replicação para todos os controladores de domínio listados no snap-in Sites e Serviços do Active Directory para o controlador de domínio raiz da floresta.</span><span class="sxs-lookup"><span data-stu-id="67757-115">Wait for Active Directory replication to complete or force replication to all the domain controllers listed in the Active Directory Sites and Services snap-in for the forest root domain controller.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a><span data-ttu-id="67757-116">Para usar cmdlets para preparar o domínio</span><span class="sxs-lookup"><span data-stu-id="67757-116">To use cmdlets to prepare the domain</span></span>

1.  <span data-ttu-id="67757-117">Faça o logon em qualquer servidor do domínio como um membro do grupo Admins de Domínio.</span><span class="sxs-lookup"><span data-stu-id="67757-117">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="67757-118">Instale os componentes principais do Lync Server da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="67757-118">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="67757-119">Na pasta ou mídia de instalação do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67757-119">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="67757-120">Se for solicitado que você instale o Microsoft Visual C++ Redistributable, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="67757-120">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="67757-121">A caixa de diálogo instalação do Lync Server 2013 solicita um local para instalar os arquivos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="67757-121">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="67757-122">Escolha o local padrão ou **Procure** um local de sua escolha e clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="67757-122">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="67757-123">Na página Contrato de Licença, marque **Aceito os termos do contrato de licença** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="67757-123">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="67757-124">O instalador instala os componentes principais do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67757-124">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="67757-125">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="67757-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="67757-126">Sejam</span><span class="sxs-lookup"><span data-stu-id="67757-126">Run:</span></span>
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    <span data-ttu-id="67757-127">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="67757-127">For example:</span></span>
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    <span data-ttu-id="67757-128">Se você não especificar o parâmetro de Domínio, o padrão é o domínio local.</span><span class="sxs-lookup"><span data-stu-id="67757-128">If you do not specify the Domain parameter, the default is the local domain.</span></span>

5.  <span data-ttu-id="67757-p104">Verificar se a preparação de domínio teve êxito. Execute:</span><span class="sxs-lookup"><span data-stu-id="67757-p104">Verify that domain preparation was successful. Run:</span></span>
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    <span data-ttu-id="67757-131">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="67757-131">For example:</span></span>
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="67757-132">O parâmetro GlobalSettingsDomainController permite indicar onde as configurações globais estão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="67757-132">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="67757-133">Se estiverem armazenadas no contêiner Sistema (o que é comum, quando as importações de atualização não tiveram a configuração global migrada para o contêiner Configuração), você definirá um controlador de domínio na raiz da sua floresta do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="67757-133">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global settings migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="67757-134">Se as configurações globais estiverem no contêiner Configuração (o que é comum nas novas implantações ou nas atualizadas, onde as configurações foram migradas para o contêiner Configuração), você definirá qualquer controlador de domínio na floresta.</span><span class="sxs-lookup"><span data-stu-id="67757-134">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="67757-135">Se você não especificar esse parâmetro, o cmdlet assumirá que as configurações são armazenadas no contêiner de configuração e se refere a qualquer controlador de domínio&nbsp;no AD DS.</span><span class="sxs-lookup"><span data-stu-id="67757-135">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>
    
    <span data-ttu-id="67757-136">Se você não especificar o parâmetro **Domain** , o padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="67757-136">If you do not specify the **Domain** parameter, the default is the local domain.</span></span>
    
    <span data-ttu-id="67757-137">Este cmdlet retorna um valor de **LC\_DOMAINSETTINGS\_estado\_pronto** se a preparação do domínio tiver sido bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="67757-137">This cmdlet returns a value of **LC\_DOMAINSETTINGS\_STATE\_READY** if domain preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="67757-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="67757-138">See Also</span></span>


[<span data-ttu-id="67757-139">Usando cmdlets para reverter a preparação do domínio para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67757-139">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[<span data-ttu-id="67757-140">Preparando domínios para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67757-140">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

