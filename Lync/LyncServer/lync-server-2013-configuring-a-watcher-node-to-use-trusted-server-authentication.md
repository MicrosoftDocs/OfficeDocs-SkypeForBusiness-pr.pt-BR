---
title: Configurando um nó do inspetor para usar a autenticação de servidor confiável
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ba69980f97e901703f51f71729c661821e70e61
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a><span data-ttu-id="6bb00-102">Configurando um nó do Inspetor no Lync Server 2013 para usar a autenticação de servidor confiável</span><span class="sxs-lookup"><span data-stu-id="6bb00-102">Configuring a watcher node in Lync Server 2013 to use Trusted Server authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bb00-103">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="6bb00-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="6bb00-104">Caso o seu computador de nó do inspetor estiver dentro da rede de perímetro, utilizar uma autenticação de Servidor Confiável pode reduzir drasticamente as taxas de administração para manter um único certificado em vez de diversas senhas de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="6bb00-104">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration taxes to maintaining a single certificate rather than numerous user account passwords.</span></span>

<span data-ttu-id="6bb00-p101">A primeira etapa na configuração da autenticação de Servidor Confiável é criar um pool de aplicativo confiável para hospedar o computador de nó do inspetor. Depois que o pool de aplicativo confiável tiver sido criado, você deverá então configurar transações sintéticas nos nós do inspetor para executar como um aplicativo confiável.</span><span class="sxs-lookup"><span data-stu-id="6bb00-p101">The first step in configuring Trusted Server authentication is to create a trusted application pool to host the watcher node computer. After the trusted application pool has been created, you must then configure synthetic transactions on that watcher node to run as a trusted application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6bb00-107">Um aplicativo confiável é um aplicativo que recebe status confiável para ser executado como parte do Lync Server 2013, mas que não é uma parte interna do produto.</span><span class="sxs-lookup"><span data-stu-id="6bb00-107">A trusted application is an application that is given trusted status to run as part of Lync Server 2013, but that is not a built-in part of the product.</span></span> <span data-ttu-id="6bb00-108">O status de confiável significa que o aplicativo não será desafiado para autenticação toda vez que executar.</span><span class="sxs-lookup"><span data-stu-id="6bb00-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>



</div>

<span data-ttu-id="6bb00-109">Para criar um pool de aplicativos confiáveis, abra o Shell de gerenciamento do Lync Server 2013 e execute um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="6bb00-109">To create a trusted application pool, open the Lync Server 2013 Management Shell and run a command similar to this:</span></span>

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> <span data-ttu-id="6bb00-110">Para obter detalhes sobre os parâmetros usados no comando anterior, digite o seguinte no prompt do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="6bb00-110">For details about the parameters used in the preceding command, type the following at the Lync Server Management Shell prompt:</span></span><BR><span data-ttu-id="6bb00-111">Get-Help New-CsTrustedApplicationPool -Full | more</span><span class="sxs-lookup"><span data-stu-id="6bb00-111">Get-Help New-CsTrustedApplicationPool -Full | more</span></span>



</div>

<span data-ttu-id="6bb00-112">Após criar o pool de aplicativo confiável, configure o computador de nó do inspetor para executar transações sintéticas como aplicativo confiável.</span><span class="sxs-lookup"><span data-stu-id="6bb00-112">After creating the trusted application pool, configure the watcher node computer to run synthetic transactions as a trusted application.</span></span> <span data-ttu-id="6bb00-113">Isso é feito utilizando o cmdlet **New-CsTrustedApplication** e um comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="6bb00-113">This is done by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

<span data-ttu-id="6bb00-114">Quando o comando estiver concluído e o aplicativo confiável for criado, execute Enable-CsTopology para certificar-se de que as alterações tenham efeito:</span><span class="sxs-lookup"><span data-stu-id="6bb00-114">When the preceding command completes and the trusted application has been created, run Enable-CsTopology to make sure that the changes take effect:</span></span>

    Enable-CsTopology

<span data-ttu-id="6bb00-115">Após executar o Enable-CsTopology, recomendamos que você reinicie o computador.</span><span class="sxs-lookup"><span data-stu-id="6bb00-115">After running Enable-CsTopology, we recommend that you restart the computer.</span></span>

<span data-ttu-id="6bb00-116">Para verificar se o novo aplicativo confiável foi criado, digite o seguinte no prompt do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="6bb00-116">To verify that the new trusted application has been created, type the following at the Lync Server Management Shell prompt:</span></span>

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="6bb00-117">Configurando um certificado padrão no nó do inspetor</span><span class="sxs-lookup"><span data-stu-id="6bb00-117">Configuring a Default Certificate on the Watcher Node</span></span>

<span data-ttu-id="6bb00-118">Cada nó do Inspetor deve ter um certificado padrão atribuído usando o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6bb00-118">Each watcher node must have a Default certificate assigned by using the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="6bb00-119">**Para atribuir um certificado padrão**</span><span class="sxs-lookup"><span data-stu-id="6bb00-119">**To assign a Default certificate**</span></span>

