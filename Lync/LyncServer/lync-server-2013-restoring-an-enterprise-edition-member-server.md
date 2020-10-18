---
title: 'Lync Server 2013: restaurar um servidor membro Enterprise Edition'
description: 'Lync Server 2013: restaurando um servidor membro Enterprise Edition.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f9838f030205d92988e185798d982f835122c9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576047"
---
# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a><span data-ttu-id="d171a-103">Restaurando um servidor membro Enterprise Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d171a-103">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d171a-104">_**Última modificação do tópico:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="d171a-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="d171a-105">Se um servidor que executa uma das seguintes funções de servidor falhar, siga o procedimento neste tópico para restaurar o servidor.</span><span class="sxs-lookup"><span data-stu-id="d171a-105">If a server running one of the following server roles fails, follow the procedure in this topic to restore the server.</span></span> <span data-ttu-id="d171a-106">Se vários servidores falharem independentemente, siga o procedimento para cada servidor.</span><span class="sxs-lookup"><span data-stu-id="d171a-106">If multiple servers fail independently, follow the procedure for each server.</span></span>

  - <span data-ttu-id="d171a-107">Servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="d171a-107">Front End Server</span></span>

  - <span data-ttu-id="d171a-108">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="d171a-108">Mediation Server</span></span>

  - <span data-ttu-id="d171a-109">Diretor</span><span class="sxs-lookup"><span data-stu-id="d171a-109">Director</span></span>

  - <span data-ttu-id="d171a-110">Servidor de Chat persistente</span><span class="sxs-lookup"><span data-stu-id="d171a-110">Persistent Chat Server</span></span>

  - <span data-ttu-id="d171a-111">Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="d171a-111">Edge Server</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d171a-112">Recomendamos que você faça uma cópia de imagem do sistema antes de iniciar a restauração.</span><span class="sxs-lookup"><span data-stu-id="d171a-112">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="d171a-113">Você pode usar essa imagem como um ponto de reversão, caso algo dê errado durante a restauração.</span><span class="sxs-lookup"><span data-stu-id="d171a-113">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="d171a-114">Você pode querer fazer a cópia da imagem depois de instalar o sistema operacional e o SQL Server e restaurar ou registrar novamente os certificados.</span><span class="sxs-lookup"><span data-stu-id="d171a-114">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-member-server"></a><span data-ttu-id="d171a-115">Para restaurar um servidor membro</span><span class="sxs-lookup"><span data-stu-id="d171a-115">To restore a member server</span></span>

1.  <span data-ttu-id="d171a-116">Comece com um servidor limpo ou novo que tenha o mesmo FQDN (nome de domínio totalmente qualificado) que o servidor com falha, instale o sistema operacional e restaure ou registre novamente os certificados.</span><span class="sxs-lookup"><span data-stu-id="d171a-116">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed server, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d171a-117">Siga os procedimentos de implantação de servidor de sua organização para executar essa etapa.</span><span class="sxs-lookup"><span data-stu-id="d171a-117">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="d171a-118">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins, faça logon no servidor que você está restaurando.</span><span class="sxs-lookup"><span data-stu-id="d171a-118">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="d171a-119">Navegue até a pasta ou a mídia de instalação do Lync Server e inicie o assistente de implantação do Lync Server localizado no \\ arquivo de instalação \\ AMD64 \\Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="d171a-119">Browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span>

4.  <span data-ttu-id="d171a-120">Siga o Assistente de Implantação para executar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d171a-120">Follow the Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="d171a-121">Execute **Etapa 1: Instalar Repositório de Configuração Local** para instalar os arquivos de configuração locais.</span><span class="sxs-lookup"><span data-stu-id="d171a-121">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="d171a-122">Execute **etapa 2: instalar ou remover componentes do Lync Server** para instalar a função de servidor do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d171a-122">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server role.</span></span>
    
    3.  <span data-ttu-id="d171a-123">Execute **Etapa 3: Solicitar, Instalar ou Ceder Certificados** para atribuir os certificados.</span><span class="sxs-lookup"><span data-stu-id="d171a-123">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="d171a-124">Execute **Etapa 4: Iniciar os Serviços** para iniciar os serviços no servidor.</span><span class="sxs-lookup"><span data-stu-id="d171a-124">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="d171a-125">Para obter detalhes sobre como executar o assistente de implantação, consulte a documentação de implantação para a função de servidor que você está restaurando.</span><span class="sxs-lookup"><span data-stu-id="d171a-125">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

