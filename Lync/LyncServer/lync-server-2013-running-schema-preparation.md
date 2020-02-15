---
title: 'Lync Server 2013: executando a preparação do esquema'
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
ms.openlocfilehash: c58f50cb5c4668525450c4aa95b4a00513d5fc17
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a><span data-ttu-id="9f89c-102">Executando a preparação do esquema do Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f89c-102">Running Active Directory schema preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f89c-103">_**Última modificação do tópico:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="9f89c-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="9f89c-104">Você pode usar os cmdlets de instalação ou do Shell de gerenciamento do Lync Server para preparar o esquema do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9f89c-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the Active Directory schema.</span></span> <span data-ttu-id="9f89c-105">O cmdlet que estende o esquema do Active Directory é **Install-CsAdServerSchema**.</span><span class="sxs-lookup"><span data-stu-id="9f89c-105">The cmdlet that extends the Active Directory schema is **Install-CsAdServerSchema**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9f89c-106">O cmdlet de preparação do esquema (<STRONG>Install-CsAdServerSchema</STRONG>) deve acessar o mestre de esquema, que exige que o serviço registro remoto esteja em execução e que a chave do registro remoto esteja habilitada.</span><span class="sxs-lookup"><span data-stu-id="9f89c-106">The schema preparation cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) must access the schema master, which requires that the remote registry service is running and that the remote registry key is enabled.</span></span> <span data-ttu-id="9f89c-107">Se o serviço registro remoto não puder ser habilitado no mestre de esquema, você pode executar o cmdlet localmente no mestre de esquema.</span><span class="sxs-lookup"><span data-stu-id="9f89c-107">If the remote registry service cannot be enabled on the schema master, you can run the cmdlet locally on the schema master.</span></span> <span data-ttu-id="9f89c-108">Para obter detalhes sobre o acesso remoto do registro, consulte o artigo 314837 da base de dados de conhecimento da Microsoft, "como gerenciar <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>o acesso remoto ao registro" em.</span><span class="sxs-lookup"><span data-stu-id="9f89c-108">For details about registry remote access, see Microsoft Knowledge Base article 314837, "How to Manage Remote Access to the Registry," at <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span></span>



</div>

