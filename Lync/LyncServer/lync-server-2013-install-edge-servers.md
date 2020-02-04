---
title: 'Lync Server 2013: Instalar Servidores de Borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22d1961a158ead735ae63d20bb2bd233d6ed5958
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a><span data-ttu-id="9ff15-102">Instalar Servidores de Borda para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ff15-102">Install Edge Servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ff15-103">_**Tópico da última modificação:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="9ff15-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="9ff15-104">Você instala o Lync Server 2013 em servidores de borda usando o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ff15-104">You install Lync Server 2013 on Edge Servers by using Lync Server Deployment Wizard.</span></span> <span data-ttu-id="9ff15-105">Ao executar o assistente de implantação em cada servidor de borda, você pode concluir a maioria das tarefas necessárias para configurar o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="9ff15-105">By running the Deployment Wizard on each Edge Server, you can complete most of the tasks required to set up the Edge Server.</span></span> <span data-ttu-id="9ff15-106">Para implantar o Lync Server 2013 em um servidor de borda, você já deve ter executado o construtor de topologias para definir e publicar a topologia do servidor de borda e exportá-la para a mídia que está disponível no servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="9ff15-106">In order to deploy Lync Server 2013 on an Edge Server, you must have already run Topology Builder to define and publish your Edge Server topology, and exported it to media that is available from the Edge Server.</span></span> <span data-ttu-id="9ff15-107">Para obter detalhes, consulte [cenários para acesso de usuários externos no Lync server 2013](lync-server-2013-scenarios-for-external-user-access.md) e [exporte sua topologia do Lync Server 2013 e copie-o para mídia externa para instalação do Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span><span class="sxs-lookup"><span data-stu-id="9ff15-107">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<span data-ttu-id="9ff15-108">Depois de usar o assistente de implantação para instalar cada servidor de borda, instalar e atribuir os certificados necessários e iniciar os serviços necessários, você pode concluir a configuração usando as informações em [Configurando o suporte para acesso de usuários externos no Lync server 2013](lync-server-2013-configuring-support-for-external-user-access.md) para habilitar e configurar o acesso do usuário externo e as informações para [verificar sua implantação de borda no Lync 2013 Server](lync-server-2013-verifying-your-edge-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="9ff15-108">After using the Deployment Wizard to install each Edge Server, install and assign the required certificates, and start the required services, you can complete the setup by using the information in [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) to enable and configure external user access and the information in [Verifying your edge deployment in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) to validate the setup, including server and client connectivity.</span></span>

<div>

## <a name="to-install-an-edge-server"></a><span data-ttu-id="9ff15-109">Para instalar um servidor de borda</span><span class="sxs-lookup"><span data-stu-id="9ff15-109">To install an Edge Server</span></span>

1.  <span data-ttu-id="9ff15-110">Faça logon no computador no qual você deseja instalar o servidor de borda como membro do grupo Administradores local ou de uma conta com direitos e permissões de usuário equivalentes.</span><span class="sxs-lookup"><span data-stu-id="9ff15-110">Log on to the computer on which you want to install your Edge Server as a member of the local Administrators group or an account with equivalent user rights and permissions.</span></span>

2.  <span data-ttu-id="9ff15-111">Verifique se o arquivo de configuração de topologia que você criou usando o construtor de topologias e depois exportado e copiado para mídia externa está disponível no servidor de borda (por exemplo, acesso à unidade USB na qual você copiou o arquivo de configuração de topologia ou verifique acesso ao compartilhamento de rede onde você copiou o arquivo).</span><span class="sxs-lookup"><span data-stu-id="9ff15-111">Ensure that the topology configuration file you created using Topology Builder, and then exported and copied to external media, is available on the Edge Server (for example, access to the USB drive onto which you copied the topology configuration file, or verify access to the network share where you copied the file).</span></span>

3.  <span data-ttu-id="9ff15-112">Iniciar o assistente de implantação.</span><span class="sxs-lookup"><span data-stu-id="9ff15-112">Start the Deployment Wizard.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9ff15-113">Se você receber uma mensagem dizendo que precisa instalar o Microsoft Visual C++ Redistributable, clique em <STRONG>Sim</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9ff15-113">If you get a message saying that you need to install Microsoft Visual C++ Redistributable, click <STRONG>Yes</STRONG>.</span></span> <span data-ttu-id="9ff15-114">Na próxima caixa de diálogo, você pode aceitar o <STRONG>local de instalação</STRONG> padrão ou clicar em <STRONG>procurar</STRONG> para selecionar um local alternativo e, em seguida, clicar em <STRONG>instalar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9ff15-114">In the next dialog box, you can accept the default <STRONG>Installation Location</STRONG> or click the <STRONG>Browse</STRONG> to select an alternate location, and then click <STRONG>Install</STRONG>.</span></span> <span data-ttu-id="9ff15-115">Na caixa de diálogo seguinte, marque a caixa de seleção aceito <STRONG>os termos do contrato de licença</STRONG> e clique em <STRONG>OK</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9ff15-115">In the next dialog box, select the <STRONG>I accept the terms in the license agreement</STRONG> check box, and then click <STRONG>OK</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="9ff15-116">No assistente de implantação, clique em **instalar ou atualizar o sistema do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9ff15-116">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="9ff15-117">Após o assistente determinar o estado de implantação, para a **etapa 1. Instale o repositório de configuração local**, clique em **executar** e siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="9ff15-117">After the wizard determines the deployment state, for **Step 1. Install Local Configuration Store**, click **Run** and then do the following:</span></span>
    
      - <span data-ttu-id="9ff15-118">Na caixa de diálogo **Configurar réplica local do repositório de gerenciamento central** , clique em **importar de um arquivo (recomendado para servidores de borda)**, vá para o local do arquivo de configuração de topologia exportado, selecione o arquivo. zip, clique em **abrir**e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9ff15-118">In the **Configure Local Replica of Central Management Store** dialog box, click **Import from a file (Recommended for Edge Servers)**, go to the location of the exported topology configuration file, select the .zip file, click **Open**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="9ff15-119">O assistente de implantação lê as informações de configuração do arquivo de configuração e grava o arquivo de configuração XML no computador local.</span><span class="sxs-lookup"><span data-stu-id="9ff15-119">The Deployment Wizard reads the configuration information from the configuration file and writes the XML configuration file to the local computer.</span></span>
    
      - <span data-ttu-id="9ff15-120">Depois que o processo de **Execução de Comandos** for concluído, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="9ff15-120">After the **Executing Commands** process is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="9ff15-121">No assistente de implantação, clique em **etapa 2: configurar ou remover componentes do Lync Server** para instalar os componentes de borda do lync Server 2013 especificados no arquivo de configuração XML armazenado no computador local.</span><span class="sxs-lookup"><span data-stu-id="9ff15-121">In the Deployment Wizard, click **Step 2: SetUp or Remove Lync Server Components** to install the Lync Server 2013 edge components specified in the XML configuration file that is stored on the local computer.</span></span>

7.  <span data-ttu-id="9ff15-122">Depois de concluir a instalação, use as informações em [configurar certificados de borda do Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) para instalar e atribuir os certificados obrigatórios antes de iniciar serviços.</span><span class="sxs-lookup"><span data-stu-id="9ff15-122">After completing the installation, use the information in [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) to install and assign the required certificates before you start services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

