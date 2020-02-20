---
title: 'Lync Server 2013: Gerenciando a qualidade de serviço (QoS)'
ms.reviewer: ''
f1.keywords:
- NOCSH
TOCTitle: Managing Quality of Service (QoS)
author: lanachin
ms.author: v-lanac
ms.manager: serdars
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b72fbd1275060ce01d56cb64e11cdd27f38b2e54
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a><span data-ttu-id="42d47-102">Gerenciando a qualidade de serviço (QoS) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42d47-102">Managing Quality of Service (QoS) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42d47-103">_**Última modificação do tópico:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="42d47-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="42d47-p101">A Qualidade de Serviço (QoS) é uma tecnologia de rede usada em algumas organizações para ajudar a fornecer a melhor experiência ao usuário final para comunicações de áudio e vídeo. a QoS é usada mais frequentemente em rede com largura de banda limitada: com uma grande número de pacotes de rede para uma quantidade relativamente pequena de largura de banda disponível, a Qualidade de Serviço fornece aos administradores uma maneira de atribuírem prioridades mais altas a pacotes que carregam dados de áudio e vídeo. Ao conceder uma prioridade mais alta a esses pacotes, as comunicações de áudio e vídeo têm uma probabilidade maior de serem concluídas mais rápido e com menos interrupções do que as sessões de rede envolvendo itens como transferências de arquivos, navegação da Web ou backups de bancos de dados. Isso ocorre porque os pacotes de rede usados para transferências de arquivos ou backups de bancos de dados recebem uma atribuição de prioridade de "melhor esforço".</span><span class="sxs-lookup"><span data-stu-id="42d47-p101">Quality of Service (QoS) is a networking technology used in some organizations to help provide an optimal end-user experience for audio and video communications. QoS is most-commonly used on networks where bandwidth is limited: with a large number of network packets competing for a relatively small amount of available bandwidth, Quality of Service provides a way for administrators to assign higher priorities to packets carrying audio or video data. By giving these packets a higher priority, audio and video communications are likely to complete faster, and with less interruption, than network sessions involving things like file transfers, web browsing, or database backups. That's because network packets used for file transfers or database backups are assigned a "best effort" priority.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42d47-p102">Como regra geral, a Qualidade de Serviço se aplica somente a sessões de comunicação em sua rede interna. Ao implementar a QoS, você configure seus servidores e roteadores para suportar a marcação de pacotes; no entanto, você configura esses dispositivos para suportar a marcação de pacotes de forma específica. Não é possível considerar que a Qualidade de Serviço será suportada na Internet ou em outras redes. Mesmo se a Qualidade de Serviço for suportada em outras redes, não há garantia de que a QoS será configurada de forma igual a que você configurou o serviço em sua rede.</span><span class="sxs-lookup"><span data-stu-id="42d47-p102">As a general rule, Quality of Service applies only to communication sessions on your internal network. When you implement QoS, you configure your servers and routers to support packet marking; however, you configure these devices to support packet marking in a particular manner. You cannot assume that Quality of Service will be supported on the Internet or on other networks. Even if Quality if Service is supported on other networks, there is no guarantee that QoS will be configured the same way that you configured the service on your network.</span></span>



</div>

<span data-ttu-id="42d47-112">O Microsoft Lync Server 2013 não requer qualidade de serviço; Se você não usa QoS no momento, não é necessário instalar o serviço antes de instalar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="42d47-112">Microsoft Lync Server 2013 does not require Quality of Service; if you do not currently use QoS there is no requirement that you install the service before installing Lync Server 2013.</span></span> <span data-ttu-id="42d47-113">Se você notar uma quantidade considerável de perda de pacotes em sua rede, a maneira recomendada de aliviar esse problema é adicionar mais largura de banda.</span><span class="sxs-lookup"><span data-stu-id="42d47-113">If you experience a considerable amount of packet loss on your network the recommended way to alleviate this problem is to add additional bandwidth.</span></span> <span data-ttu-id="42d47-114">Se não for possível adicionar mais largura de banda, então pode ser necessário implementar a Qualidade de Serviço.</span><span class="sxs-lookup"><span data-stu-id="42d47-114">If adding more bandwidth is not possible, then you might want to implement Quality of Service instead.</span></span>