<span data-ttu-id="9f89c-109">Após a conclusão da preparação do esquema, verifique manualmente se a partição do esquema foi replicada antes de prosseguir para a preparação da floresta.</span><span class="sxs-lookup"><span data-stu-id="9f89c-109">After you complete schema preparation, manually verify that the schema partition has been replicated before proceeding to forest preparation.</span></span> <span data-ttu-id="9f89c-110">Para obter detalhes, consulte [Verifying Active Directory Schema Replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="9f89c-110">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="9f89c-111">Para usar a Instalação para preparar o esquema da floresta atual</span><span class="sxs-lookup"><span data-stu-id="9f89c-111">To use Setup to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="9f89c-112">Faça logon em um servidor em sua floresta como membro do grupo Administradores de Esquema e com direitos de administrador no mestre de esquema.</span><span class="sxs-lookup"><span data-stu-id="9f89c-112">Log on to a server in your forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="9f89c-113">Na pasta ou mídia de instalação do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação.</span><span class="sxs-lookup"><span data-stu-id="9f89c-113">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="9f89c-114">Se for solicitado que você instale o Microsoft Visual C++ Redistributable, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="9f89c-114">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>

4.  <span data-ttu-id="9f89c-115">A caixa de diálogo instalação do Lync Server 2013 solicita um local para instalar os arquivos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f89c-115">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="9f89c-116">Escolha o local padrão ou **Procure** um local de sua escolha e clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="9f89c-116">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>

5.  <span data-ttu-id="9f89c-117">Na página Contrato de Licença, marque **Aceito os termos do contrato de licença** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f89c-117">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span>

6.  <span data-ttu-id="9f89c-118">O instalador instala os componentes principais do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f89c-118">The installer installs the Lync Server Core Components.</span></span>

7.  <span data-ttu-id="9f89c-119">Quando o Assistente de Implantação estiver pronto, clique em **Preparar Active Directory** e espere que o estado da implantação seja determinado.</span><span class="sxs-lookup"><span data-stu-id="9f89c-119">When the Deployment Wizard is ready, click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

8.  <span data-ttu-id="9f89c-120">Na **Etapa 1: Preparar Esquema**, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="9f89c-120">At **Step 1: Prepare Schema**, click **Run**.</span></span>

9.  <span data-ttu-id="9f89c-121">Na página **Preparar Esquema**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9f89c-121">On the **Prepare Schema** page, click **Next**.</span></span>

10. <span data-ttu-id="9f89c-122">Na página **Executando Comandos**, procure **Status da tarefa: Concluída** e clique em **Exibir Log**.</span><span class="sxs-lookup"><span data-stu-id="9f89c-122">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

11. <span data-ttu-id="9f89c-123">Na coluna **ação** , expanda **esquema Prep**, procure o \*\* \<\> \*\* resultado de execução de êxito no final de cada tarefa para verificar se a preparação do esquema foi concluída com êxito, feche o log e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="9f89c-123">Under the **Action** column, expand **Schema Prep**, look for the **\<Success\>** Execution Result at the end of each task to verify that schema preparation completed successfully, close the log, and then click **Finish**.</span></span>

12. <span data-ttu-id="9f89c-124">Aguarde a replicação do Active Directory ser concluída ou force a replicação.</span><span class="sxs-lookup"><span data-stu-id="9f89c-124">Wait for Active Directory replication to complete or force replication.</span></span>

13. <span data-ttu-id="9f89c-125">Verifique manualmente se as alterações do esquema foram replicadas para todos os outros controladores de domínio.</span><span class="sxs-lookup"><span data-stu-id="9f89c-125">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="9f89c-126">Para obter detalhes, consulte [Verifying Active Directory Schema Replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="9f89c-126">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="9f89c-127">Para usar cmdlets para preparar o esquema da floresta atual</span><span class="sxs-lookup"><span data-stu-id="9f89c-127">To use cmdlets to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="9f89c-128">Faça logon em um computador na floresta como um membro do grupo Administradores de Esquemas e com direitos de administrador no mestre de esquema.</span><span class="sxs-lookup"><span data-stu-id="9f89c-128">Log on to a computer in the forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="9f89c-129">Instale os componentes principais do Lync Server da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9f89c-129">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="9f89c-130">Na pasta ou mídia de instalação do Lync Server 2013, execute Setup. exe para iniciar o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f89c-130">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="9f89c-131">Se for solicitado que você instale o Microsoft Visual C++ Redistributable, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="9f89c-131">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="9f89c-132">A caixa de diálogo instalação do Lync Server 2013 solicita um local para instalar os arquivos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f89c-132">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="9f89c-133">Escolha o local padrão ou **Procure** um local de sua escolha e clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="9f89c-133">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="9f89c-134">Na página Contrato de Licença, marque **Aceito os termos do contrato de licença** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f89c-134">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="9f89c-135">O instalador instala os componentes principais do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9f89c-135">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="9f89c-136">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9f89c-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="9f89c-137">Sejam</span><span class="sxs-lookup"><span data-stu-id="9f89c-137">Run:</span></span>
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    <span data-ttu-id="9f89c-138">Se você não especificar o parâmetro ldf, o valor padrão será o caminho de instalação do Lync Server 2013 que é lido a partir do registro.</span><span class="sxs-lookup"><span data-stu-id="9f89c-138">If you do not specify the Ldf parameter, the default value is the Lync Server 2013 installation path that is read from the registry.</span></span>
    
    <span data-ttu-id="9f89c-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9f89c-139">For example:</span></span>
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  <span data-ttu-id="9f89c-140">Use o cmdlet a seguir para verificar se a preparação do esquema foi executada até o final.</span><span class="sxs-lookup"><span data-stu-id="9f89c-140">Use the following cmdlet to verify that schema preparation ran to completion.</span></span>
    
        Get-CsAdServerSchema 
    
    <span data-ttu-id="9f89c-141">Este cmdlet retorna um valor de **estado\_\_de\_versão do esquema atual** se a preparação do esquema tiver sido bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="9f89c-141">This cmdlet returns a value of **SCHEMA\_VERSION\_STATE\_CURRENT** if schema preparation was successful.</span></span>

6.  <span data-ttu-id="9f89c-142">Aguarde a replicação do Active Directory ser concluída ou force a replicação.</span><span class="sxs-lookup"><span data-stu-id="9f89c-142">Wait for Active Directory replication to complete or force replication.</span></span>

7.  <span data-ttu-id="9f89c-143">Verifique manualmente se as alterações do esquema foram replicadas para todos os outros controladores de domínio.</span><span class="sxs-lookup"><span data-stu-id="9f89c-143">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="9f89c-144">Para obter detalhes, consulte [Verifying Active Directory Schema Replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span><span class="sxs-lookup"><span data-stu-id="9f89c-144">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9f89c-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="9f89c-145">See Also</span></span>


[<span data-ttu-id="9f89c-146">Verificando a replicação do esquema do Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f89c-146">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)  


[<span data-ttu-id="9f89c-147">Preparando o esquema do Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f89c-147">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

