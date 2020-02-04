---
title: 'Lync Server 2013: Executando preparação de esquema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06b02981e9baa589801839c8fd8c871ae35b0dde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a><span data-ttu-id="ef4c5-102">Executando preparação de esquema de Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef4c5-102">Running Active Directory schema preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef4c5-103">_**Tópico da última modificação:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="ef4c5-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="ef4c5-104">Você pode usar os cmdlets do Shell de gerenciamento do Lync Server e do setup para preparar o esquema do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the Active Directory schema.</span></span> <span data-ttu-id="ef4c5-105">O cmdlet que estende o esquema do Active Directory é **install-CsAdServerSchema**.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-105">The cmdlet that extends the Active Directory schema is **Install-CsAdServerSchema**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ef4c5-106">O cmdlet de preparação do esquema (<STRONG>install-CsAdServerSchema</STRONG>) deve acessar o mestre de esquema, que requer que o serviço do registro remoto esteja em execução e que a chave do registro remoto esteja habilitada.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-106">The schema preparation cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) must access the schema master, which requires that the remote registry service is running and that the remote registry key is enabled.</span></span> <span data-ttu-id="ef4c5-107">Se o serviço de registro remoto não puder ser habilitado no mestre de esquema, você poderá executar o cmdlet localmente no mestre de esquema.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-107">If the remote registry service cannot be enabled on the schema master, you can run the cmdlet locally on the schema master.</span></span> <span data-ttu-id="ef4c5-108">Para obter detalhes sobre o acesso remoto ao registro, consulte o artigo 314837 da base de dados de conhecimento Microsoft, "como gerenciar o <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>acesso remoto ao registro".</span><span class="sxs-lookup"><span data-stu-id="ef4c5-108">For details about registry remote access, see Microsoft Knowledge Base article 314837, "How to Manage Remote Access to the Registry," at <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span></span>



</div>

<span data-ttu-id="ef4c5-109">Depois de concluir a preparação do esquema, verifique manualmente se a partição do esquema foi replicada antes de prosseguir com a preparação da floresta.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-109">After you complete schema preparation, manually verify that the schema partition has been replicated before proceeding to forest preparation.</span></span> <span data-ttu-id="ef4c5-110">Para obter detalhes, consulte [verificando a replicação de esquema do Active Directory no Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ef4c5-110">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="ef4c5-111">Para usar a instalação para preparar o esquema da floresta atual</span><span class="sxs-lookup"><span data-stu-id="ef4c5-111">To use Setup to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="ef4c5-112">Faça logon em um servidor na sua floresta como membro do grupo Administradores de esquemas e com direitos de administrador no mestre de esquema.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-112">Log on to a server in your forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="ef4c5-113">Na pasta de instalação ou mídia do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-113">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="ef4c5-114">Se você for solicitado a instalar o Microsoft Visual C++ Redistributable, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-114">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>

4.  <span data-ttu-id="ef4c5-115">A caixa de diálogo instalação do Lync Server 2013 solicita um local para instalar os arquivos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-115">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="ef4c5-116">Escolha o local padrão ou **navegue** até um local de sua escolha e clique em **instalar**.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-116">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>

5.  <span data-ttu-id="ef4c5-117">Na página contrato de licença, marque **a opção aceito os termos do contrato de licença**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-117">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span>

6.  <span data-ttu-id="ef4c5-118">O instalador instala os componentes principais do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-118">The installer installs the Lync Server Core Components.</span></span>

7.  <span data-ttu-id="ef4c5-119">Quando o assistente de implantação estiver pronto, clique em **preparar o Active Directory**e aguarde o estado de implantação ser determinado.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-119">When the Deployment Wizard is ready, click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

8.  <span data-ttu-id="ef4c5-120">Na **etapa 1: preparar o esquema**, clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-120">At **Step 1: Prepare Schema**, click **Run**.</span></span>

9.  <span data-ttu-id="ef4c5-121">Na página **preparar esquema** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-121">On the **Prepare Schema** page, click **Next**.</span></span>