<span data-ttu-id="42d47-115">O Lync Server 2013 oferece suporte completo para a qualidade de serviço: isso significa que as organizações que já estão usando a QoS podem integrar facilmente o Lync Server à sua infraestrutura de rede existente.</span><span class="sxs-lookup"><span data-stu-id="42d47-115">Lync Server 2013 offers full support for Quality of Service: that means that organizations that are already using QoS can easily integrate Lync Server into their existing network infrastructure.</span></span> <span data-ttu-id="42d47-116">Para fazer isso, você precisa executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="42d47-116">In order to do this you must perform the following tasks:</span></span>

  - <span data-ttu-id="42d47-117">[Habilitando a QoS no Lync Server 2013 para dispositivos que não são baseados no Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span><span class="sxs-lookup"><span data-stu-id="42d47-117">[Enabling QoS in Lync Server 2013 for devices that are not based on Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span></span> <span data-ttu-id="42d47-118">Por padrão, a QoS está desativada para computadores e outros dispositivos (como iPhones) que executam outros sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="42d47-118">By default, QoS is disabled for computers and other devices (such as iPhones) that run other operating systems.</span></span> <span data-ttu-id="42d47-119">Embora você possa usar o Lync Server para habilitar e desabilitar a qualidade do serviço para dispositivos, normalmente não é possível usar o produto para modificar os códigos de DSCP usados por esses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="42d47-119">Although you can use Lync Server to enable and disable Quality of Service for devices, you typically cannot use the product to modify the DSCP codes used by these devices.</span></span>

  - <span data-ttu-id="42d47-120">[Configurando intervalos de portas no Lync Server 2013 para seus servidores de conferência, aplicativos e mediação](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span><span class="sxs-lookup"><span data-stu-id="42d47-120">[Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="42d47-121">É necessário reservar um conjunto exclusivo de portas para tipos de pacotes diferentes, como áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="42d47-121">You must reserve a unique set of ports for different packet types, such as audio and video.</span></span> <span data-ttu-id="42d47-122">Com o Lync Server 2013, não é possível habilitar ou desabilitar a qualidade de serviço, digamos, definir um valor de propriedade como true ou false.</span><span class="sxs-lookup"><span data-stu-id="42d47-122">With Lync Server 2013 you do not enable or disable Quality of Service by, say, setting a property value to True or to False.</span></span> <span data-ttu-id="42d47-123">Em vez disso, você ativa a Qualidade de Serviço configurando intervalos de porta e, em seguida, criando e aplicando a Política de grupo.</span><span class="sxs-lookup"><span data-stu-id="42d47-123">Instead, you enable Quality of Service by configuring port ranges and then creating and applying Group Policy.</span></span> <span data-ttu-id="42d47-124">Se decidir posteriormente não usar a QoS, você pode “desativar” a Qualidade de Serviço removendo os objetos de Política de grupo apropriados.</span><span class="sxs-lookup"><span data-stu-id="42d47-124">If you later decide not to use QoS you can “disable” Quality of Service simply by removing the appropriate Group Policy objects.</span></span>

  - <span data-ttu-id="42d47-125">[Configurando intervalos de portas para seus servidores de borda no Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="42d47-125">[Configuring port ranges for your Edge Servers in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span></span> <span data-ttu-id="42d47-126">Embora não seja necessário, você pode configurar seus servidores de borda para usar os mesmos intervalos de porta que os outros servidores.</span><span class="sxs-lookup"><span data-stu-id="42d47-126">Although not required, you can configure your Edge servers to use the same port ranges as your other servers.</span></span>

  - <span data-ttu-id="42d47-127">[Configurando intervalos de portas para seus clientes Microsoft Lync no Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="42d47-127">[Configuring port ranges for your Microsoft Lync clients in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span></span> <span data-ttu-id="42d47-128">Esses intervalos de porta se aplicam somente a computadores cliente e normalmente não são os mesmos que os intervalos de porta configurados em seus servidores.</span><span class="sxs-lookup"><span data-stu-id="42d47-128">These port ranges apply only to client computers and are typically not the same as the port ranges configured on your servers.</span></span>

  - <span data-ttu-id="42d47-129">[Configuração de uma política de qualidade de serviço no Lync Server 2013 para seus servidores de conferência, aplicativos e mediação](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span><span class="sxs-lookup"><span data-stu-id="42d47-129">[Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="42d47-130">Essas políticas determinam os códigos DSCP que são aplicados a tipos de pacotes diferentes.</span><span class="sxs-lookup"><span data-stu-id="42d47-130">These policies determine the DSCP codes that are applied to different packet types.</span></span>

  - <span data-ttu-id="42d47-131">[Configurando uma política de qualidade de serviço para seus servidores de borda a/V no Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="42d47-131">[Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span></span> <span data-ttu-id="42d47-132">Isso deve ser executado somente para o lado interno de seus servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="42d47-132">This should only be done for the internal side of your Edge servers.</span></span> <span data-ttu-id="42d47-133">Isso ocorre pois a Qualidade do Serviço foi projetada para uso em sua rede interna e não na Internet.</span><span class="sxs-lookup"><span data-stu-id="42d47-133">That's because Quality of Service is designed for use on your internal network and not on the Internet.</span></span>

  - <span data-ttu-id="42d47-134">[Configuração de políticas de qualidade de serviço no Lync Server 2013 para clientes que executam o Windows 7 ou Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span><span class="sxs-lookup"><span data-stu-id="42d47-134">[Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span></span> <span data-ttu-id="42d47-135">Observe que o Microsoft Lync Server 2013 não oferece suporte a QoS para outros sistemas operacionais Windows, como o Windows Vista ou o Windows XP.</span><span class="sxs-lookup"><span data-stu-id="42d47-135">Note that Microsoft Lync Server 2013 does not support QoS for other Windows operating systems, such as Windows Vista or Windows XP.</span></span>

  - <span data-ttu-id="42d47-136">[Configurando a qualidade de serviço nos dispositivos do Microsoft Lync Phone Edition no Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span><span class="sxs-lookup"><span data-stu-id="42d47-136">[Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span></span> <span data-ttu-id="42d47-137">Por padrão, a QoS é habilitada para dispositivos do Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="42d47-137">By default, QoS is enabled for Lync Phone Edition devices.</span></span> <span data-ttu-id="42d47-138">No entanto, pode ser necessário alterar o valor padrão de DSCP para garantir que todos os pacotes de áudio em sua organização usem o mesmo código de DSCP.</span><span class="sxs-lookup"><span data-stu-id="42d47-138">However, you might want to change the default DSCP value in order to ensure that all audio packets in your organization use the same DSCP code.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42d47-139">Se você estiver usando o Microsoft Windows Server 2012 ou o Windows Server 2012 R2, você pode estar interessado no novo conjunto de cmdlets do Windows PowerShell disponíveis para o gerenciamento da qualidade de serviço nessa plataforma.</span><span class="sxs-lookup"><span data-stu-id="42d47-139">If you are using Microsoft Windows Server 2012 or Windows Server 2012 R2 you might be interested in the new set of Windows PowerShell cmdlets available for managing Quality of Service on that platform.</span></span> <span data-ttu-id="42d47-140">Para obter mais informações, consulte Network Quality of Service cmdlets in Windows PowerShell [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)em.</span><span class="sxs-lookup"><span data-stu-id="42d47-140">For more information, see Network Quality of Service Cmdlets in Windows PowerShell at [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

