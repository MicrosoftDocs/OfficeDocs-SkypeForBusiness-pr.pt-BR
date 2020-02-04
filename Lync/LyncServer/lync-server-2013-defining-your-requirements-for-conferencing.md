---
title: 'Lync Server 2013: Definindo seus requisitos para conferência'
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
ms.openlocfilehash: c19269ef06fc2aa7ec19e2ede53f406b345536b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="37526-102">Definindo seus requisitos para conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37526-102">Defining your requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37526-103">_**Tópico da última modificação:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="37526-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="37526-104">Ao determinar quais funcionalidades de conferência serão implantadas, você precisa considerar os recursos que deseja disponibilizar para seus usuários, bem como seus recursos de largura de banda de rede.</span><span class="sxs-lookup"><span data-stu-id="37526-104">When you are determining which conferencing capabilities to deploy, you need to consider the features that you want available to your users and your network bandwidth capabilities.</span></span> <span data-ttu-id="37526-105">A lista de perguntas a seguir orienta você pelo processo de planejamento de conferência para determinar quais recursos de conferência você deve implantar com base nas necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="37526-105">The following list of questions guides you through the conferencing planning process to determine what features of conferencing you should deploy, based on your organization’s requirements.</span></span>

  - <span data-ttu-id="37526-106">**Você deseja habilitar a webconferência, que inclui a colaboração em documentos e o compartilhamento de aplicativos?**</span><span class="sxs-lookup"><span data-stu-id="37526-106">**Do you want to enable web conferencing, which includes document collaboration and application sharing?**</span></span>
    
    <span data-ttu-id="37526-107">Em caso afirmativo, você deve habilitar a conferência para seu pool de front-end no Microsoft Lync Server 2013, ferramenta de planejamento ou no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="37526-107">If so, you must enable conferencing for your Front End pool in the Microsoft Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="37526-108">Ao habilitar a conferência, habilite A conferência via Web e conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="37526-108">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="37526-109">O compartilhamento de aplicativos requer e usa mais largura de banda que a colaboração em documentos.</span><span class="sxs-lookup"><span data-stu-id="37526-109">Application sharing requires and uses more network bandwidth than document collaboration.</span></span> <span data-ttu-id="37526-110">O Lync Server 2013 fornece um mecanismo de limitação para controlar cada sessão de compartilhamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="37526-110">Lync Server 2013 provides a throttling mechanism to control each application sharing session.</span></span> <span data-ttu-id="37526-111">Por padrão, isso é definido como 1,5 KB por segundo para cada sessão.</span><span class="sxs-lookup"><span data-stu-id="37526-111">By default, this is set to 1.5 KB/second for each session.</span></span>
    
    <span data-ttu-id="37526-112">Se você não quiser habilitar o compartilhamento de aplicativos, mas quiser a colaboração de documentos, poderá habilitar a conferência e usar políticas de reunião para desabilitar o compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="37526-112">If you do not want to enable application sharing but you do want document collaboration, you can enable conferencing and use meeting policies to disable application sharing.</span></span> <span data-ttu-id="37526-113">Para obter detalhes sobre como configurar políticas de reunião, consulte [políticas de conferência no Lync Server 2013](lync-server-2013-conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="37526-113">For details about configuring meeting policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md).</span></span>
    
    <span data-ttu-id="37526-114">Para habilitar os usuários a compartilharem apresentações do PowerPoint, é preciso configurar o Servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="37526-114">To enable users to share PowerPoint presentations, you need to configure Office Web Apps Server.</span></span> <span data-ttu-id="37526-115">Para obter detalhes sobre como configurar o servidor do Office Web Apps, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="37526-115">For details about configuring Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="37526-116">**Você deseja habilitar A conferência A/V?**</span><span class="sxs-lookup"><span data-stu-id="37526-116">**Do you want to enable A/V conferencing?**</span></span>
    
    <span data-ttu-id="37526-117">Em caso afirmativo, você deve habilitar a conferência para seu pool de front-end no Lync Server 2013, ferramenta de planejamento ou no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="37526-117">If so, you must enable conferencing for your Front End pool in the Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="37526-118">Ao habilitar a conferência, habilite A conferência via Web e conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="37526-118">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="37526-119">A conferência A/V requer e usa mais largura de banda de rede do que a Webconferência (que inclui colaboração de documentos e compartilhamento de aplicativos).</span><span class="sxs-lookup"><span data-stu-id="37526-119">A/V conferencing requires and uses more network bandwidth than web conferencing (which includes document collaboration and application sharing).</span></span> <span data-ttu-id="37526-120">Se você não quiser habilitar uma conferência de A/V, mas quiser habilitar a conferência pela Web, poderá habilitar A conferência e usar políticas de reunião para desabilitar conferências A/V.</span><span class="sxs-lookup"><span data-stu-id="37526-120">If you do not want to enable A/V conferencing but you do want to enable web conferencing, you can enable conferencing and use meeting policies to disable A/V conferences.</span></span>
    
    <span data-ttu-id="37526-121">Se quiser habilitar conferências de áudio, mas não videoconferências, você pode habilitar A conferência A/V e usar políticas de reunião para impedir videoconferências.</span><span class="sxs-lookup"><span data-stu-id="37526-121">If you do want to enable audio conferences but not video conferences, you can enable A/V conferencing and use meeting policies to prevent video conferences.</span></span> <span data-ttu-id="37526-122">Como alternativa, você pode habilitar a conferência A/V e permitir que somente determinados usuários iniciem ou participem de conferências A/V.</span><span class="sxs-lookup"><span data-stu-id="37526-122">Alternatively, you can enable A/V conferencing and enable only certain users to start or participate in A/V conferences.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="37526-p109">O Enterprise Voice não é necessário para você usar a conferência A/V. Se você habilitar a conferência A/V, seus usuários poderão adicionar áudio às conferências, caso tenham dispositivos de áudio, mesmo que você use um sistema PBX como solução de telefonia.</span><span class="sxs-lookup"><span data-stu-id="37526-p109">Enterprise Voice is not required for you to use A/V conferencing. If you enable A/V conferencing, your users can add audio to their conferences if they have audio devices, even if you use a PBX for your telephone solution.</span></span>

    
    </div>

  - <span data-ttu-id="37526-125">**Deseja permitir que os usuários ingressem na parte de áudio de conferências ao usar um telefone PSTN?**</span><span class="sxs-lookup"><span data-stu-id="37526-125">**Do you want to enable users to join the audio portion of conferences when using a PSTN phone?**</span></span>
    
    <span data-ttu-id="37526-p110">Em caso afirmativo, implante e habilite a conferência de discagem. Em seguida, os usuários convidados (dentro e fora da sua organização) poderão ingressar na parte de áudio de conferências usando um telefone PSTN.</span><span class="sxs-lookup"><span data-stu-id="37526-p110">If so, deploy and enable dial-in conferencing. Invited users, both inside and outside your organization, can then join the audio portion of conferences by using a PSTN phone.</span></span>

  - <span data-ttu-id="37526-128">**Deseja permitir que usuários externos com clientes do Lync Server 2013 ingressem nos tipos de conferências que você ativou?**</span><span class="sxs-lookup"><span data-stu-id="37526-128">**Do you want to enable external users with Lync Server 2013 clients to join the types of conferences that you have enabled?**</span></span>
    
    <span data-ttu-id="37526-129">Nesse caso, você deve implantar os servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="37526-129">If so, you should deploy Edge Servers.</span></span> <span data-ttu-id="37526-130">Ao permitir a participação externa em reuniões, você maximiza o seu investimento no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37526-130">By allowing external participation in meetings, you maximize your investment in Lync Server 2013.</span></span> <span data-ttu-id="37526-131">Por exemplo, os usuários com laptops com o Lync Server 2013 podem participar de conferências de onde quer que estejam, em casa, no aeroporto ou em sites de clientes.</span><span class="sxs-lookup"><span data-stu-id="37526-131">For example, users with laptops with Lync Server 2013 can join conferences from wherever they are—at home, in the airport, or at customer sites.</span></span>
    
    <span data-ttu-id="37526-132">Além disso, com os servidores de Borda implantados, você pode criar relações federadas com outras organizações, como clientes ou fornecedores, e os usuários dessas organizações podem colaborar com mais facilidade com seus usuários.</span><span class="sxs-lookup"><span data-stu-id="37526-132">Additionally, with Edge Servers deployed you can create federated relationships with other organizations-such as your customers or vendors-and users from those organizations can more easily collaborate with your users.</span></span>
    
    <span data-ttu-id="37526-133">Para obter detalhes sobre a implantação de servidores de borda, consulte [planejando o acesso de usuários externos no Lync server 2013](lync-server-2013-planning-for-external-user-access.md) e [implantando o acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="37526-133">For details about deploying Edge Servers, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span> <span data-ttu-id="37526-134">Para obter detalhes sobre como habilitar o acesso externo para o Office Web Apps Server, consulte [publicando o servidor do Office Web Apps no Lync Server 2013 usando um servidor proxy reverso](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span><span class="sxs-lookup"><span data-stu-id="37526-134">For details about enabling external access for Office Web Apps Server, see [Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span></span>

  - <span data-ttu-id="37526-135">**Você deseja controlar os clientes que podem ingressar em reuniões do Lync Server 2013?**</span><span class="sxs-lookup"><span data-stu-id="37526-135">**Do you want to control the clients that can join Lync Server 2013 meetings?**</span></span>
    
    <span data-ttu-id="37526-136">Em caso afirmativo, você deve configurar a página de ingresso na reunião para que apenas as opções do cliente que você deseja oferecer fiquem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="37526-136">If so, you should configure the meeting join page so that only the client options that you want to support are available.</span></span> <span data-ttu-id="37526-137">Sempre que um usuário clica em um link para ingressar em uma reunião agendada, o Lync Server 2013 detecta se um cliente já está instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="37526-137">Each time a user clicks a link to join a scheduled meeting, Lync Server 2013 detects whether a client is already installed on the computer.</span></span> <span data-ttu-id="37526-138">Em seguida, ele iniciará o cliente padrão e abrirá a página de ingresso na reunião, que contém links para clientes alternativos.</span><span class="sxs-lookup"><span data-stu-id="37526-138">It then starts the default client and opens the meeting join page, which contains links for alternate clients.</span></span> <span data-ttu-id="37526-139">A página Associação de reunião sempre contém a opção para usar o Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="37526-139">The meeting join page always contains the option to use Microsoft Lync Web App.</span></span> <span data-ttu-id="37526-140">Além dessa opção, você pode decidir se deseja incluir links para o Atendedor e versões anteriores do Communicator.</span><span class="sxs-lookup"><span data-stu-id="37526-140">In addition to this option, you can decide whether to include links for Attendee and previous versions of Communicator.</span></span> <span data-ttu-id="37526-141">Para obter detalhes, consulte [Configurando a página ingressar na reunião no Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span><span class="sxs-lookup"><span data-stu-id="37526-141">For details, see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="37526-142">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="37526-142">In This Section</span></span>

  - [<span data-ttu-id="37526-143">Requisitos da webconferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37526-143">Web conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-requirements.md)

  - [<span data-ttu-id="37526-144">Requisitos de conferência A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37526-144">A/V conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-a-v-conferencing-requirements.md)

  - [<span data-ttu-id="37526-145">Requisitos de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37526-145">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="37526-146">Confira também</span><span class="sxs-lookup"><span data-stu-id="37526-146">See Also</span></span>


[<span data-ttu-id="37526-147">Planejamento de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37526-147">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)  
[<span data-ttu-id="37526-148">Lista de verificação de implantação para conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37526-148">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

