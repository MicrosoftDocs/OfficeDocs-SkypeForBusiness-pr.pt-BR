---
title: 'Lync Server 2013: restaurando um servidor membro da Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83f0283dc6525dbb75ce74809bd88f4e962a9aec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a><span data-ttu-id="48169-102">Restaurando um servidor membro da Enterprise Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48169-102">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48169-103">_**Tópico da última modificação:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="48169-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="48169-104">Se um servidor com uma das funções a seguir falhar, siga o procedimento deste tópico para restaurar o servidor.</span><span class="sxs-lookup"><span data-stu-id="48169-104">If a server running one of the following server roles fails, follow the procedure in this topic to restore the server.</span></span> <span data-ttu-id="48169-105">Se vários servidores falharem independentemente, siga o procedimento para cada servidor.</span><span class="sxs-lookup"><span data-stu-id="48169-105">If multiple servers fail independently, follow the procedure for each server.</span></span>

  - <span data-ttu-id="48169-106">Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="48169-106">Front End Server</span></span>

  - <span data-ttu-id="48169-107">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="48169-107">Mediation Server</span></span>

  - <span data-ttu-id="48169-108">Diretor</span><span class="sxs-lookup"><span data-stu-id="48169-108">Director</span></span>

  - <span data-ttu-id="48169-109">Servidor de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="48169-109">Persistent Chat Server</span></span>

  - <span data-ttu-id="48169-110">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="48169-110">Edge Server</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="48169-111">Recomendamos que você tire uma cópia da imagem do sistema antes de iniciar a restauração.</span><span class="sxs-lookup"><span data-stu-id="48169-111">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="48169-112">Você pode usar essa imagem como um ponto de recuperação, caso algo dê errado durante a restauração.</span><span class="sxs-lookup"><span data-stu-id="48169-112">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="48169-113">Talvez você queira fazer a cópia da imagem depois de instalar o sistema operacional e o SQL Server, e restaurar ou registrar novamente os certificados.</span><span class="sxs-lookup"><span data-stu-id="48169-113">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-member-server"></a><span data-ttu-id="48169-114">Para restaurar um servidor membro</span><span class="sxs-lookup"><span data-stu-id="48169-114">To restore a member server</span></span>

1.  <span data-ttu-id="48169-115">Comece com um servidor limpo ou novo que tenha o mesmo FQDN (nome de domínio totalmente qualificado) da mesma forma que o servidor com falha, instale o sistema operacional e, em seguida, restaure ou registre novamente os certificados.</span><span class="sxs-lookup"><span data-stu-id="48169-115">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed server, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="48169-116">Siga os procedimentos de implantação do servidor da sua organização para executar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="48169-116">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="48169-117">Em uma conta de usuário que seja um membro do grupo RTCUniversalServerAdmins, faça logon no servidor que você está restaurando.</span><span class="sxs-lookup"><span data-stu-id="48169-117">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="48169-118">Navegue até a pasta de instalação ou a mídia do Lync Server e inicie o assistente de implantação do \\Lync\\Server\\localizado em setup AMD64 setup. exe.</span><span class="sxs-lookup"><span data-stu-id="48169-118">Browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span>

4.  <span data-ttu-id="48169-119">Siga o assistente de implantação para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="48169-119">Follow the Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="48169-120">Execute a **etapa 1: instalar o repositório de configuração local** para instalar os arquivos de configuração local.</span><span class="sxs-lookup"><span data-stu-id="48169-120">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="48169-121">Execute a **etapa 2: configurar ou remover componentes do Lync Server** para instalar a função do servidor do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="48169-121">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server role.</span></span>
    
    3.  <span data-ttu-id="48169-122">Execute a **etapa 3: solicitar, instalar ou atribuir certificados** para atribuir os certificados.</span><span class="sxs-lookup"><span data-stu-id="48169-122">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="48169-123">Execute a **etapa 4: Iniciar serviços** para iniciar serviços no servidor.</span><span class="sxs-lookup"><span data-stu-id="48169-123">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="48169-124">Para obter detalhes sobre como executar o assistente de implantação, consulte a documentação de implantação para a função de servidor que você está restaurando.</span><span class="sxs-lookup"><span data-stu-id="48169-124">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

