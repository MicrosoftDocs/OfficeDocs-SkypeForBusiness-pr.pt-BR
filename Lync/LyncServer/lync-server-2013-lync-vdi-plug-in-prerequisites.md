---
title: 'Lync Server 2013: pré-requisitos do plug-in VDI do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b63ee7f494b131fc194d6bf9d028525efd71cf0a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534678"
---
# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a><span data-ttu-id="c739b-102">Pré-requisitos do plug-in VDI do Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c739b-102">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c739b-103">_**Última modificação do tópico:** 2017-03-07_</span><span class="sxs-lookup"><span data-stu-id="c739b-103">_**Topic Last Modified:** 2017-03-07_</span></span>

<span data-ttu-id="c739b-104">Em um ambiente de infraestrutura de área de trabalho virtual (VDI), as máquinas virtuais e o computador local do usuário devem atender aos requisitos descritos nesta seção.</span><span class="sxs-lookup"><span data-stu-id="c739b-104">In a virtual desktop infrastructure (VDI) environment, the virtual machines and the user’s local computer must meet the requirements outlined in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c739b-p101">Consulte o provedor de solução de virtualização para obter detalhes sobre como instalar e implantar o ambiente virtualizado. Para obter informações sobre como implantar um ambiente virtualizado com base nos Serviços de Área de Trabalho Remota e Hyper-V, consulte os artigos a seguir na Biblioteca TechNet da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="c739b-p101">Refer to your virtualization solution provider for details about how to install and deploy the virtualized environment. For information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft TechNet Library:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="c739b-107">Hyper-V em <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span><span class="sxs-lookup"><span data-stu-id="c739b-107">Hyper-V at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span></span></P>
> <LI>
> <P><span data-ttu-id="c739b-108">Serviços de área de trabalho remota no Windows Server &nbsp; 2008 &nbsp; R2 em <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span><span class="sxs-lookup"><span data-stu-id="c739b-108">Remote Desktop Services in Windows Server&nbsp;2008&nbsp;R2 at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="c739b-109">A seguir estão requisitos para máquinas virtuais executando no computador do centro de dados:</span><span class="sxs-lookup"><span data-stu-id="c739b-109">The following are requirements for the virtual machines running on the data center computer:</span></span>

  - <span data-ttu-id="c739b-110">As máquinas virtuais devem ser configuradas com Windows 10, Windows 8,1, Windows 8, Windows 7 ou Windows Server 2008 R2 com os service packs mais recentes.</span><span class="sxs-lookup"><span data-stu-id="c739b-110">Virtual machines must be configured with Windows 10, Windows 8.1, Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>

