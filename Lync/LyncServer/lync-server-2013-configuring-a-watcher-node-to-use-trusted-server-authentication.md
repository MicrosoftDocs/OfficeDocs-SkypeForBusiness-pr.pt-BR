---
title: Configurando um nó de inspetor para usar a autenticação de servidor confiável
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6634fa55424190d2e0a05aece38d88977d2f6bca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a><span data-ttu-id="22e52-102">Configurando um nó de Inspetor no Lync Server 2013 para usar a autenticação de servidor confiável</span><span class="sxs-lookup"><span data-stu-id="22e52-102">Configuring a watcher node in Lync Server 2013 to use Trusted Server authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22e52-103">_**Tópico da última modificação:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="22e52-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="22e52-104">Se o seu computador do nó do Inspetor estiver dentro da rede de perímetro, o uso da autenticação de servidor confiável pode reduzir significativamente os impostos da administração para manter um único certificado em vez de várias senhas de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="22e52-104">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration taxes to maintaining a single certificate rather than numerous user account passwords.</span></span>

<span data-ttu-id="22e52-105">A primeira etapa na configuração da autenticação do servidor confiável é criar um pool de aplicativos confiável para hospedar o computador do nó do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="22e52-105">The first step in configuring Trusted Server authentication is to create a trusted application pool to host the watcher node computer.</span></span> <span data-ttu-id="22e52-106">Após a criação do pool de aplicativos confiáveis, você deve configurar transações sintéticas nesse nó do inspetor para executar como um aplicativo confiável.</span><span class="sxs-lookup"><span data-stu-id="22e52-106">After the trusted application pool has been created, you must then configure synthetic transactions on that watcher node to run as a trusted application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="22e52-107">Um aplicativo confiável é um aplicativo que recebe status confiável para ser executado como parte do Lync Server 2013, mas que não é uma parte interna do produto.</span><span class="sxs-lookup"><span data-stu-id="22e52-107">A trusted application is an application that is given trusted status to run as part of Lync Server 2013, but that is not a built-in part of the product.</span></span> <span data-ttu-id="22e52-108">O status de confiável significa que o aplicativo não será desafiado para autenticação toda vez que executar.</span><span class="sxs-lookup"><span data-stu-id="22e52-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>



</div>

<span data-ttu-id="22e52-109">Para criar um pool de aplicativos confiável, abra o Shell de gerenciamento do Lync Server 2013 e execute um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="22e52-109">To create a trusted application pool, open the Lync Server 2013 Management Shell and run a command similar to this:</span></span>

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> <span data-ttu-id="22e52-110">Para obter detalhes sobre os parâmetros usados no comando anterior, digite o seguinte no prompt do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="22e52-110">For details about the parameters used in the preceding command, type the following at the Lync Server Management Shell prompt:</span></span><BR><span data-ttu-id="22e52-111">Get-Help New-CsTrustedApplicationPool-Full | Saiba</span><span class="sxs-lookup"><span data-stu-id="22e52-111">Get-Help New-CsTrustedApplicationPool -Full | more</span></span>



</div>

<span data-ttu-id="22e52-112">Depois de criar o pool de aplicativos confiável, configure o computador do nó do inspetor para executar transações sintéticas como um aplicativo confiável.</span><span class="sxs-lookup"><span data-stu-id="22e52-112">After creating the trusted application pool, configure the watcher node computer to run synthetic transactions as a trusted application.</span></span> <span data-ttu-id="22e52-113">Isso é feito usando-se o cmdlet **New-CsTrustedApplication** e um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="22e52-113">This is done by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

<span data-ttu-id="22e52-114">Quando o comando anterior for concluído e o aplicativo confiável tiver sido criado, execute Enable-CsTopology para garantir que as alterações entrem em vigor:</span><span class="sxs-lookup"><span data-stu-id="22e52-114">When the preceding command completes and the trusted application has been created, run Enable-CsTopology to make sure that the changes take effect:</span></span>

    Enable-CsTopology

<span data-ttu-id="22e52-115">Depois de executar o Enable-CsTopology, recomendamos reiniciar o computador.</span><span class="sxs-lookup"><span data-stu-id="22e52-115">After running Enable-CsTopology, we recommend that you restart the computer.</span></span>

<span data-ttu-id="22e52-116">Para verificar se o novo aplicativo confiável foi criado, digite o seguinte no prompt do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="22e52-116">To verify that the new trusted application has been created, type the following at the Lync Server Management Shell prompt:</span></span>

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="22e52-117">Configurando um certificado padrão no nó Inspetor</span><span class="sxs-lookup"><span data-stu-id="22e52-117">Configuring a Default Certificate on the Watcher Node</span></span>

<span data-ttu-id="22e52-118">Cada nó do Inspetor deve ter um certificado padrão atribuído usando o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22e52-118">Each watcher node must have a Default certificate assigned by using the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="22e52-119">**Para atribuir um certificado padrão**</span><span class="sxs-lookup"><span data-stu-id="22e52-119">**To assign a Default certificate**</span></span>

1.  <span data-ttu-id="22e52-120">Clique em **Iniciar**, em **todos os programas**, em **Lync Server**e em **Assistente de implantação do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="22e52-120">Click **Start**, click **All Programs**, click **Lync Server**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="22e52-121">No assistente de implantação do Lync Server, clique em **instalar ou atualizar o sistema do Lync Server** e, em seguida, clique em **executar** sob a solicitação de título **, instalar ou atribuir certificado**.</span><span class="sxs-lookup"><span data-stu-id="22e52-121">In the Lync Server Deployment Wizard, click **Install or Update Lync Server System** and then click **Run** under the heading **Request, Install, or Assign Certificate**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="22e52-122">Se o botão <STRONG>executar</STRONG> estiver desabilitado, talvez seja necessário clicar primeiro em <STRONG>executar</STRONG> em <STRONG>instalar repositório de configuração local</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="22e52-122">If the <STRONG>Run</STRONG> button is disabled, you may need to first click <STRONG>Run</STRONG> under <STRONG>Install Local Configuration Store</STRONG>.</span></span>

    
    </div>

