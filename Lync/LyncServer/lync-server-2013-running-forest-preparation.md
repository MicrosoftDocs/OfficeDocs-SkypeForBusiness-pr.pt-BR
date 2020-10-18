---
title: 'Lync Server 2013: executando preparação da floresta'
description: 'Lync Server 2013: executando a preparação da floresta.'
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
ms.openlocfilehash: ad3ef2d7583d541701d6606946ca1df1bbd8cf23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577757"
---
# <a name="running-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="20ba0-103">Executando a preparação da floresta para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20ba0-103">Running forest preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20ba0-104">_**Última modificação do tópico:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="20ba0-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="20ba0-105">Você pode usar os cmdlets de instalação ou do Shell de gerenciamento do Lync Server para preparar a floresta.</span><span class="sxs-lookup"><span data-stu-id="20ba0-105">You can use Setup or Lync Server Management Shell cmdlets to prepare the forest.</span></span> <span data-ttu-id="20ba0-106">O cmdlet que prepara a floresta é **Enable-CsAdForest**.</span><span class="sxs-lookup"><span data-stu-id="20ba0-106">The cmdlet that prepares the forest is **Enable-CsAdForest**.</span></span>

<span data-ttu-id="20ba0-107">Depois de preparar a floresta, você deverá verificar se as configurações globais foram replicadas antes de executar a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="20ba0-107">After you prepare the forest, you must verify that global settings have been replicated before running domain preparation.</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a><span data-ttu-id="20ba0-108">Para usar a Instalação para preparar a floresta</span><span class="sxs-lookup"><span data-stu-id="20ba0-108">To use Setup to prepare the forest</span></span>

1.  <span data-ttu-id="20ba0-109">Faça logon em um computador que seja parte de um domínio como membro do grupo Administradores de Empresa para o domínio raiz da floresta.</span><span class="sxs-lookup"><span data-stu-id="20ba0-109">Log on to a computer that is joined to a domain as a member of the Enterprise Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="20ba0-110">Na pasta ou mídia de instalação do Lync Server 2013, execute Setup.exe para iniciar o assistente de implantação.</span><span class="sxs-lookup"><span data-stu-id="20ba0-110">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="20ba0-111">Clique em **Preparar o Active Directory** e espere que o estado da implantação seja determinado.</span><span class="sxs-lookup"><span data-stu-id="20ba0-111">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="20ba0-112">Na **Etapa 3: Preparar Floresta Atual**, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="20ba0-112">At **Step 3: Prepare Current Forest**, click **Run**.</span></span>

5.  <span data-ttu-id="20ba0-113">Na página **Preparar Floresta**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="20ba0-113">On the **Prepare Forest** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="20ba0-114">A preparação da floresta permite que você escolha onde colocar os grupos universais para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="20ba0-114">Forest Preparation allows you to choose where to place the Universal Groups for Lync Server 2013.</span></span> <span data-ttu-id="20ba0-115">Escolha o local consistente com as exigências de sua organização.</span><span class="sxs-lookup"><span data-stu-id="20ba0-115">Choose a location that is consistent with the requirements of your organization.</span></span>

    
    </div>

6.  <span data-ttu-id="20ba0-116">Na página **Executando Comandos**, procure por **Status da tarefa: concluída** e clique em **Exibir Log**.</span><span class="sxs-lookup"><span data-stu-id="20ba0-116">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="20ba0-117">Na coluna **ação** , expanda **Forest prep**, procure um **\<Success\>** resultado de execução ao final de cada tarefa para verificar se a preparação da floresta foi concluída com êxito, feche o log e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="20ba0-117">Under the **Action** column, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="20ba0-p103">Aguarde a replicação do Active Directory ser concluída ou force a replicação em todos os controladores de domínio listados no snap-in **Sites e Serviços do Active Directory** no controlador de domínio raiz da floresta, antes de executar a preparação do domínio. Force a replicação entre os controladores de domínio em todos os sites do Active Directory para que a replicação nos sites ocorra dentro de alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="20ba0-p103">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation. Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a><span data-ttu-id="20ba0-120">Para usar os cmdlets para preparar a floresta</span><span class="sxs-lookup"><span data-stu-id="20ba0-120">To use cmdlets to prepare the forest</span></span>

1.  <span data-ttu-id="20ba0-121">Faça logon em um computador que ingressou em um domínio como membro do grupo Admins. do Domínio no domínio raiz da floresta.</span><span class="sxs-lookup"><span data-stu-id="20ba0-121">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="20ba0-122">Instale os componentes principais do Lync Server da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="20ba0-122">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="20ba0-123">Na pasta ou mídia de instalação do Lync Server 2013, execute Setup.exe para iniciar o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20ba0-123">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="20ba0-124">Se for solicitado que você instale o Microsoft Visual C++ Redistributable, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="20ba0-124">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="20ba0-125">A caixa de diálogo instalação do Lync Server 2013 solicita um local para instalar os arquivos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20ba0-125">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="20ba0-126">Escolha o local padrão ou **Procure** um local de sua escolha e clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="20ba0-126">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="20ba0-127">Na página Contrato de Licença, marque **Aceito os termos do contrato de licença** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="20ba0-127">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="20ba0-128">O instalador instala os componentes principais do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="20ba0-128">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="20ba0-129">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="20ba0-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="20ba0-130">Sejam</span><span class="sxs-lookup"><span data-stu-id="20ba0-130">Run:</span></span>
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    <span data-ttu-id="20ba0-131">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="20ba0-131">For example:</span></span>
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    <span data-ttu-id="20ba0-p106">Se você não especificar o parâmetro GroupDomain, o valor padrão será o domínio local. Se grupos universais tiverem sido criados anteriormente em um domínio que não seja o domínio padrão, será necessário especificar explicitamente o parâmetro GroupDomain.</span><span class="sxs-lookup"><span data-stu-id="20ba0-p106">If you do not specify the GroupDomain parameter, the default value is the local domain. If universal groups were created previously in a domain that is not the default domain, you must specify the GroupDomain parameter explicitly.</span></span>

5.  <span data-ttu-id="20ba0-134">Aguarde a replicação do Active Directory ser concluída ou force a replicação em todos os controladores de domínio listados no snap-in **Sites e Serviços do Active Directory** no controlador de domínio raiz da floresta, antes de executar a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="20ba0-134">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span>

6.  <span data-ttu-id="20ba0-p107">Verificar se a preparação da floresta teve êxito. Execute:</span><span class="sxs-lookup"><span data-stu-id="20ba0-p107">Verify that forest preparation was successful. Run:</span></span>
    
        Get-CsAdForest 
    
    <span data-ttu-id="20ba0-137">Este cmdlet retorna um valor de \*\* \_ FORESTSETTINGS do \_ estado \_ da LC pronto\*\* se a preparação da floresta tiver sido bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="20ba0-137">This cmdlet returns a value of **LC\_FORESTSETTINGS\_STATE\_READY** if forest preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="20ba0-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="20ba0-138">See Also</span></span>


[<span data-ttu-id="20ba0-139">Usando cmdlets para reverter a preparação da floresta para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20ba0-139">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[<span data-ttu-id="20ba0-140">Preparando a floresta para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20ba0-140">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

