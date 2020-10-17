---
title: Reativar servidor após o assistente de configuração de segurança fechar portas no IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a72bfcf9facfeaa3ca943275d9cdcb3b1ac7705
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512038"
---
# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a><span data-ttu-id="5be0e-102">Reativar servidor após o assistente de configuração de segurança fechar portas no IIS</span><span class="sxs-lookup"><span data-stu-id="5be0e-102">Re-activate server after Security Configuration Wizard closes ports in IIS</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5be0e-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5be0e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5be0e-104">Algumas funções do Lync Server 2013 executam serviços Web na porta de serviços de informações da Internet (IIS) 4443.</span><span class="sxs-lookup"><span data-stu-id="5be0e-104">Some Lync Server 2013 roles run Web Services on Internet Information Services (IIS) port 4443.</span></span> <span data-ttu-id="5be0e-105">Executar o assistente de implantação do Lync Server, Bootstrapper.exe ou usar o cmdlet **Enable-CsComputer** cria uma exceção no firewall e abre a porta.</span><span class="sxs-lookup"><span data-stu-id="5be0e-105">Running the Lync Server Deployment Wizard, Bootstrapper.exe, or using the **Enable-CsComputer** cmdlet creates an exception in the firewall and opens the port.</span></span> <span data-ttu-id="5be0e-106">Se você executar o assistente de configuração de segurança do Windows Server 2008 R2 (ou outros scripts de proteção), a porta 4443 será bloqueada, e os clientes externos não poderão entrar em contato com os serviços Web.</span><span class="sxs-lookup"><span data-stu-id="5be0e-106">If you then run the Windows Server 2008 R2 Security Configuration Wizard (or other hardening scripts), port 4443 will be blocked, and external clients will not be able to contact Web Services.</span></span> <span data-ttu-id="5be0e-107">Para reabrir a porta, você pode modificar a exceção do firewall diretamente ou reativar o servidor.</span><span class="sxs-lookup"><span data-stu-id="5be0e-107">To reopen the port you can either modify the firewall exception directly or re-activate the server.</span></span>

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a><span data-ttu-id="5be0e-108">Para reativar o servidor usando o Assistente de Implantação</span><span class="sxs-lookup"><span data-stu-id="5be0e-108">To re-activate the server by using the Deployment Wizard</span></span>

1.  <span data-ttu-id="5be0e-109">Na página Assistente de implantação do Lync Server, clique em **executar** ao lado de **etapa 2: instalar ou remover componentes do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5be0e-109">On the Lync Server Deployment Wizard page, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

2.  <span data-ttu-id="5be0e-110">Na página **Instalar componentes do Lync Server**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="5be0e-110">On **Setup Lync Server components** page, click **Next**.</span></span>

3.  <span data-ttu-id="5be0e-111">Na página **Executando Comandos**, quando o status da tarefa é exibido como concluído, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="5be0e-111">On the **Executing Commands** page, when the task status is shown as completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="5be0e-112">Também é possível usar bootstrapper.exe ou <STRONG>Enable-CsComputer</STRONG> para reativar o servidor.</span><span class="sxs-lookup"><span data-stu-id="5be0e-112">You can also use bootstrapper.exe or <STRONG>Enable-CsComputer</STRONG> to re-activate the server.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

