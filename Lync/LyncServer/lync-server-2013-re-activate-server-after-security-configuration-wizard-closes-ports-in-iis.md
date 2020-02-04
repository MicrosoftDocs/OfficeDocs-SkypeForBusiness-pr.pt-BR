---
title: Re-ativar servidor após o Assistente de Configuração de Segurança fechar portas no IIS
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
ms.openlocfilehash: f6642906c1855575fb8077846eef6646bfb37531
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a><span data-ttu-id="28615-102">Re-ativar servidor após o Assistente de Configuração de Segurança fechar portas no IIS</span><span class="sxs-lookup"><span data-stu-id="28615-102">Re-activate server after Security Configuration Wizard closes ports in IIS</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28615-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="28615-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="28615-104">Algumas funções do Lync Server 2013 executam serviços Web na porta do serviços de informações da Internet (IIS) 4443.</span><span class="sxs-lookup"><span data-stu-id="28615-104">Some Lync Server 2013 roles run Web Services on Internet Information Services (IIS) port 4443.</span></span> <span data-ttu-id="28615-105">Executar o assistente de implantação do Lync Server, bootstrapper. exe ou usar o cmdlet **Enable-CsComputer** cria uma exceção no firewall e abre a porta.</span><span class="sxs-lookup"><span data-stu-id="28615-105">Running the Lync Server Deployment Wizard, Bootstrapper.exe, or using the **Enable-CsComputer** cmdlet creates an exception in the firewall and opens the port.</span></span> <span data-ttu-id="28615-106">Se você executar o assistente de configuração de segurança do Windows Server 2008 R2 (ou outros scripts de proteção), a porta 4443 será bloqueada e os clientes externos não poderão entrar em contato com os serviços Web.</span><span class="sxs-lookup"><span data-stu-id="28615-106">If you then run the Windows Server 2008 R2 Security Configuration Wizard (or other hardening scripts), port 4443 will be blocked, and external clients will not be able to contact Web Services.</span></span> <span data-ttu-id="28615-107">Para reabrir a porta, você pode modificar a exceção do firewall diretamente ou ativar novamente o servidor.</span><span class="sxs-lookup"><span data-stu-id="28615-107">To reopen the port you can either modify the firewall exception directly or re-activate the server.</span></span>

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a><span data-ttu-id="28615-108">Para reativar o servidor usando o assistente de implantação</span><span class="sxs-lookup"><span data-stu-id="28615-108">To re-activate the server by using the Deployment Wizard</span></span>

1.  <span data-ttu-id="28615-109">Na página do assistente de implantação do Lync Server, clique em **executar** ao lado da **etapa 2: configurar ou remover componentes do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="28615-109">On the Lync Server Deployment Wizard page, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

2.  <span data-ttu-id="28615-110">Na página **configurar componentes do Lync Server** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="28615-110">On **Setup Lync Server components** page, click **Next**.</span></span>

3.  <span data-ttu-id="28615-111">Na página **comandos em execução** , quando o status da tarefa for exibido como concluído, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="28615-111">On the **Executing Commands** page, when the task status is shown as completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="28615-112">Você também pode usar bootstrapper. exe ou <STRONG>Enable-CsComputer</STRONG> para ativar novamente o servidor.</span><span class="sxs-lookup"><span data-stu-id="28615-112">You can also use bootstrapper.exe or <STRONG>Enable-CsComputer</STRONG> to re-activate the server.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

