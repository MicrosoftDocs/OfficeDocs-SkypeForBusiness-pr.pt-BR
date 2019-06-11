---
title: 'Lync Server 2013: Pré-requisitos do plug-in Lync VDI'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae32480e5a3dbfbdfc22c4dbde59c62383c9587f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a><span data-ttu-id="f0f60-102">Pré-requisitos do plug-in Lync VDI no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0f60-102">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0f60-103">_**Tópico da última modificação:** 2017-03-07_</span><span class="sxs-lookup"><span data-stu-id="f0f60-103">_**Topic Last Modified:** 2017-03-07_</span></span>

<span data-ttu-id="f0f60-104">Em um ambiente da Virtual Desktop Infrastructure (VDI), as máquinas virtuais e o computador local do usuário devem atender aos requisitos descritos nesta seção.</span><span class="sxs-lookup"><span data-stu-id="f0f60-104">In a virtual desktop infrastructure (VDI) environment, the virtual machines and the user’s local computer must meet the requirements outlined in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f0f60-105">Consulte seu provedor de soluções de virtualização para obter detalhes sobre como instalar e implantar o ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="f0f60-105">Refer to your virtualization solution provider for details about how to install and deploy the virtualized environment.</span></span> <span data-ttu-id="f0f60-106">Para obter informações sobre como implantar um ambiente virtualizado com base no Hyper-V e nos serviços de área de trabalho remota, consulte os seguintes artigos na biblioteca do Microsoft TechNet:</span><span class="sxs-lookup"><span data-stu-id="f0f60-106">For information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft TechNet Library:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="f0f60-107">Hyper-V em<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span><span class="sxs-lookup"><span data-stu-id="f0f60-107">Hyper-V at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span></span></P>
> <LI>
> <P><span data-ttu-id="f0f60-108">Serviços de área de trabalho remota&nbsp;no&nbsp;Windows Server 2008 R2 em<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span><span class="sxs-lookup"><span data-stu-id="f0f60-108">Remote Desktop Services in Windows Server&nbsp;2008&nbsp;R2 at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="f0f60-109">Veja a seguir os requisitos para as máquinas virtuais em execução no computador do Data Center:</span><span class="sxs-lookup"><span data-stu-id="f0f60-109">The following are requirements for the virtual machines running on the data center computer:</span></span>

  - <span data-ttu-id="f0f60-110">Máquinas virtuais devem ser configuradas com o Windows 10, o Windows 8,1, o Windows 8, o Windows 7 ou o Windows Server 2008 R2 com os service packs mais recentes.</span><span class="sxs-lookup"><span data-stu-id="f0f60-110">Virtual machines must be configured with Windows 10, Windows 8.1, Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>

