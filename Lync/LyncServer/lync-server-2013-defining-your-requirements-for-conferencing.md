---
title: 'Lync Server 2013: definindo seus requisitos para conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee3b7631a3c05fb497ee7fcdf37b6db984361845
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="704f1-102">Definindo seus requisitos de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="704f1-102">Defining your requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="704f1-103">_**Última modificação do tópico:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="704f1-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="704f1-p101">Ao determinar quais funcionalidades de conferência serão implantadas, você precisa considerar os recursos que deseja disponibilizar para seus usuários, bem como seus recursos de largura de banda de rede. A lista de perguntas a seguir o guiará durante o processo de planejamento de conferências para determinar quais recursos de conferência você deve implantar de acordo com as necessidades de sua organização.</span><span class="sxs-lookup"><span data-stu-id="704f1-p101">When you are determining which conferencing capabilities to deploy, you need to consider the features that you want available to your users and your network bandwidth capabilities. The following list of questions guides you through the conferencing planning process to determine what features of conferencing you should deploy, based on your organization’s requirements.</span></span>

  - <span data-ttu-id="704f1-106">**Você deseja habilitar a webconferência, que inclui a colaboração em documentos e o compartilhamento de aplicativos?**</span><span class="sxs-lookup"><span data-stu-id="704f1-106">**Do you want to enable web conferencing, which includes document collaboration and application sharing?**</span></span>
    
    <span data-ttu-id="704f1-107">Em caso afirmativo, você deve habilitar a conferência para seu pool de front-ends no Microsoft Lync Server 2013, na ferramenta de planejamento ou no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="704f1-107">If so, you must enable conferencing for your Front End pool in the Microsoft Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="704f1-108">Ao habilitar a conferência, tanto a webconferência como a conferência A/V são habilitadas.</span><span class="sxs-lookup"><span data-stu-id="704f1-108">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="704f1-109">O compartilhamento de aplicativo requer e usa mais largura de banda do que a colaboração em documentos.</span><span class="sxs-lookup"><span data-stu-id="704f1-109">Application sharing requires and uses more network bandwidth than document collaboration.</span></span> <span data-ttu-id="704f1-110">O Lync Server 2013 fornece um mecanismo de limitação para controlar cada sessão de compartilhamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="704f1-110">Lync Server 2013 provides a throttling mechanism to control each application sharing session.</span></span> <span data-ttu-id="704f1-111">Por padrão, isso é definido como 1,5 KB por segundo para cada sessão.</span><span class="sxs-lookup"><span data-stu-id="704f1-111">By default, this is set to 1.5 KB/second for each session.</span></span>
    
    <span data-ttu-id="704f1-112">Se você não desejar habilitar o compartilhamento de aplicativo, mas desejar a colaboração em documentos, poderá habilitar a conferência e usar políticas de reunião para desabilitar o compartilhamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="704f1-112">If you do not want to enable application sharing but you do want document collaboration, you can enable conferencing and use meeting policies to disable application sharing.</span></span> <span data-ttu-id="704f1-113">Para obter detalhes sobre como configurar políticas de reunião, consulte [políticas de conferência no Lync Server 2013](lync-server-2013-conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="704f1-113">For details about configuring meeting policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md).</span></span>
    
    <span data-ttu-id="704f1-114">Para permitir que os usuários compartilhem apresentações do PowerPoint, você precisa configurar o servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="704f1-114">To enable users to share PowerPoint presentations, you need to configure Office Web Apps Server.</span></span> <span data-ttu-id="704f1-115">Para obter detalhes sobre como configurar o servidor do Office Web Apps, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="704f1-115">For details about configuring Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="704f1-116">**Deseja habilitar a conferência A/V?**</span><span class="sxs-lookup"><span data-stu-id="704f1-116">**Do you want to enable A/V conferencing?**</span></span>
    
    <span data-ttu-id="704f1-117">Em caso afirmativo, você deve habilitar a conferência para seu pool de front-ends no Lync Server 2013, na ferramenta de planejamento ou no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="704f1-117">If so, you must enable conferencing for your Front End pool in the Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="704f1-118">Ao habilitar a conferência, tanto a webconferência como a conferência A/V são habilitadas.</span><span class="sxs-lookup"><span data-stu-id="704f1-118">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="704f1-p107">A conferência A/V exige e usa mais largura de banda que a webconferência (que inclui a colaboração em documentos e o compartilhamento de aplicativo). Se você desejar habilitar a webconferência, mas não a conferência A/V, poderá habilitar a conferência e usar as políticas de reunião para desabilitar a conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="704f1-p107">A/V conferencing requires and uses more network bandwidth than web conferencing (which includes document collaboration and application sharing). If you do not want to enable A/V conferencing but you do want to enable web conferencing, you can enable conferencing and use meeting policies to disable A/V conferences.</span></span>
    
    <span data-ttu-id="704f1-p108">Se você desejar habilitar a conferência de áudio, mas não a conferência de vídeo, poderá habilitar a conferência A/V e usar políticas de reunião para impedir as conferências de vídeo. Como alternativa, você pode habilitar a conferência A/V e permitir que somente determinados usuários iniciem ou participem de conferências A/V.</span><span class="sxs-lookup"><span data-stu-id="704f1-p108">If you do want to enable audio conferences but not video conferences, you can enable A/V conferencing and use meeting policies to prevent video conferences. Alternatively, you can enable A/V conferencing and enable only certain users to start or participate in A/V conferences.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="704f1-123">O Enterprise Voice não é necessário para usar A conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="704f1-123">Enterprise Voice is not required for you to use A/V conferencing.</span></span> <span data-ttu-id="704f1-124">Se você habilitar a conferência A/V, seus usuários poderão adicionar áudio a suas conferências se tiverem dispositivos de áudio, mesmo que você use um sistema PBX como sua solução de telefone.</span><span class="sxs-lookup"><span data-stu-id="704f1-124">If you enable A/V conferencing, your users can add audio to their conferences if they have audio devices, even if you use a PBX for your telephone solution.</span></span>

    
    </div>

  - <span data-ttu-id="704f1-125">**Deseja permitir que os usuários ingressem na parte de áudio de conferências quando usam um telefone PSTN?**</span><span class="sxs-lookup"><span data-stu-id="704f1-125">**Do you want to enable users to join the audio portion of conferences when using a PSTN phone?**</span></span>
    
    <span data-ttu-id="704f1-p110">Em caso afirmativo, implante e habilite a conferência de discagem. Em seguida, os usuários convidados (dentro e fora da sua organização) poderão ingressar na parte de áudio de conferências usando um telefone PSTN.</span><span class="sxs-lookup"><span data-stu-id="704f1-p110">If so, deploy and enable dial-in conferencing. Invited users, both inside and outside your organization, can then join the audio portion of conferences by using a PSTN phone.</span></span>

  - <span data-ttu-id="704f1-128">**Deseja permitir que usuários externos com clientes do Lync Server 2013 ingressem nos tipos de conferências que você habilitou?**</span><span class="sxs-lookup"><span data-stu-id="704f1-128">**Do you want to enable external users with Lync Server 2013 clients to join the types of conferences that you have enabled?**</span></span>
    
    <span data-ttu-id="704f1-129">Em caso afirmativo, você deve implantar Servidores de Borda.</span><span class="sxs-lookup"><span data-stu-id="704f1-129">If so, you should deploy Edge Servers.</span></span> <span data-ttu-id="704f1-130">Ao permitir a participação externa em reuniões, você maximiza seu investimento no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="704f1-130">By allowing external participation in meetings, you maximize your investment in Lync Server 2013.</span></span> <span data-ttu-id="704f1-131">Por exemplo, os usuários com laptops com o Lync Server 2013 podem participar de conferências de onde quer que estejam, em casa, no aeroporto ou em sites do cliente.</span><span class="sxs-lookup"><span data-stu-id="704f1-131">For example, users with laptops with Lync Server 2013 can join conferences from wherever they are—at home, in the airport, or at customer sites.</span></span>
    
    <span data-ttu-id="704f1-132">Além disso, com os Servidores de Borda implantados, você pode criar relacionamentos federados com outras organizações (como seus clientes ou fornecedores) e os usuários de empresas poderão colaborar mais facilmente com os usuários.</span><span class="sxs-lookup"><span data-stu-id="704f1-132">Additionally, with Edge Servers deployed you can create federated relationships with other organizations-such as your customers or vendors-and users from those organizations can more easily collaborate with your users.</span></span>
    
    <span data-ttu-id="704f1-133">Para obter detalhes sobre a implantação de servidores de borda, consulte [Planning for External User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) e [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="704f1-133">For details about deploying Edge Servers, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span> <span data-ttu-id="704f1-134">Para obter detalhes sobre como habilitar o acesso externo para o servidor do Office Web Apps, consulte [Publishing Office Web Apps Server in Lync Server 2013 using a Reverse Proxy Server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span><span class="sxs-lookup"><span data-stu-id="704f1-134">For details about enabling external access for Office Web Apps Server, see [Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span></span>

  - <span data-ttu-id="704f1-135">**Você deseja controlar os clientes que podem ingressar em reuniões do Lync Server 2013?**</span><span class="sxs-lookup"><span data-stu-id="704f1-135">**Do you want to control the clients that can join Lync Server 2013 meetings?**</span></span>
    
    <span data-ttu-id="704f1-136">Em caso afirmativo, você deve configurar a página de ingresso em reunião para que apenas as opções do cliente que você deseja oferecer fiquem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="704f1-136">If so, you should configure the meeting join page so that only the client options that you want to support are available.</span></span> <span data-ttu-id="704f1-137">Cada vez que um usuário clica em um link para ingressar em uma reunião agendada, o Lync Server 2013 detecta se um cliente já está instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="704f1-137">Each time a user clicks a link to join a scheduled meeting, Lync Server 2013 detects whether a client is already installed on the computer.</span></span> <span data-ttu-id="704f1-138">Em seguida, ele iniciará o cliente padrão e abrirá a página de ingresso em reunião, que contém links para clientes alternativos.</span><span class="sxs-lookup"><span data-stu-id="704f1-138">It then starts the default client and opens the meeting join page, which contains links for alternate clients.</span></span> <span data-ttu-id="704f1-139">A página de participação da reunião contém a opção de usar o Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="704f1-139">The meeting join page always contains the option to use Microsoft Lync Web App.</span></span> <span data-ttu-id="704f1-140">Além dessa opção, você pode decidir se deseja incluir links para o participante e versões anteriores do Communicator.</span><span class="sxs-lookup"><span data-stu-id="704f1-140">In addition to this option, you can decide whether to include links for Attendee and previous versions of Communicator.</span></span> <span data-ttu-id="704f1-141">Para obter detalhes, consulte [Configurando a página de ingresso na reunião no Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span><span class="sxs-lookup"><span data-stu-id="704f1-141">For details, see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="704f1-142">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="704f1-142">In This Section</span></span>

  - [<span data-ttu-id="704f1-143">Requisitos de Webconferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="704f1-143">Web conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-requirements.md)

  - [<span data-ttu-id="704f1-144">Requisitos de conferência A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="704f1-144">A/V conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-a-v-conferencing-requirements.md)

  - [<span data-ttu-id="704f1-145">Requisitos de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="704f1-145">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="704f1-146">Confira também</span><span class="sxs-lookup"><span data-stu-id="704f1-146">See Also</span></span>


[<span data-ttu-id="704f1-147">Planejamento de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="704f1-147">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)  
[<span data-ttu-id="704f1-148">Lista de verificação de implantação para conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="704f1-148">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

