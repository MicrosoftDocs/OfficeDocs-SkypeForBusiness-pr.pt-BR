---
title: 'Lync Server 2013: Executando preparação de floresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 129926afe17f946a2ea32d7c67fdea89fab32a54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="c6d8d-102">Executando preparação de floresta para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6d8d-102">Running forest preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6d8d-103">_**Tópico da última modificação:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="c6d8d-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="c6d8d-104">Você pode usar os cmdlets do Shell de gerenciamento do Lync Server e do setup para preparar a floresta.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the forest.</span></span> <span data-ttu-id="c6d8d-105">O cmdlet que prepara a floresta é **Enable-CsAdForest**.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-105">The cmdlet that prepares the forest is **Enable-CsAdForest**.</span></span>

<span data-ttu-id="c6d8d-106">Depois de preparar a floresta, você deve verificar se as configurações globais foram duplicadas antes de executar a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-106">After you prepare the forest, you must verify that global settings have been replicated before running domain preparation.</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a><span data-ttu-id="c6d8d-107">Para usar a instalação para preparar a floresta</span><span class="sxs-lookup"><span data-stu-id="c6d8d-107">To use Setup to prepare the forest</span></span>

1.  <span data-ttu-id="c6d8d-108">Faça logon em um computador que esteja associado a um domínio como membro do grupo Administradores de empresa do domínio raiz da floresta.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-108">Log on to a computer that is joined to a domain as a member of the Enterprise Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="c6d8d-109">Na pasta de instalação ou mídia do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="c6d8d-110">Clique em **Preparar o Active Directory** e espere que o estado da implantação seja determinado.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="c6d8d-111">Na **etapa 3: preparar a floresta atual**, clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-111">At **Step 3: Prepare Current Forest**, click **Run**.</span></span>

5.  <span data-ttu-id="c6d8d-112">Na página **preparar floresta** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-112">On the **Prepare Forest** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c6d8d-113">A preparação da floresta permite que você escolha onde colocar os grupos universais do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-113">Forest Preparation allows you to choose where to place the Universal Groups for Lync Server 2013.</span></span> <span data-ttu-id="c6d8d-114">Escolha um local que atenda aos requisitos de sua organização.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-114">Choose a location that is consistent with the requirements of your organization.</span></span>

    
    </div>

6.  <span data-ttu-id="c6d8d-115">Na página **Executando Comandos**, procure por **Status da tarefa: Concluída** e clique em **Exibir Log**.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-115">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="c6d8d-116">Na coluna **Action (ação** ), expanda **Forest prep**, procure um \*\* \<\> \*\* resultado de execução de sucesso no final de cada tarefa para verificar se a preparação da floresta foi concluída com êxito, feche o log e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-116">Under the **Action** column, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="c6d8d-117">Aguarde a conclusão da replicação do Active Directory ou force a replicação para todos os controladores de domínio listados no snap-in **sites e serviços do Active Directory** para o controlador de domínio raiz da floresta, antes de executar a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-117">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="c6d8d-118">Force a replicação entre os controladores de domínio em todos os sites do Active Directory para fazer com que a replicação dentro dos sites ocorra em minutos.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-118">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a><span data-ttu-id="c6d8d-119">Para usar cmdlets para preparar a floresta</span><span class="sxs-lookup"><span data-stu-id="c6d8d-119">To use cmdlets to prepare the forest</span></span>

1.  <span data-ttu-id="c6d8d-120">Faça logon em um computador que esteja associado a um domínio como membro do grupo Domain admins no domínio raiz da floresta.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-120">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="c6d8d-121">Instale os componentes principais do Lync Server da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c6d8d-121">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="c6d8d-122">Na pasta de instalação ou mídia do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-122">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="c6d8d-123">Se você for solicitado a instalar o Microsoft Visual C++ Redistributable, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-123">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="c6d8d-124">A caixa de diálogo instalação do Lync Server 2013 solicita um local para instalar os arquivos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-124">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="c6d8d-125">Escolha o local padrão ou **navegue** até um local de sua escolha e clique em **instalar**.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-125">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="c6d8d-126">Na página contrato de licença, marque **a opção aceito os termos do contrato de licença**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-126">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="c6d8d-127">O instalador instala os componentes principais do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-127">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="c6d8d-128">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="c6d8d-129">Execute:</span><span class="sxs-lookup"><span data-stu-id="c6d8d-129">Run:</span></span>
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    <span data-ttu-id="c6d8d-130">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c6d8d-130">For example:</span></span>
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    <span data-ttu-id="c6d8d-131">Se você não especificar o parâmetro GroupDomain, o valor padrão será o domínio local.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-131">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span> <span data-ttu-id="c6d8d-132">Se grupos universais foram criados anteriormente em um domínio que não seja o domínio padrão, você deve especificar o parâmetro GroupDomain explicitamente.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-132">If universal groups were created previously in a domain that is not the default domain, you must specify the GroupDomain parameter explicitly.</span></span>

5.  <span data-ttu-id="c6d8d-133">Aguarde a conclusão da replicação do Active Directory ou force a replicação para todos os controladores de domínio listados no snap-in **sites e serviços do Active Directory** para o controlador de domínio raiz da floresta, antes de executar a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-133">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span>

6.  <span data-ttu-id="c6d8d-134">Verifique se a preparação da floresta foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-134">Verify that forest preparation was successful.</span></span> <span data-ttu-id="c6d8d-135">Execute:</span><span class="sxs-lookup"><span data-stu-id="c6d8d-135">Run:</span></span>
    
        Get-CsAdForest 
    
    <span data-ttu-id="c6d8d-136">Esse cmdlet retorna um valor do **estado\_\_\_FORESTSETTINGS da LC pronto** se a preparação da floresta tiver sido bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="c6d8d-136">This cmdlet returns a value of **LC\_FORESTSETTINGS\_STATE\_READY** if forest preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c6d8d-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="c6d8d-137">See Also</span></span>


[<span data-ttu-id="c6d8d-138">Usando cmdlets para reverter preparação da floresta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6d8d-138">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[<span data-ttu-id="c6d8d-139">Preparando a floresta para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6d8d-139">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

