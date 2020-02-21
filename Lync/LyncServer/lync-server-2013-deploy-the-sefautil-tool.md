---
title: 'Lync Server 2013: implantar a ferramenta SEFAUtil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c37108d8429567c2653174e4d5a9d0510278e4f3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a><span data-ttu-id="d6bf3-102">Implantar a ferramenta SEFAUtil no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6bf3-102">Deploy the SEFAUtil tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6bf3-103">_**Última modificação do tópico:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="d6bf3-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="d6bf3-104">Para implantar e gerenciar o recebimento de chamadas em grupo, você precisa usar a ferramenta SEFAUtil Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-104">To deploy and manage Group Call Pickup, you need to use the SEFAUtil resource kit tool.</span></span> <span data-ttu-id="d6bf3-105">A ferramenta faz parte das ferramentas do Lync Server 2013 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-105">The tool is part of the Lync Server 2013 resource kit tools.</span></span> <span data-ttu-id="d6bf3-106">Antes de instalar o SEFAUtil, você deve ter um pool de aplicativos confiáveis em sua topologia, especificar SEFAUtil como um aplicativo confiável e habilitar a topologia.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-106">Before you can install SEFAUtil, you must have a trusted application pool in your topology, specify SEFAUtil as a trusted application, and enable the topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d6bf3-107">Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK deve ser instalado em qualquer computador no qual você planeja executar a ferramenta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-107">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span>



</div>

<span data-ttu-id="d6bf3-108">Você pode executar o SEFAUtil em qualquer pool de front-ends em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-108">You can run the SEFAUtil in any Front End pool in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6bf3-109">Para obter mais detalhes sobre a execução do SEFAUtil, consulte o artigo do blog da TechNet, "How to Get SEFAutil Running?"</span><span class="sxs-lookup"><span data-stu-id="d6bf3-109">For more details about running SEFAUtil, see the Technet blog article, "How to get SEFAutil running?"</span></span> <span data-ttu-id="d6bf3-110">em <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A>.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-110">at <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A>.</span></span>



</div>

<div>

## <a name="to-deploy-sefautil"></a><span data-ttu-id="d6bf3-111">Para implantar o SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="d6bf3-111">To deploy SEFAUtil</span></span>

1.  <span data-ttu-id="d6bf3-112">Faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d6bf3-112">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d6bf3-113">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d6bf3-114">A ferramenta SEFAUtil pode ser executada apenas em um computador que faça parte de um pool de aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-114">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="d6bf3-115">Se necessário, defina um pool de aplicativos confiáveis para o pool de front-ends onde você planeja executar o SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-115">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="d6bf3-116">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="d6bf3-116">At the command line, run:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  <span data-ttu-id="d6bf3-117">Defina a ferramenta SEFAUtil como um aplicativo confiável.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-117">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="d6bf3-118">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="d6bf3-118">At the command line, run:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d6bf3-119">Você pode usar uma porta diferente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-119">You can use a different port if needed.</span></span>

    
    </div>

5.  <span data-ttu-id="d6bf3-120">Habilite a topologia com suas alterações.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-120">Enable the topology with your changes.</span></span> <span data-ttu-id="d6bf3-121">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="d6bf3-121">At the command line, run:</span></span>
    
        Enable-CsTopology

6.  <span data-ttu-id="d6bf3-122">Instale as ferramentas do kit de recursos do Lync Server 2013 em um servidor front-end que esteja no pool de aplicativos confiáveis que você criou na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-122">Install the Lync Server 2013 resource kit tools on a Front End Server that is in the trusted application pool that you created in step 3.</span></span>

7.  <span data-ttu-id="d6bf3-123">Verifique se a ferramenta SEFAUtil está funcionando corretamente, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d6bf3-123">Verify that the SEFAUtil tool is running correctly, as follows:</span></span>
    
    1.  <span data-ttu-id="d6bf3-124">Execute a ferramenta a partir do prompt de comando do Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamadas de um usuário em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-124">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d6bf3-125">A ferramenta está localizada em \Program Files\Microsoft Lync Server 2013 \ reskit.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-125">The tool is located at \Program Files\Microsoft Lync Server 2013\Reskit.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="d6bf3-126">Exibir as configurações de encaminhamento de chamadas de um usuário.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-126">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="d6bf3-127">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="d6bf3-127">At the command line, run:</span></span>
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        <span data-ttu-id="d6bf3-128">As configurações de encaminhamento de chamadas para o usuário serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="d6bf3-128">The call forwarding settings for the user will be displayed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

