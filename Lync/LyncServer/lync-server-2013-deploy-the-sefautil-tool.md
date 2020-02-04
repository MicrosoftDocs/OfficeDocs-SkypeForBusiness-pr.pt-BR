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
ms.openlocfilehash: dcd995a99514fa54a221e17f1ea556565cbebdcb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a><span data-ttu-id="ad227-102">Deploy the SEFAUtil tool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad227-102">Deploy the SEFAUtil tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad227-103">_**Tópico da última modificação:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="ad227-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="ad227-104">Para implantar e gerenciar o recebimento de chamadas em grupo, você precisa usar a ferramenta kit de recursos do SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="ad227-104">To deploy and manage Group Call Pickup, you need to use the SEFAUtil resource kit tool.</span></span> <span data-ttu-id="ad227-105">A ferramenta faz parte das ferramentas do Lync Server 2013 Resource Kit.</span><span class="sxs-lookup"><span data-stu-id="ad227-105">The tool is part of the Lync Server 2013 resource kit tools.</span></span> <span data-ttu-id="ad227-106">Antes de poder instalar o SEFAUtil, você deve ter um pool de aplicativos confiável na sua topologia, especificar SEFAUtil como um aplicativo confiável e habilitar a topologia.</span><span class="sxs-lookup"><span data-stu-id="ad227-106">Before you can install SEFAUtil, you must have a trusted application pool in your topology, specify SEFAUtil as a trusted application, and enable the topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ad227-107">O Microsoft UCMA (Unified Communications Managed API) 3.0 Core SDK deve estar instalado em qualquer computador no qual você planeja executar a ferramenta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="ad227-107">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span>



</div>

<span data-ttu-id="ad227-108">Você pode executar o SEFAUtil em qualquer pool de front-ends na sua implantação.</span><span class="sxs-lookup"><span data-stu-id="ad227-108">You can run the SEFAUtil in any Front End pool in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad227-109">Para obter mais detalhes sobre como executar o SEFAUtil, consulte o artigo do blog do TechNet "como fazer SEFAutil executar?"</span><span class="sxs-lookup"><span data-stu-id="ad227-109">For more details about running SEFAUtil, see the Technet blog article, "How to get SEFAutil running?"</span></span> <span data-ttu-id="ad227-110">em <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>.</span><span class="sxs-lookup"><span data-stu-id="ad227-110">at <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>.</span></span>



</div>

<div>

## <a name="to-deploy-sefautil"></a><span data-ttu-id="ad227-111">Para implantar a SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="ad227-111">To deploy SEFAUtil</span></span>

1.  <span data-ttu-id="ad227-112">Faça logon no computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [permissões de configuração de representante no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ad227-112">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ad227-113">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ad227-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ad227-114">A ferramenta SEFAUtil só pode ser executada em um computador que integra um pool de aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="ad227-114">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="ad227-115">Se necessário, defina um pool de aplicativos confiável para o pool de front-ends em que você planeja executar o SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="ad227-115">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="ad227-116">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="ad227-116">At the command line, run:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  <span data-ttu-id="ad227-p104">Defina a ferramenta SEFAUtil como um aplicativo confiável. Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="ad227-p104">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ad227-119">Se necessário, você pode usar uma porta diferente.</span><span class="sxs-lookup"><span data-stu-id="ad227-119">You can use a different port if needed.</span></span>

    
    </div>

5.  <span data-ttu-id="ad227-p105">Habilite a topologia com suas alterações. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="ad227-p105">Enable the topology with your changes. At the command line, run:</span></span>
    
        Enable-CsTopology

6.  <span data-ttu-id="ad227-122">Instale as ferramentas do Lync Server 2013 Resource Kit em um servidor front-end que está no pool de aplicativos confiáveis que você criou na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="ad227-122">Install the Lync Server 2013 resource kit tools on a Front End Server that is in the trusted application pool that you created in step 3.</span></span>

7.  <span data-ttu-id="ad227-123">Verifique se a ferramenta SEFAUtil está sendo executada corretamente conforme segue:</span><span class="sxs-lookup"><span data-stu-id="ad227-123">Verify that the SEFAUtil tool is running correctly, as follows:</span></span>
    
    1.  <span data-ttu-id="ad227-124">Execute a ferramenta no prompt de comando do Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamada de um usuário de sua implantação.</span><span class="sxs-lookup"><span data-stu-id="ad227-124">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ad227-125">A ferramenta está localizada em \Arquivos de Programas\microsoft Lync Server 2013 \ reskit.</span><span class="sxs-lookup"><span data-stu-id="ad227-125">The tool is located at \Program Files\Microsoft Lync Server 2013\Reskit.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="ad227-p106">Exiba as configurações de encaminhamento de chamada de um usuário, Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="ad227-p106">Display the call forwarding settings of a user. At the command line, run:</span></span>
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        <span data-ttu-id="ad227-128">As configurações de encaminhamento de chamada do usuário serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="ad227-128">The call forwarding settings for the user will be displayed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

