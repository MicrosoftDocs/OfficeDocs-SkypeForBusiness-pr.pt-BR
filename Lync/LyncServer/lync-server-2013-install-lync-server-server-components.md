---
title: 'Lync Server 2013: Instalar componentes de servidor do Lync Server'
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
ms.openlocfilehash: 4f039f9363469663410f08f078a3b7e17a170075
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a><span data-ttu-id="215ee-102">Instalar componentes de servidor para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="215ee-102">Install server components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="215ee-103">_**Tópico da última modificação:** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="215ee-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="215ee-104">Antes de seguir essas etapas, verifique se você está conectado ao servidor com uma conta de usuário de domínio que seja um administrador local e um membro do grupo RTCUniversalReadOnlyAdmins no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="215ee-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmins group in Active Directory.</span></span>

<span data-ttu-id="215ee-105">O assistente de implantação do Lync Server é usado para instalar os componentes necessários para cada função do Lync Server e ativar o servidor.</span><span class="sxs-lookup"><span data-stu-id="215ee-105">The Lync Server Deployment Wizard is used to install the needed components for each Lync server role and to activate the server.</span></span> <span data-ttu-id="215ee-106">Este artigo orienta você pelas etapas de implantação de um servidor Standard Edition ou de um servidor front-end na sua infraestrutura do Lync.</span><span class="sxs-lookup"><span data-stu-id="215ee-106">This article walks you through the steps of deploying a Standard Edition server or a Front End Server in your Lync infrastructure.</span></span>

<div>

## <a name="to-install-lync-server-components"></a><span data-ttu-id="215ee-107">Para instalar os componentes do Lync Server</span><span class="sxs-lookup"><span data-stu-id="215ee-107">To install Lync Server components</span></span>

1.  <span data-ttu-id="215ee-108">Se o assistente de implantação do Lync Server não estiver em execução, inicie-o no servidor em que você deseja instalar o Lync.</span><span class="sxs-lookup"><span data-stu-id="215ee-108">If the Lync Server Deployment Wizard isn’t running, start it on the server you want to install Lync onto.</span></span>

2.  <span data-ttu-id="215ee-109">Clique em **instalar ou atualizar o sistema do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="215ee-109">Click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="215ee-110">No assistente de implantação, confirme se a **etapa 1: instalar o repositório de configuração local** tem uma marca de seleção verde, o que significa que o servidor tem uma cópia local da loja instalada com êxito.</span><span class="sxs-lookup"><span data-stu-id="215ee-110">In the Deployment Wizard, confirm that **Step 1: Install Local Configuration Store** has a green check mark, which means that this server has a local copy of the store installed successfully.</span></span> <span data-ttu-id="215ee-111">Se não estiver marcada, você precisará instalar o repositório de configuração local no servidor.</span><span class="sxs-lookup"><span data-stu-id="215ee-111">If it’s not checked, you need to install the Local Configuration store on the server.</span></span> <span data-ttu-id="215ee-112">Siga as etapas em [instalar o repositório de configuração local no Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) e, em seguida, volte aqui.</span><span class="sxs-lookup"><span data-stu-id="215ee-112">Follow the steps at [Install the Local Configuration store in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) and then come back here.</span></span>

4.  <span data-ttu-id="215ee-113">Quando estiver pronto para instalar os componentes do Lync Server 2013 em seu servidor, clique em **executar** ao lado da **etapa 2: configurar ou remover componentes do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="215ee-113">When you’re ready to install the Lync Server 2013 components on your server, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

5.  <span data-ttu-id="215ee-114">Na página **configurar componentes do Lync Server** , clique em **Avançar** para configurar componentes conforme definido na sua topologia publicada.</span><span class="sxs-lookup"><span data-stu-id="215ee-114">On the **Set Up Lync Server Components** page, click **Next** to set up components as defined in your published topology.</span></span>

6.  <span data-ttu-id="215ee-115">A página **comandos em execução** exibirá um resumo dos comandos e informações de instalação à medida que a configuração ocorre.</span><span class="sxs-lookup"><span data-stu-id="215ee-115">The **Executing Commands** page will display a summary of commands and installation information as the set up takes place.</span></span> <span data-ttu-id="215ee-116">Quando terminar, use a lista para selecionar um log para exibição e clique em **Exibir Log**.</span><span class="sxs-lookup"><span data-stu-id="215ee-116">When it’s done, you can use the list to select a log to view, and then click **View Log**.</span></span>

7.  <span data-ttu-id="215ee-117">Quando a instalação dos componentes do Lync Server 2013 for concluída e você tiver revisado os logs conforme necessário, clique em **concluir** para concluir esta etapa na instalação.</span><span class="sxs-lookup"><span data-stu-id="215ee-117">When Lync Server 2013 components setup is done, and you’ve reviewed the logs as needed, click **Finish** to complete this step in the installation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="215ee-118">Se você for solicitado a reiniciar o servidor (o que pode acontecer se a experiência da área de trabalho do Windows precisar ser instalada), definitivamente faça isso.</span><span class="sxs-lookup"><span data-stu-id="215ee-118">If you’re prompted to restart the server (which might happen if Windows Desktop Experience needed to be installed), definitely do that.</span></span> <span data-ttu-id="215ee-119">Quando o computador estiver em operação de backup e em execução, você precisará executar essas etapas novamente, começando da etapa três listadas acima (basicamente, execute a etapa 2 no assistente de implantação mais uma vez).</span><span class="sxs-lookup"><span data-stu-id="215ee-119">When the computer is back up and running, you need to do these steps over again, starting from step three listed above (basically run Step 2 in the Deployment Wizard one more time).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

