---
title: 'Lync Server 2013: Requisitos técnicos para conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a275836b940cfe2c56b184d238bc12c432132e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="c10ba-102">Requisitos técnicos para conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c10ba-102">Technical requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c10ba-103">_**Tópico da última modificação:** 2014-06-25_</span><span class="sxs-lookup"><span data-stu-id="c10ba-103">_**Topic Last Modified:** 2014-06-25_</span></span>

<span data-ttu-id="c10ba-104">Para o Lync Server 2013, conferência discada, conferência A/V, conferências de mensagens instantâneas e recursos de Webconferência sempre são executados em servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="c10ba-104">For Lync Server 2013, dial-in conferencing, A/V conferencing, instant messaging (IM) conferencing and web conferencing capabilities always run on Front End Servers.</span></span>

<span data-ttu-id="c10ba-105">Esta seção detalha os requisitos de hardware e software para esses servidores, além da colocação de suporte.</span><span class="sxs-lookup"><span data-stu-id="c10ba-105">This section details the hardware and software requirements for these servers, along with the supported collocation.</span></span>

<span data-ttu-id="c10ba-106">A conferência discada é um recurso que inclui diversos componentes.</span><span class="sxs-lookup"><span data-stu-id="c10ba-106">Dial-in conferencing is a feature that includes a variety of components.</span></span> <span data-ttu-id="c10ba-107">Alguns dos componentes são específicos para conferência discada e alguns são componentes do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c10ba-107">Some of the components are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="c10ba-108">Esta seção descreve os requisitos para os componentes específicos da conferência discada.</span><span class="sxs-lookup"><span data-stu-id="c10ba-108">This section describes the requirements for the components that are specific to dial-in conferencing.</span></span> <span data-ttu-id="c10ba-109">Para obter detalhes sobre o servidor de mediação e requisitos de gateway PSTN (rede telefônica pública comutada), consulte [componente servidor de mediação no Lync server 2013](lync-server-2013-mediation-server-component.md) e [componentes e topologias do servidor de mediação no Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="c10ba-109">For details about Mediation Server and public switched telephone network (PSTN) gateway requirements, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) and [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="c10ba-110">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="c10ba-110">Hardware Requirements</span></span>