<span data-ttu-id="c739b-111">Estes são os requisitos para o usuário e o computador local do usuário:</span><span class="sxs-lookup"><span data-stu-id="c739b-111">The following are requirements for the user and the user’s local computer:</span></span>

  - <span data-ttu-id="c739b-112">O usuário deve estar hospedado no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c739b-112">The user must be homed on Lync Server 2013.</span></span>

  - <span data-ttu-id="c739b-113">O computador local deve estar executando o Windows Embedded Standard 7 com SP1, Windows 7 com SP1, Windows 8, Windows 8,1 Embedded ou Windows 8,1 (não incorporado).</span><span class="sxs-lookup"><span data-stu-id="c739b-113">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, Windows 8, Windows 8.1 Embedded, or Windows 8.1 (not embedded).</span></span>

  - <span data-ttu-id="c739b-114">Se você estiver usando os serviços de área de trabalho remota, a leitura de bits do plug-in VDI do Lync (ou seja, se o aplicativo for 32 bits ou 64 bits) deve corresponder ao bit de bits do sistema operacional do computador local.</span><span class="sxs-lookup"><span data-stu-id="c739b-114">If you are using Remote Desktop Services, the Lync VDI plug-in bitness (that is, whether the application is 32-bit or 64-bit) must match the local computer’s operating system bitness.</span></span> <span data-ttu-id="c739b-115">O bitness do sistema operacional no computador local e o sistema operacional na máquina virtual não precisam corresponder.</span><span class="sxs-lookup"><span data-stu-id="c739b-115">The bitness of the operating system on the local computer and the operating system on the virtual machine do not need to match.</span></span> <span data-ttu-id="c739b-116">Se você estiver usando outra solução de virtualização ou plataforma, consulte o guia do seu provedor de solução de virtualização sobre os requisitos de bitness.</span><span class="sxs-lookup"><span data-stu-id="c739b-116">If you are using another virtualization solution or platform, refer to guidance from your virtualization solution provider about bitness requirements.</span></span>

  - <span data-ttu-id="c739b-117">O computador local deve estar executando a versão mais atual do cliente de área de trabalho remota.</span><span class="sxs-lookup"><span data-stu-id="c739b-117">The local computer must be running the latest version of the remote desktop client.</span></span> <span data-ttu-id="c739b-118">Instale as últimas atualizações do cliente dos Serviços da Área de Trabalho Remota da Microsoft ou o software do cliente de área de trabalho remota mais atual do seu provedor de solução de virtualização.</span><span class="sxs-lookup"><span data-stu-id="c739b-118">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> <span data-ttu-id="c739b-119">Para obter as atualizações mais recentes dos serviços de área de trabalho remota, consulte [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) .</span><span class="sxs-lookup"><span data-stu-id="c739b-119">For the latest Remote Desktop Services updates, see [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

  - <span data-ttu-id="c739b-120">No computador local, as configurações do cliente de área de trabalho remota devem ser definidas para que o áudio reproduza o computador local e a gravação remota esteja desabilitada.</span><span class="sxs-lookup"><span data-stu-id="c739b-120">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="c739b-121">Para definir essas configurações para a conexão de área de trabalho remota no Windows, confira a próxima seção, "para definir as configurações da conexão de área de trabalho remota".</span><span class="sxs-lookup"><span data-stu-id="c739b-121">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span>

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a><span data-ttu-id="c739b-122">Para definir as configurações da Conexão da Área de Trabalho Remota</span><span class="sxs-lookup"><span data-stu-id="c739b-122">To configure Remote Desktop Connection settings</span></span>

<span data-ttu-id="c739b-123">Para preparar a conexão de área de trabalho remota no Windows para o plug-in VDI do Lync, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c739b-123">To prepare Remote Desktop Connection in Windows for the Lync VDI plug-in, follow these steps.</span></span>

1.  <span data-ttu-id="c739b-124">Se o computador local estiver executando o Windows 8, pule esta etapa.</span><span class="sxs-lookup"><span data-stu-id="c739b-124">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="c739b-125">Se o computador local estiver executando o Windows 7 com SP1, instale a versão mais recente do Windows 8 do cliente de serviços de área de trabalho remota, disponível em [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) .</span><span class="sxs-lookup"><span data-stu-id="c739b-125">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the Remote Desktop Services client, available at [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

2.  <span data-ttu-id="c739b-126">Inicie o cliente dos Serviços de Área de Trabalho Remota clicando em **Iniciar** e em **Conexão da Área de Trabalho Remota**.</span><span class="sxs-lookup"><span data-stu-id="c739b-126">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>

3.  <span data-ttu-id="c739b-127">Clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="c739b-127">Click **Options**.</span></span>

4.  <span data-ttu-id="c739b-128">Clique na guia **Recursos locais**. Em **Áudio remoto**, clique em **Configurações** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c739b-128">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
      - <span data-ttu-id="c739b-129">Em **Reprodução de áudio remoto**, selecione **Reproduzir neste computador**.</span><span class="sxs-lookup"><span data-stu-id="c739b-129">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
      - <span data-ttu-id="c739b-130">Em **Gravação de áudio remoto**, selecione **Não gravar**.</span><span class="sxs-lookup"><span data-stu-id="c739b-130">Under **Remote audio recording**, select **Do not record**.</span></span>
    
      - <span data-ttu-id="c739b-131">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c739b-131">Click **OK**.</span></span>

5.  <span data-ttu-id="c739b-132">Clique na guia **Experiência**. Em **Desempenho**, desmarque a caixa de seleção **Cache de bitmap persistente**.</span><span class="sxs-lookup"><span data-stu-id="c739b-132">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>

6.  <span data-ttu-id="c739b-133">Clique na guia **Geral**. Em **Computador**, digite o nome da máquina virtual e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="c739b-133">Click the **General** tab. In **Computer**, type the name of the virtual machine, and then click **Connect**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

