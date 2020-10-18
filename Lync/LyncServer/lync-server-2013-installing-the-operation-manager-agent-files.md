---
title: 'Lync Server 2013: instalando os arquivos do agente do Gerenciador de operações'
description: 'Lync Server 2013: instalando os arquivos do agente do Operation Manager.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61bba93549e4831b65657a1fe80c918bbcb45572
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573777"
---
# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a><span data-ttu-id="2216f-103">Instalando os arquivos do agente do Operation Manager no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2216f-103">Installing the Operation Manager agent files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2216f-104">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="2216f-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="2216f-105">Para instalar os arquivos do agente do Operations Manager no computador, conclua as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="2216f-105">To install the Operations Manager agent files on the computer, complete the following steps.</span></span>

1.  <span data-ttu-id="2216f-106">Na mídia de instalação do System Center, clique duas vezes em **SetupOM.exe**.</span><span class="sxs-lookup"><span data-stu-id="2216f-106">On your System Center setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="2216f-107">Na instalação do System Center Operation Manager, clique em **instalar o agente do Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="2216f-107">In System Center Operation Manager setup, click **Install Operations Manager Agent**.</span></span>

3.  <span data-ttu-id="2216f-108">No assistente de instalação do System Center, na página **Bem-vindo ao assistente de instalação do System Center Operations Manager** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2216f-108">In System Center Setup wizard, on the **Welcome to the System Center Operations Manager Setup** wizard page, click **Next**.</span></span>

4.  <span data-ttu-id="2216f-109">Na página **pasta de destino** , selecione a pasta onde os arquivos do agente do Operations Manager serão instalados e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2216f-109">On the **Destination Folder** page, select the folder where the Operations Manager Agent files will be installed, and then click **Next**.</span></span>

5.  <span data-ttu-id="2216f-110">Na página **configuração do grupo de gerenciamento** , selecione **especificar informações do grupo de gerenciamento**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2216f-110">On the **Management Group Configuration** page, select **Specify Management Group information**, and then click **Next**.</span></span>

6.  <span data-ttu-id="2216f-111">Na página **configuração do grupo de gerenciamento** , digite o nome do grupo de gerenciamento do Operations Manager na caixa **nome do grupo de gerenciamento** e, em seguida, digite o nome do host do seu servidor do Operations Manager (por exemplo, ATL-SCOM-001) na caixa servidor de **Gerenciamento** .</span><span class="sxs-lookup"><span data-stu-id="2216f-111">On the **Management Group Configuration** page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="2216f-112">Se você tiver alterado o número da porta usada pelo Operations Manager, digite o novo número de porta na caixa porta do servidor de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="2216f-112">If you have changed the port number used by Operations Manager, then type the new port number in the Management Server Port box.</span></span> <span data-ttu-id="2216f-113">Caso contrário, deixe a porta no valor padrão de 5723 e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2216f-113">Otherwise, leave the port at the default value of 5723 and click **Next**.</span></span>

7.  <span data-ttu-id="2216f-114">Na página **conta de ação do agente** , selecione **sistema local**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2216f-114">On the **Agent Action Account** page, select **Local System**, and then click **Next**.</span></span>

8.  <span data-ttu-id="2216f-115">Na página **Microsoft Update** , selecione **eu não desejo usar o Microsoft Update**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2216f-115">On the **Microsoft Update** page, select **I don't want to use Microsoft Update**, and then click **Next**.</span></span>

9.  <span data-ttu-id="2216f-116">Na página **pronto para instalar** , clique em **instalar**.</span><span class="sxs-lookup"><span data-stu-id="2216f-116">On the **Ready to Install** page, click **Install**.</span></span>

10. <span data-ttu-id="2216f-117">Na página **concluindo o assistente de instalação do System Center Operations Manager** , clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="2216f-117">On the **Completing the System Center Operations Manager Setup wizard** page, click **Finish**.</span></span>

11. <span data-ttu-id="2216f-118">Clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="2216f-118">Click **Exit**.</span></span>

<span data-ttu-id="2216f-119">Se você estiver usando o System Center 2007 R2, é possível verificar se o agente foi criado clicando em **Iniciar**, em **todos os programas**, em **System Center Operations Manager 2007 R2**e, em seguida, em **shell do Operations Manager**.</span><span class="sxs-lookup"><span data-stu-id="2216f-119">If you are using System Center 2007 R2, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2007 R2**, and then clicking **Operations Manager Shell**.</span></span> <span data-ttu-id="2216f-120">No Shell do Operations Manager, digite o seguinte comando do Windows PowerShell e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="2216f-120">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-Agent 

<span data-ttu-id="2216f-121">Uma lista de todos os seus agentes do Operations Manager será exibida na tela.</span><span class="sxs-lookup"><span data-stu-id="2216f-121">A list of all your Operations Manager agents will appear onscreen.</span></span>

<span data-ttu-id="2216f-122">Se você estiver usando o System Center 2012, execute este comando no Shell do Gerenciador de operações 2012:</span><span class="sxs-lookup"><span data-stu-id="2216f-122">If you are using System Center 2012, run this command from the Operations 2012 Manager Shell:</span></span>

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

