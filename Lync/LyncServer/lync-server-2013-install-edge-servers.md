---
title: 'Lync Server 2013: instalar servidores de borda'
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
ms.openlocfilehash: af95403b8a1fc383d8d6065f26a55242e735a51b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a><span data-ttu-id="a81a9-102">Instalar servidores de borda para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a81a9-102">Install Edge Servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a81a9-103">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="a81a9-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="a81a9-104">Você instala o Lync Server 2013 em servidores de borda usando o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a81a9-104">You install Lync Server 2013 on Edge Servers by using Lync Server Deployment Wizard.</span></span> <span data-ttu-id="a81a9-105">Executando o Assistente de Implantação em cada Servidor de Borda, é possível concluir a maioria das tarefas necessárias para configurar o Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="a81a9-105">By running the Deployment Wizard on each Edge Server, you can complete most of the tasks required to set up the Edge Server.</span></span> <span data-ttu-id="a81a9-106">Para implantar o Lync Server 2013 em um servidor de borda, você já deve ter executado o construtor de topologias para definir e publicar sua topologia do servidor de borda e exportá-lo para a mídia que está disponível no servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="a81a9-106">In order to deploy Lync Server 2013 on an Edge Server, you must have already run Topology Builder to define and publish your Edge Server topology, and exported it to media that is available from the Edge Server.</span></span> <span data-ttu-id="a81a9-107">Para obter detalhes, consulte [cenários para acesso de usuário externo no Lync server 2013](lync-server-2013-scenarios-for-external-user-access.md) e [exporte sua topologia do Lync Server 2013 e copie-o para a mídia externa para instalação de borda](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span><span class="sxs-lookup"><span data-stu-id="a81a9-107">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<span data-ttu-id="a81a9-108">Após usar o assistente de implantação para instalar cada servidor de borda, instalar e atribuir os certificados necessários e iniciar os serviços necessários, você poderá concluir a instalação usando as informações em [Configurando o suporte para acesso de usuário externo no Lync server 2013](lync-server-2013-configuring-support-for-external-user-access.md) para habilitar e configurar o acesso de usuário externo e as informações em [verificar sua implantação de borda no Lync 2013 Server](lync-server-2013-verifying-your-edge-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="a81a9-108">After using the Deployment Wizard to install each Edge Server, install and assign the required certificates, and start the required services, you can complete the setup by using the information in [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) to enable and configure external user access and the information in [Verifying your edge deployment in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) to validate the setup, including server and client connectivity.</span></span>

<div>

## <a name="to-install-an-edge-server"></a><span data-ttu-id="a81a9-109">Para instalar um Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="a81a9-109">To install an Edge Server</span></span>

1.  <span data-ttu-id="a81a9-110">Faça logon no computador no qual deseja instalar seu Servidor de Borda como um membro do grupo de Administradores locais ou como uma conta com direitos e permissões de usuário equivalentes.</span><span class="sxs-lookup"><span data-stu-id="a81a9-110">Log on to the computer on which you want to install your Edge Server as a member of the local Administrators group or an account with equivalent user rights and permissions.</span></span>

2.  <span data-ttu-id="a81a9-111">Verifique se o arquivo de configuração de topologia criado usando o construtor de topologias e, em seguida, exportado e copiado para a mídia externa, está disponível no servidor de borda (por exemplo, acesso à unidade USB na qual você copiou o arquivo de configuração de topologia ou verifique acesso ao compartilhamento de rede onde você copiou o arquivo).</span><span class="sxs-lookup"><span data-stu-id="a81a9-111">Ensure that the topology configuration file you created using Topology Builder, and then exported and copied to external media, is available on the Edge Server (for example, access to the USB drive onto which you copied the topology configuration file, or verify access to the network share where you copied the file).</span></span>

3.  <span data-ttu-id="a81a9-112">Iniciar o assistente de implantação.</span><span class="sxs-lookup"><span data-stu-id="a81a9-112">Start the Deployment Wizard.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a81a9-p102">Se você receber uma mensagem dizendo que você precisa instalar o Microsoft Visual C++ Redistribuível, clique em <STRONG>Sim</STRONG>. Na próxima caixa de diálogo, você pode aceitar o padrão <STRONG>Local de instalação</STRONG> ou clique em <STRONG>Pesquisar</STRONG> para selecionar um local e alterá-lo, depois clique em <STRONG>Instalar</STRONG>. Na próxima caixa de diálogo, marque a caixa de seleção <STRONG>Aceito os termos do contrato de licença</STRONG> e clique em <STRONG>OK</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a81a9-p102">If you get a message saying that you need to install Microsoft Visual C++ Redistributable, click <STRONG>Yes</STRONG>. In the next dialog box, you can accept the default <STRONG>Installation Location</STRONG> or click the <STRONG>Browse</STRONG> to select an alternate location, and then click <STRONG>Install</STRONG>. In the next dialog box, select the <STRONG>I accept the terms in the license agreement</STRONG> check box, and then click <STRONG>OK</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="a81a9-116">No Assistente de Implantação, clique em **Instalar ou Atualizar o Sistema do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a81a9-116">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="a81a9-117">Depois que o assistente determinar o estado da implantação, em **Etapa 1. Instalar repositório de configuração local**, clique em **Executar** e, depois, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a81a9-117">After the wizard determines the deployment state, for **Step 1. Install Local Configuration Store**, click **Run** and then do the following:</span></span>
    
      - <span data-ttu-id="a81a9-118">Na caixa de diálogo **Configurar réplica local do repositório de gerenciamento central**, clique em **Importar de um arquivo (Recomendado para os Servidores de Borda)**, vá para o local do arquivo de configuração da topologia, selecione o arquivo .zip, clique em **Abrir** e depois em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a81a9-118">In the **Configure Local Replica of Central Management Store** dialog box, click **Import from a file (Recommended for Edge Servers)**, go to the location of the exported topology configuration file, select the .zip file, click **Open**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="a81a9-119">O Assistente de Implantação lê as informações de configuração do arquivo de configuração e grava o arquivo de configuração XML no computador local.</span><span class="sxs-lookup"><span data-stu-id="a81a9-119">The Deployment Wizard reads the configuration information from the configuration file and writes the XML configuration file to the local computer.</span></span>
    
      - <span data-ttu-id="a81a9-120">Depois que o processo de **Execução de Comandos** for concluído, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="a81a9-120">After the **Executing Commands** process is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="a81a9-121">No assistente de implantação, clique em **etapa 2: instalar ou remover componentes do Lync Server** para instalar os componentes de borda do lync Server 2013 especificados no arquivo de configuração XML que está armazenado no computador local.</span><span class="sxs-lookup"><span data-stu-id="a81a9-121">In the Deployment Wizard, click **Step 2: SetUp or Remove Lync Server Components** to install the Lync Server 2013 edge components specified in the XML configuration file that is stored on the local computer.</span></span>

7.  <span data-ttu-id="a81a9-122">Após concluir a instalação, use as informações em [set up Edge Certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) para instalar e atribuir os certificados necessários antes de iniciar os serviços.</span><span class="sxs-lookup"><span data-stu-id="a81a9-122">After completing the installation, use the information in [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) to install and assign the required certificates before you start services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