1.  <span data-ttu-id="6bb00-120">Clique em **Iniciar**, em **todos os programas**, em **Lync Server**e em **Assistente de implantação do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6bb00-120">Click **Start**, click **All Programs**, click **Lync Server**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="6bb00-121">No assistente de implantação do Lync Server, clique em **instalar ou atualizar o sistema do Lync Server** e clique em **executar** no cabeçalho **solicitar, instalar ou atribuir certificado**.</span><span class="sxs-lookup"><span data-stu-id="6bb00-121">In the Lync Server Deployment Wizard, click **Install or Update Lync Server System** and then click **Run** under the heading **Request, Install, or Assign Certificate**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6bb00-122">Caso o botão <STRONG>Executar</STRONG> esteja inativo, talvez você precise clicar primeiro em <STRONG>Executar</STRONG>, sob <STRONG>Instalar Repositório de Configuração Local</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="6bb00-122">If the <STRONG>Run</STRONG> button is disabled, you may need to first click <STRONG>Run</STRONG> under <STRONG>Install Local Configuration Store</STRONG>.</span></span>

    
    </div>

3.  <span data-ttu-id="6bb00-123">Faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="6bb00-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="6bb00-p104">Se você já tiver um certificado que possa ser utilizado como certificado padrão, clique em **Padrão** no assistente de Certificado e, então, clique em **Atribuir**. Siga as etapas no assistente de Atribuição de Certificado para atribuí-lo.</span><span class="sxs-lookup"><span data-stu-id="6bb00-p104">If you already have a certificate that can be used as the Default certificate, click **Default** in the Certificate wizard and then click **Assign**. Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
      - <span data-ttu-id="6bb00-p105">Se você precisar solicitar um certificado para utilizar o certificado padrão, clique em **Solicitar** e, então, siga as etapas no assistente de Solicitação de Certificado. Se você utilizar valores padrão para o certificado de Servidor da Web, você terá um certificado que pode ser atribuído como certificado padrão.</span><span class="sxs-lookup"><span data-stu-id="6bb00-p105">If you need to request a certificate for use the Default certificate, click **Request** and then follow the steps in the Certificate Request wizard to request that certificate. If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a><span data-ttu-id="6bb00-128">Instalando e configurando um nó de inspetor</span><span class="sxs-lookup"><span data-stu-id="6bb00-128">Installing and Configuring a Watcher Node</span></span>

<span data-ttu-id="6bb00-129">Depois de ter reiniciado o computador de nó do inspetor e configurado o certificado, você precisará executar o arquivo Watchernode.msi.</span><span class="sxs-lookup"><span data-stu-id="6bb00-129">After you have restarted the watcher node computer and configured a certificate, you need to run the file Watchernode.msi.</span></span> <span data-ttu-id="6bb00-130">(Você deve executar o Watchernode. msi em um computador onde os arquivos do agente do Operations Manager e os componentes principais do Lync Server 2013 estão instalados.)</span><span class="sxs-lookup"><span data-stu-id="6bb00-130">(You must run Watchernode.msi on a computer where both the Operations Manager agent files and the Lync Server 2013 core components are installed.)</span></span>

<span data-ttu-id="6bb00-131">**Para instalar e configurar um nó de inspetor**</span><span class="sxs-lookup"><span data-stu-id="6bb00-131">**To install and configure a watcher node**</span></span>

1.  <span data-ttu-id="6bb00-132">Abra o Shell de gerenciamento do Lync Server clicando em **Iniciar**, em **todos os programas**, em **Lync Server**e em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6bb00-132">Open the Lync Server Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server**, and then clicking **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6bb00-133">No Shell de gerenciamento do Lync Server, digite o seguinte comando e pressione ENTER (especifique o caminho real para a sua cópia do Watchernode. msi):</span><span class="sxs-lookup"><span data-stu-id="6bb00-133">In the Lync Server Management Shell, type the following command and then press ENTER (specify the actual path to your copy of Watchernode.msi):</span></span>
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6bb00-p107">Você também pode executar o Watchernode.msi de uma janela de comando. Para abrir uma janela de comando, clique em <STRONG>Iniciar</STRONG>, clique com o botão direito do mouse em <STRONG>Prompt de comando</STRONG> e, então, em <STRONG>Executar como administrador</STRONG>. Quando a janela de comando abrir, digite o mesmo comando anterior.</span><span class="sxs-lookup"><span data-stu-id="6bb00-p107">You can also run Watchernode.msi from a command window. To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>. When the command window opens, type the same preceding command.</span></span>

    
    </div>

<span data-ttu-id="6bb00-p108">Observe que o par de valor/nome no comando anterior Authentication=TrustedServer diferencia maiúscula de minúscula. Você deve digitar exatamente como mostrado. O comando a seguir falha porque não utiliza a formatação correta:</span><span class="sxs-lookup"><span data-stu-id="6bb00-p108">Note that the name/value pair in the preceding command Authentication=TrustedServer is case-sensitive. You must type it exactly as shown. The following command fails because it does not use the correct letter casing:</span></span>

<span data-ttu-id="6bb00-140">C:\\ferramentas\\Watchernode. msi Authentication = trustedserver</span><span class="sxs-lookup"><span data-stu-id="6bb00-140">C:\\Tools\\Watchernode.msi authentication=trustedserver</span></span>

<span data-ttu-id="6bb00-p109">Você pode utilizar o modo TrustedServer apenas com computadores que estão localizados na rede do perímetro. Quando um nó de inspetor está executando no modo TrustedServer, os administradores não precisam manter senhas de usuário de teste no computador.</span><span class="sxs-lookup"><span data-stu-id="6bb00-p109">You can use TrustedServer mode only with computers that are located within the perimeter network. When a watcher node is running in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

