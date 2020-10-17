---
title: 'Lync Server 2013: instalar componentes de servidor do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9237ed0b60e14383f69ff1e7ef0b0927afe49c98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498698"
---
# <a name="install-server-components-for-lync-server-2013"></a><span data-ttu-id="e1395-102">Instalar componentes de servidor do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1395-102">Install server components for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1395-103">_**Última modificação do tópico:** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="e1395-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="e1395-104">Antes de seguir estas etapas, verifique se você está conectado ao servidor com uma conta de usuário de domínio que seja um administrador local e um membro do grupo RTCUniversalReadOnlyAdmins no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e1395-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmins group in Active Directory.</span></span>

<span data-ttu-id="e1395-105">O assistente de implantação do Lync Server é usado para instalar os componentes necessários para cada função do Lync Server e para ativar o servidor.</span><span class="sxs-lookup"><span data-stu-id="e1395-105">The Lync Server Deployment Wizard is used to install the needed components for each Lync server role and to activate the server.</span></span> <span data-ttu-id="e1395-106">Este artigo descreve as etapas de implantação de um servidor Standard Edition ou de um servidor front-end na sua infraestrutura do Lync.</span><span class="sxs-lookup"><span data-stu-id="e1395-106">This article walks you through the steps of deploying a Standard Edition server or a Front End Server in your Lync infrastructure.</span></span>

<div>

## <a name="to-install-lync-server-components"></a><span data-ttu-id="e1395-107">Instalação dos componentes do Lync Server</span><span class="sxs-lookup"><span data-stu-id="e1395-107">To install Lync Server components</span></span>

1.  <span data-ttu-id="e1395-108">Se o assistente de implantação do Lync Server não estiver em execução, inicie-o no servidor em que você deseja instalar o Lync.</span><span class="sxs-lookup"><span data-stu-id="e1395-108">If the Lync Server Deployment Wizard isn’t running, start it on the server you want to install Lync onto.</span></span>

2.  <span data-ttu-id="e1395-109">Clique em **instalar ou atualizar o sistema do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e1395-109">Click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="e1395-110">No assistente de implantação, confirme se a **etapa 1: instalar o repositório de configuração local** tem uma marca de seleção verde, o que significa que esse servidor tem uma cópia local do repositório instalado com êxito.</span><span class="sxs-lookup"><span data-stu-id="e1395-110">In the Deployment Wizard, confirm that **Step 1: Install Local Configuration Store** has a green check mark, which means that this server has a local copy of the store installed successfully.</span></span> <span data-ttu-id="e1395-111">Se ele não estiver selecionado, você precisará instalar o repositório de configuração local no servidor.</span><span class="sxs-lookup"><span data-stu-id="e1395-111">If it’s not checked, you need to install the Local Configuration store on the server.</span></span> <span data-ttu-id="e1395-112">Siga as etapas em [instalar o repositório de configuração local no Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) e volte aqui.</span><span class="sxs-lookup"><span data-stu-id="e1395-112">Follow the steps at [Install the Local Configuration store in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) and then come back here.</span></span>

4.  <span data-ttu-id="e1395-113">Quando estiver pronto para instalar os componentes do Lync Server 2013 no servidor, clique em **executar** ao lado de **etapa 2: instalar ou remover componentes do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e1395-113">When you’re ready to install the Lync Server 2013 components on your server, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

5.  <span data-ttu-id="e1395-114">Na página **configurar componentes do Lync Server** , clique em **Avançar** para configurar componentes conforme definido na topologia publicada.</span><span class="sxs-lookup"><span data-stu-id="e1395-114">On the **Set Up Lync Server Components** page, click **Next** to set up components as defined in your published topology.</span></span>

6.  <span data-ttu-id="e1395-115">A página **executando comandos** exibirá um resumo dos comandos e informações de instalação à medida que a configuração ocorrer.</span><span class="sxs-lookup"><span data-stu-id="e1395-115">The **Executing Commands** page will display a summary of commands and installation information as the set up takes place.</span></span> <span data-ttu-id="e1395-116">Quando terminar, você poderá usar a lista para selecionar um log a ser exibido e, em seguida, clique em **Exibir log**.</span><span class="sxs-lookup"><span data-stu-id="e1395-116">When it’s done, you can use the list to select a log to view, and then click **View Log**.</span></span>

7.  <span data-ttu-id="e1395-117">Quando a instalação dos componentes do Lync Server 2013 é concluída e você analisou os logs conforme necessário, clique em **concluir** para concluir esta etapa na instalação.</span><span class="sxs-lookup"><span data-stu-id="e1395-117">When Lync Server 2013 components setup is done, and you’ve reviewed the logs as needed, click **Finish** to complete this step in the installation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e1395-118">Se você for solicitado a reiniciar o servidor (o que pode acontecer se a experiência da área de trabalho do Windows precisar ser instalada), definitivamente faça isso.</span><span class="sxs-lookup"><span data-stu-id="e1395-118">If you’re prompted to restart the server (which might happen if Windows Desktop Experience needed to be installed), definitely do that.</span></span> <span data-ttu-id="e1395-119">Quando o computador fizer o backup e a execução, você precisará executar estas etapas novamente, começando pela etapa três listada acima (basicamente, execute a etapa 2 no assistente de implantação mais uma vez).</span><span class="sxs-lookup"><span data-stu-id="e1395-119">When the computer is back up and running, you need to do these steps over again, starting from step three listed above (basically run Step 2 in the Deployment Wizard one more time).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