10. <span data-ttu-id="ef4c5-122">Na página **Executando Comandos**, procure por **Status da tarefa: Concluída** e clique em **Exibir Log**.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-122">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

11. <span data-ttu-id="ef4c5-123">Na coluna **Action (ação** ), expanda **Schema prep**, procure o resultado da \*\* \<execução Success\> \*\* no final de cada tarefa para verificar se a preparação do esquema foi concluída com êxito, feche o log e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-123">Under the **Action** column, expand **Schema Prep**, look for the **\<Success\>** Execution Result at the end of each task to verify that schema preparation completed successfully, close the log, and then click **Finish**.</span></span>

12. <span data-ttu-id="ef4c5-124">Aguarde a conclusão da replicação do Active Directory ou force a replicação.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-124">Wait for Active Directory replication to complete or force replication.</span></span>

13. <span data-ttu-id="ef4c5-125">Verifique manualmente se as alterações de esquema foram duplicadas para todos os outros controladores de domínio.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-125">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="ef4c5-126">Para obter detalhes, consulte [verificando a replicação de esquema do Active Directory no Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ef4c5-126">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="ef4c5-127">Usar cmdlets para preparar o esquema da floresta atual</span><span class="sxs-lookup"><span data-stu-id="ef4c5-127">To use cmdlets to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="ef4c5-128">Faça logon em um computador na floresta como membro do grupo Administradores de esquemas e com direitos de administrador no mestre de esquema.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-128">Log on to a computer in the forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="ef4c5-129">Instale os componentes principais do Lync Server da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="ef4c5-129">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="ef4c5-130">Na pasta de instalação ou mídia do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-130">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="ef4c5-131">Se você for solicitado a instalar o Microsoft Visual C++ Redistributable, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-131">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="ef4c5-132">A caixa de diálogo instalação do Lync Server 2013 solicita um local para instalar os arquivos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-132">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="ef4c5-133">Escolha o local padrão ou **navegue** até um local de sua escolha e clique em **instalar**.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-133">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="ef4c5-134">Na página contrato de licença, marque **a opção aceito os termos do contrato de licença**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-134">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="ef4c5-135">O instalador instala os componentes principais do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-135">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="ef4c5-136">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="ef4c5-137">Execute:</span><span class="sxs-lookup"><span data-stu-id="ef4c5-137">Run:</span></span>
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    <span data-ttu-id="ef4c5-138">Se você não especificar o parâmetro ldf, o valor padrão será o caminho de instalação do Lync Server 2013 lido do registro.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-138">If you do not specify the Ldf parameter, the default value is the Lync Server 2013 installation path that is read from the registry.</span></span>
    
    <span data-ttu-id="ef4c5-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ef4c5-139">For example:</span></span>
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  <span data-ttu-id="ef4c5-140">Use o cmdlet a seguir para verificar se a conclusão da preparação do esquema foi concluída.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-140">Use the following cmdlet to verify that schema preparation ran to completion.</span></span>
    
        Get-CsAdServerSchema 
    
    <span data-ttu-id="ef4c5-141">Esse cmdlet retorna um valor de **estado\_\_de\_versão do esquema atual** se a preparação do esquema foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-141">This cmdlet returns a value of **SCHEMA\_VERSION\_STATE\_CURRENT** if schema preparation was successful.</span></span>

6.  <span data-ttu-id="ef4c5-142">Aguarde a conclusão da replicação do Active Directory ou force a replicação.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-142">Wait for Active Directory replication to complete or force replication.</span></span>

7.  <span data-ttu-id="ef4c5-143">Verifique manualmente se as alterações de esquema foram duplicadas para todos os outros controladores de domínio.</span><span class="sxs-lookup"><span data-stu-id="ef4c5-143">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="ef4c5-144">Para obter detalhes, consulte [verificando a replicação de esquema do Active Directory no Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="ef4c5-144">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ef4c5-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="ef4c5-145">See Also</span></span>


[<span data-ttu-id="ef4c5-146">Verificando a replicação de esquema do Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef4c5-146">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)  


[<span data-ttu-id="ef4c5-147">Preparando o esquema do Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef4c5-147">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