3.  <span data-ttu-id="22e52-123">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="22e52-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="22e52-124">Se você já tiver um certificado que pode ser usado como o certificado padrão, clique em **padrão** no assistente de certificado e clique em **atribuir**.</span><span class="sxs-lookup"><span data-stu-id="22e52-124">If you already have a certificate that can be used as the Default certificate, click **Default** in the Certificate wizard and then click **Assign**.</span></span> <span data-ttu-id="22e52-125">Siga as etapas no assistente de Atribuição de Certificado para atribuí-lo.</span><span class="sxs-lookup"><span data-stu-id="22e52-125">Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
      - <span data-ttu-id="22e52-126">Se você precisar solicitar um certificado para usar o certificado padrão, clique em **solicitar** e siga as etapas no Assistente para solicitação de certificados para solicitar esse certificado.</span><span class="sxs-lookup"><span data-stu-id="22e52-126">If you need to request a certificate for use the Default certificate, click **Request** and then follow the steps in the Certificate Request wizard to request that certificate.</span></span> <span data-ttu-id="22e52-127">Se você utilizar valores padrão para o certificado de Servidor da Web, você terá um certificado que pode ser atribuído como certificado padrão.</span><span class="sxs-lookup"><span data-stu-id="22e52-127">If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a><span data-ttu-id="22e52-128">Instalando e configurando um nó de Inspetor</span><span class="sxs-lookup"><span data-stu-id="22e52-128">Installing and Configuring a Watcher Node</span></span>

<span data-ttu-id="22e52-129">Depois de reiniciar o computador do nó do Inspetor e configurar um certificado, você precisará executar o arquivo Watchernode. msi.</span><span class="sxs-lookup"><span data-stu-id="22e52-129">After you have restarted the watcher node computer and configured a certificate, you need to run the file Watchernode.msi.</span></span> <span data-ttu-id="22e52-130">(Você deve executar o Watchernode. msi em um computador onde os arquivos de agente do Operations Manager e os componentes principais do Lync Server 2013 estejam instalados.)</span><span class="sxs-lookup"><span data-stu-id="22e52-130">(You must run Watchernode.msi on a computer where both the Operations Manager agent files and the Lync Server 2013 core components are installed.)</span></span>

<span data-ttu-id="22e52-131">**Para instalar e configurar um nó de Inspetor**</span><span class="sxs-lookup"><span data-stu-id="22e52-131">**To install and configure a watcher node**</span></span>

1.  <span data-ttu-id="22e52-132">Para abrir o Shell de gerenciamento do Lync Server, clique em **Iniciar**, em **todos os programas**, em **Lync Server**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="22e52-132">Open the Lync Server Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server**, and then clicking **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="22e52-133">No Shell de gerenciamento do Lync Server, digite o seguinte comando e pressione ENTER (especificar o caminho real para a sua cópia do Watchernode. msi):</span><span class="sxs-lookup"><span data-stu-id="22e52-133">In the Lync Server Management Shell, type the following command and then press ENTER (specify the actual path to your copy of Watchernode.msi):</span></span>
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="22e52-134">Você também pode executar o Watchernode. msi a partir de uma janela de comando.</span><span class="sxs-lookup"><span data-stu-id="22e52-134">You can also run Watchernode.msi from a command window.</span></span> <span data-ttu-id="22e52-135">Para abrir uma janela de comando, clique em <STRONG>Iniciar</STRONG>, clique com o botão direito do mouse em <STRONG>Prompt de Comando</STRONG> e clique em <STRONG>Executar como administrador</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="22e52-135">To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>.</span></span> <span data-ttu-id="22e52-136">Quando a janela de comando abrir, digite o mesmo comando anterior.</span><span class="sxs-lookup"><span data-stu-id="22e52-136">When the command window opens, type the same preceding command.</span></span>

    
    </div>

<span data-ttu-id="22e52-137">Observe que o par nome/valor no comando anterior Authentication = TrustedServer diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="22e52-137">Note that the name/value pair in the preceding command Authentication=TrustedServer is case-sensitive.</span></span> <span data-ttu-id="22e52-138">Você deve digitá-lo exatamente como mostrado.</span><span class="sxs-lookup"><span data-stu-id="22e52-138">You must type it exactly as shown.</span></span> <span data-ttu-id="22e52-139">O comando a seguir falha porque não usa a capitalização de letras correta:</span><span class="sxs-lookup"><span data-stu-id="22e52-139">The following command fails because it does not use the correct letter casing:</span></span>

<span data-ttu-id="22e52-140">C:\\ferramentas\\Watchernode. msi Authentication = trustedserver</span><span class="sxs-lookup"><span data-stu-id="22e52-140">C:\\Tools\\Watchernode.msi authentication=trustedserver</span></span>

<span data-ttu-id="22e52-141">Você pode usar o modo TrustedServer somente com computadores localizados na rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="22e52-141">You can use TrustedServer mode only with computers that are located within the perimeter network.</span></span> <span data-ttu-id="22e52-142">Quando um nó do inspetor está em execução no modo TrustedServer, os administradores não precisam manter as senhas dos usuários do teste no computador.</span><span class="sxs-lookup"><span data-stu-id="22e52-142">When a watcher node is running in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