<span data-ttu-id="f0f60-111">Veja a seguir os requisitos para o usuário e o computador local do usuário:</span><span class="sxs-lookup"><span data-stu-id="f0f60-111">The following are requirements for the user and the user’s local computer:</span></span>

  - <span data-ttu-id="f0f60-112">O usuário deve ser hospedado no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0f60-112">The user must be homed on Lync Server 2013.</span></span>

  - <span data-ttu-id="f0f60-113">O computador local deve estar executando o Windows Embedded Standard 7 com SP1, o Windows 7 com SP1, o Windows 8, o Windows 8,1 Embedded ou o Windows 8,1 (não incorporado).</span><span class="sxs-lookup"><span data-stu-id="f0f60-113">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, Windows 8, Windows 8.1 Embedded, or Windows 8.1 (not embedded).</span></span>

  - <span data-ttu-id="f0f60-114">Se você estiver usando os serviços de área de trabalho remota, o bit de bits de plug-in do Lync da VDI (ou seja, se o aplicativo for 32 bits ou 64 bits) deve corresponder ao sistema operacional do sistema operacional do computador local.</span><span class="sxs-lookup"><span data-stu-id="f0f60-114">If you are using Remote Desktop Services, the Lync VDI plug-in bitness (that is, whether the application is 32-bit or 64-bit) must match the local computer’s operating system bitness.</span></span> <span data-ttu-id="f0f60-115">A bits do sistema operacional no computador local e o sistema operacional na máquina virtual não precisam ser correspondentes.</span><span class="sxs-lookup"><span data-stu-id="f0f60-115">The bitness of the operating system on the local computer and the operating system on the virtual machine do not need to match.</span></span> <span data-ttu-id="f0f60-116">Se você estiver usando outra solução ou plataforma de virtualização, consulte a orientação de seu provedor de soluções de virtualização sobre requisitos de bits.</span><span class="sxs-lookup"><span data-stu-id="f0f60-116">If you are using another virtualization solution or platform, refer to guidance from your virtualization solution provider about bitness requirements.</span></span>

  - <span data-ttu-id="f0f60-117">O computador local deve estar executando a versão mais recente do cliente da área de trabalho remota.</span><span class="sxs-lookup"><span data-stu-id="f0f60-117">The local computer must be running the latest version of the remote desktop client.</span></span> <span data-ttu-id="f0f60-118">Instale as últimas atualizações do cliente de Serviços de Área de Trabalho Remota da Microsoft ou o software cliente de área de trabalho remota mais recente do seu provedor de soluções de virtualização.</span><span class="sxs-lookup"><span data-stu-id="f0f60-118">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> <span data-ttu-id="f0f60-119">Para obter as atualizações mais recentes dos serviços de [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)área de trabalho remota, consulte.</span><span class="sxs-lookup"><span data-stu-id="f0f60-119">For the latest Remote Desktop Services updates, see [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

  - <span data-ttu-id="f0f60-120">No computador local, as configurações do cliente de área de trabalho remota devem ser definidas para que o áudio seja reproduzido no computador local e a gravação remota seja desabilitada.</span><span class="sxs-lookup"><span data-stu-id="f0f60-120">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="f0f60-121">Para definir essas configurações para a conexão de área de trabalho remota no Windows, consulte a próxima seção, "para definir as configurações de conexão de área de trabalho remota".</span><span class="sxs-lookup"><span data-stu-id="f0f60-121">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span>

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a><span data-ttu-id="f0f60-122">Para definir as configurações da conexão de área de trabalho remota</span><span class="sxs-lookup"><span data-stu-id="f0f60-122">To configure Remote Desktop Connection settings</span></span>

<span data-ttu-id="f0f60-123">Para preparar a conexão de área de trabalho remota no Windows para o plug-in VDI do Lync, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f0f60-123">To prepare Remote Desktop Connection in Windows for the Lync VDI plug-in, follow these steps.</span></span>

1.  <span data-ttu-id="f0f60-124">Se o computador local estiver executando o Windows 8, pule esta etapa.</span><span class="sxs-lookup"><span data-stu-id="f0f60-124">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="f0f60-125">Se o computador local estiver executando o Windows 7 com SP1, instale a versão mais recente do Windows 8 do cliente dos serviços de área [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)de trabalho remota, disponível em.</span><span class="sxs-lookup"><span data-stu-id="f0f60-125">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the Remote Desktop Services client, available at [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

2.  <span data-ttu-id="f0f60-126">Inicie o cliente de Serviços de Área de Trabalho Remota clicando em **Iniciar** e em **Conexão de Área de Trabalho Remota**.</span><span class="sxs-lookup"><span data-stu-id="f0f60-126">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>

3.  <span data-ttu-id="f0f60-127">Clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="f0f60-127">Click **Options**.</span></span>

4.  <span data-ttu-id="f0f60-128">Clique na guia **Recursos Locais**. Em **Áudio remoto**, clique em **Configurações** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f0f60-128">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
      - <span data-ttu-id="f0f60-129">Em **Reprodução de áudio remoto**, selecione **Reproduzir neste computador**.</span><span class="sxs-lookup"><span data-stu-id="f0f60-129">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
      - <span data-ttu-id="f0f60-130">Em **Gravação de áudio remoto**, selecione **Não gravar**.</span><span class="sxs-lookup"><span data-stu-id="f0f60-130">Under **Remote audio recording**, select **Do not record**.</span></span>
    
      - <span data-ttu-id="f0f60-131">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0f60-131">Click **OK**.</span></span>

5.  <span data-ttu-id="f0f60-132">Clique na guia **Experiência**. Em **Desempenho**, desmarque a caixa de seleção **Armazenamento persistente de bitmaps em cache**.</span><span class="sxs-lookup"><span data-stu-id="f0f60-132">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>

6.  <span data-ttu-id="f0f60-133">Clique na guia **geral** . Em **computador**, digite o nome da máquina virtual e, em seguida, clique em **conectar**.</span><span class="sxs-lookup"><span data-stu-id="f0f60-133">Click the **General** tab. In **Computer**, type the name of the virtual machine, and then click **Connect**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