<span data-ttu-id="c10ba-111">Como a conferência da Web e conferência A/V são posicionadas com o servidor front-end, os requisitos de hardware do servidor são os mesmos para os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="c10ba-111">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server hardware requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="c10ba-112">Para obter detalhes sobre os requisitos de hardware, consulte [plataformas de hardware do servidor para o Lync Server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="c10ba-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="c10ba-113">Os seguintes componentes necessários para a conferência discada também têm os mesmos requisitos de hardware que os servidores front-end:</span><span class="sxs-lookup"><span data-stu-id="c10ba-113">The following components required for dial-in conferencing also have the same hardware requirements as Front End Servers:</span></span>

  - <span data-ttu-id="c10ba-114">Serviço de aplicativos</span><span class="sxs-lookup"><span data-stu-id="c10ba-114">Application service</span></span>

  - <span data-ttu-id="c10ba-115">Aplicativo Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="c10ba-115">Conferencing Attendant application</span></span>

  - <span data-ttu-id="c10ba-116">Aplicativo Comunicado de Conferência</span><span class="sxs-lookup"><span data-stu-id="c10ba-116">Conferencing Announcement application</span></span>

<span data-ttu-id="c10ba-117">Os requisitos de hardware para front-end Server são os mesmos para muitas outras funções de servidor no Lync Server 2013 são descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c10ba-117">The hardware requirements for Front End Server are the same as for many other server roles in Lync Server 2013 are outlined in the following table.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="c10ba-118">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="c10ba-118">Software Requirements</span></span>

<span data-ttu-id="c10ba-119">Como a conferência da Web e conferência A/V estão posicionadas com o servidor front-end, os requisitos de software do servidor são os mesmos para os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="c10ba-119">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server software requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="c10ba-120">Para obter detalhes sobre os requisitos de software, consulte [suporte ao sistema operacional do servidor e ferramentas no Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="c10ba-120">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="c10ba-121">Para webconferência, o Lync Server 2013 também requer o Office Web Apps e o Office Web Apps Server (anteriormente conhecido como WAC Server) para manipular apresentações do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="c10ba-121">For web conferencing, Lync Server 2013 also requires Office Web Apps and the Office Web Apps Server (formerly known as WAC Server) to handle PowerPoint presentations.</span></span> <span data-ttu-id="c10ba-122">Para obter detalhes, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="c10ba-122">For details, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="c10ba-123">Para conferência discada, serviço de aplicativo, aplicativo atendedor de conferência e aplicativo de anúncio de conferência têm os mesmos requisitos de sistema operacional que os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="c10ba-123">For dial-in conferencing, Application service, Conferencing Attendant application, and Conferencing Announcement application have the same operating system requirements as Front End Servers.</span></span> <span data-ttu-id="c10ba-124">Para obter detalhes sobre os requisitos de software, consulte [suporte ao sistema operacional do servidor e ferramentas no Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="c10ba-124">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="c10ba-125">Aplicativo de atendedor de conferência o aplicativo de anúncio de conferência requer que o tempo de execução do Windows Media Format seja instalado em servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="c10ba-125">Conferencing Attendant application and Conferencing Announcement application require that Windows Media Format Runtime is installed on Front End Servers.</span></span> <span data-ttu-id="c10ba-126">O tempo de execução do Windows Media Format é necessário para reproduzir arquivos de áudio do Windows Media (WMA) usados para música em espera, nomes gravados e solicitações.</span><span class="sxs-lookup"><span data-stu-id="c10ba-126">The Windows Media Format Runtime is required to play Windows Media audio (WMA) files that are used for music on hold, recorded names, and prompts.</span></span> <span data-ttu-id="c10ba-127">Com exceção do Windows Server 2012 e do Windows Server 2012 R2, o tempo de execução do Windows Media Format é instalado automaticamente como parte da experiência da área de trabalho do Windows quando você executa a instalação, mas talvez seja necessário reiniciar o computador.</span><span class="sxs-lookup"><span data-stu-id="c10ba-127">Except for Windows Server 2012 and Windows Server 2012 R2, the Windows Media Format Runtime is installed automatically as part of the Windows Desktop Experience when you run Setup, but you might need to restart the computer.</span></span> <span data-ttu-id="c10ba-128">Portanto, recomendamos que você instale como parte da experiência da área de trabalho do Windows, que inclui o tempo de execução do Windows Media Format antes de executar a instalação.</span><span class="sxs-lookup"><span data-stu-id="c10ba-128">Therefore, we recommend that you install as part of the Windows Desktop Experience, which includes Windows Media Format Runtime before you run Setup.</span></span> <span data-ttu-id="c10ba-129">O Windows Server 2012 e o Windows Server 2012 R2 exigem o Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="c10ba-129">Windows Server 2012 and Windows Server 2012 R2 requires Microsoft Media Foundation.</span></span>

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a><span data-ttu-id="c10ba-130">Requisitos de porta para conferência discada</span><span class="sxs-lookup"><span data-stu-id="c10ba-130">Port Requirements for dial-in conferencing</span></span>

<span data-ttu-id="c10ba-131">A tabela a seguir descreve as portas usadas pela conferência discada.</span><span class="sxs-lookup"><span data-stu-id="c10ba-131">The following table describes the ports that are used by dial-in conferencing.</span></span> <span data-ttu-id="c10ba-132">Se você usar um balanceador de carga, certifique-se de que o balanceador de carga está configurado para as portas usadas por quaisquer aplicativos que serão executados no pool.</span><span class="sxs-lookup"><span data-stu-id="c10ba-132">If you use a load balancer, ensure that the load balancer is configured for the ports used by any applications that will run in the pool.</span></span>

<span data-ttu-id="c10ba-133">Essas portas são configurações padrão que podem ser alteradas usando o cmdlet **set-CsApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="c10ba-133">These ports are default settings that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="c10ba-134">Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c10ba-134">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c10ba-135">Todas as instâncias do mesmo aplicativo em um pool usam a mesma porta de escuta SIP.</span><span class="sxs-lookup"><span data-stu-id="c10ba-135">All instances of the same application in a pool use the same SIP listening port.</span></span>



</div>

### <a name="ports-used-by-dial-in-conferencing"></a><span data-ttu-id="c10ba-136">Portas usadas pela conferência discada</span><span class="sxs-lookup"><span data-stu-id="c10ba-136">Ports used by dial-in conferencing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c10ba-137">Número da porta</span><span class="sxs-lookup"><span data-stu-id="c10ba-137">Port number</span></span></th>
<th><span data-ttu-id="c10ba-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="c10ba-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c10ba-139">5072</span><span class="sxs-lookup"><span data-stu-id="c10ba-139">5072</span></span></p></td>
<td><p><span data-ttu-id="c10ba-140">Usado pelo aplicativo de assistente de conferência para solicitações de escuta SIP</span><span class="sxs-lookup"><span data-stu-id="c10ba-140">Used by Conferencing Attendant application for SIP listening requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c10ba-141">5073</span><span class="sxs-lookup"><span data-stu-id="c10ba-141">5073</span></span></p></td>
<td><p><span data-ttu-id="c10ba-142">Usado pelo aplicativo de anúncio de conferência para solicitações de escuta SIP</span><span class="sxs-lookup"><span data-stu-id="c10ba-142">Used by Conferencing Announcement application for SIP listening requests</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a><span data-ttu-id="c10ba-143">Clientes com suporte para conferência discada</span><span class="sxs-lookup"><span data-stu-id="c10ba-143">Supported Clients for Dial-In Conferencing</span></span>

<span data-ttu-id="c10ba-144">Você pode usar o seguinte cliente para programar conferências locais que dão suporte ao acesso de discagem:</span><span class="sxs-lookup"><span data-stu-id="c10ba-144">You can use the following client to schedule on-premises conferences that support dial-in access:</span></span>

  - <span data-ttu-id="c10ba-145">Suplemento de reunião online do Lync 2013 (instalado automaticamente quando você instala o Lync 2013 ou participante)</span><span class="sxs-lookup"><span data-stu-id="c10ba-145">Online Meeting Add-in for Lync 2013 (installed automatically when you install Lync 2013 or Attendee)</span></span>

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a><span data-ttu-id="c10ba-146">Requisitos da página de configurações de conferência discada</span><span class="sxs-lookup"><span data-stu-id="c10ba-146">Dial-in Conferencing Settings page Requirements</span></span>

<span data-ttu-id="c10ba-147">A página Configurações de conferência discada aceita as combinações de sistemas operacionais e navegadores da Web descritos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c10ba-147">The Dial-in Conferencing Settings page supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c10ba-148">Há suporte para as versões de 32 bits e 64 bits dos sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="c10ba-148">32-bit and 64-bit versions of the operating systems are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="c10ba-149">Navegadores da Web e sistemas operacionais com suporte</span><span class="sxs-lookup"><span data-stu-id="c10ba-149">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c10ba-150">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="c10ba-150">Operating system</span></span></th>
<th><span data-ttu-id="c10ba-151">Navegador da Web</span><span class="sxs-lookup"><span data-stu-id="c10ba-151">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c10ba-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="c10ba-152">Windows 7</span></span></p></td>
<td><p><span data-ttu-id="c10ba-153">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="c10ba-153">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="c10ba-154">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="c10ba-154">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="c10ba-155">Firefox</span><span class="sxs-lookup"><span data-stu-id="c10ba-155">Firefox</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c10ba-156">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="c10ba-156">Windows Server 2008 R2</span></span></p></td>
<td><p><span data-ttu-id="c10ba-157">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="c10ba-157">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="c10ba-158">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="c10ba-158">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="c10ba-159">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="c10ba-159">Internet Explorer 7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c10ba-160">Mac OS</span><span class="sxs-lookup"><span data-stu-id="c10ba-160">Mac OS</span></span></p></td>
<td><p><span data-ttu-id="c10ba-161">Firefox</span><span class="sxs-lookup"><span data-stu-id="c10ba-161">Firefox</span></span></p>
<p><span data-ttu-id="c10ba-162">Safari</span><span class="sxs-lookup"><span data-stu-id="c10ba-162">Safari</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a><span data-ttu-id="c10ba-163">Requisitos de arquivo de áudio para conferência discada</span><span class="sxs-lookup"><span data-stu-id="c10ba-163">Audio File Requirements for dial-in conferencing</span></span>

<span data-ttu-id="c10ba-164">O Lync Server 2013 não é compatível com a personalização de prompts de voz e música para conferência discada.</span><span class="sxs-lookup"><span data-stu-id="c10ba-164">Lync Server 2013 does not support customization of voice prompts and music for dial-in conferencing.</span></span> <span data-ttu-id="c10ba-165">No entanto, se você tiver uma forte necessidade empresarial que exija a alteração dos arquivos de áudio padrão, consulte o artigo 961177 da base de dados de conhecimento Microsoft, [como personalizar prompts de voz ou arquivos de música para conferências de áudio discadas no Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span><span class="sxs-lookup"><span data-stu-id="c10ba-165">However, if you have a strong business need that requires you to change the default audio files, see Microsoft Knowledge Base article 961177, [How to customize voice prompts or music files for dial-in audio conferencing in Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span></span>

<span data-ttu-id="c10ba-166">Você também pode usar o utilitário de gerenciamento de [solicitações de voz personalizado do atendedor do Microsoft Lync Server](http://go.microsoft.com/fwlink/p/?linkid=396880) , que permite aos administradores substituir as solicitações de voz padrão usadas quando um chamador de telefone ingressar em uma reunião do Lync com avisos personalizados para fornecer uma experiência de entrada de reunião diferente.</span><span class="sxs-lookup"><span data-stu-id="c10ba-166">You can also use the [Microsoft Lync Server Conferencing Attendant Custom Voice Prompts](http://go.microsoft.com/fwlink/p/?linkid=396880) management utility, which enables administrators to replace the default voice prompts used when a phone caller joins a Lync meeting with custom prompts to provide a different meeting entry experience.</span></span> <span data-ttu-id="c10ba-167">Os prompts de voz personalizados podem ser instalados em um servidor que esteja executando o Lync Server 2010 ou o Lync Server 2013, Enterprise ou Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c10ba-167">The custom voice prompts can be installed on a server that is running Lync Server 2010 or Lync Server 2013, either Enterprise or Standard Edition.</span></span>

<span data-ttu-id="c10ba-168">Aplicativo de atendedor de conferência o aplicativo de anúncio de conferência tem os seguintes requisitos para músicas em espera, nomes gravados e arquivos de prompt de áudio:</span><span class="sxs-lookup"><span data-stu-id="c10ba-168">Conferencing Attendant application and Conferencing Announcement application have the following requirements for music on hold, recorded name, and audio prompt files:</span></span>

  - <span data-ttu-id="c10ba-169">Formato de arquivo WMA (áudio do Windows Media)</span><span class="sxs-lookup"><span data-stu-id="c10ba-169">Windows Media Audio (WMA) file format</span></span>

  - <span data-ttu-id="c10ba-170">16 bits mono</span><span class="sxs-lookup"><span data-stu-id="c10ba-170">16-bit mono</span></span>

  - <span data-ttu-id="c10ba-171">48 kbps 2-pass CBR (taxa de bits constante)</span><span class="sxs-lookup"><span data-stu-id="c10ba-171">48 kbps 2-pass CBR (constant bit rate)</span></span>

  - <span data-ttu-id="c10ba-172">Nível da fala a -24 DB</span><span class="sxs-lookup"><span data-stu-id="c10ba-172">Speech level at -24DB</span></span>

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a><span data-ttu-id="c10ba-173">Requisitos do usuário para conferência discada</span><span class="sxs-lookup"><span data-stu-id="c10ba-173">User Requirements for Dial-In Conferencing</span></span>

<span data-ttu-id="c10ba-174">Os usuários de conferências discadas devem ter um número de telefone ou extensão exclusivos atribuídos à respectiva conta.</span><span class="sxs-lookup"><span data-stu-id="c10ba-174">Dial-in conferencing users must have a unique phone number or extension assigned to their account.</span></span> <span data-ttu-id="c10ba-175">Este requisito oferece suporte à autenticação durante a conferência discada.</span><span class="sxs-lookup"><span data-stu-id="c10ba-175">This requirement supports authentication during dial-in conferencing.</span></span> <span data-ttu-id="c10ba-176">Usuários corporativos (ou seja, os usuários que têm credenciais de serviços de domínio Active Directory e contas do Lync Server em sua organização) inserem o número de telefone (ou ramal) e um número de identificação pessoal (PIN) para discar para conferências como um usuário autenticado.</span><span class="sxs-lookup"><span data-stu-id="c10ba-176">Enterprise users (that is, users who have Active Directory Domain Services credentials and Lync Server accounts within your organization) enter their phone number (or extension) and a personal identification number (PIN) to dial in to conferences as an authenticated user.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

