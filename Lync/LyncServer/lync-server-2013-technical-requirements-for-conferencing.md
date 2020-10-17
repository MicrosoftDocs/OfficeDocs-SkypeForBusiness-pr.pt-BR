---
title: Requisitos técnicos do Lync Server 2013 para conferência
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
ms.openlocfilehash: d28afb699b63ee3523c7b5d4ae31bf9153459abf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533938"
---
# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="f30cc-102">Requisitos técnicos para conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f30cc-102">Technical requirements for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f30cc-103">_**Última modificação do tópico:** 2014-06-25_</span><span class="sxs-lookup"><span data-stu-id="f30cc-103">_**Topic Last Modified:** 2014-06-25_</span></span>

<span data-ttu-id="f30cc-104">Para Lync Server 2013, conferência discada, conferência de A/V, recursos de conferência de mensagens instantâneas (IM) e webconferência sempre são executados em servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="f30cc-104">For Lync Server 2013, dial-in conferencing, A/V conferencing, instant messaging (IM) conferencing and web conferencing capabilities always run on Front End Servers.</span></span>

<span data-ttu-id="f30cc-105">Esta seção detalha os requisitos de hardware e software para esses servidores, juntamente com a colocação de suporte.</span><span class="sxs-lookup"><span data-stu-id="f30cc-105">This section details the hardware and software requirements for these servers, along with the supported collocation.</span></span>

<span data-ttu-id="f30cc-106">A conferência discada é um recurso que contém vários componentes.</span><span class="sxs-lookup"><span data-stu-id="f30cc-106">Dial-in conferencing is a feature that includes a variety of components.</span></span> <span data-ttu-id="f30cc-107">Alguns destes componentes são específicos para conferência discada e alguns são componentes do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="f30cc-107">Some of the components are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="f30cc-108">Esta seção descreve os requisitos para os componentes específicos para a conferência discada.</span><span class="sxs-lookup"><span data-stu-id="f30cc-108">This section describes the requirements for the components that are specific to dial-in conferencing.</span></span> <span data-ttu-id="f30cc-109">Para obter detalhes sobre o servidor de mediação e os requisitos de gateway PSTN (rede telefônica pública comutada), consulte [Mediation Server Component in Lync server 2013](lync-server-2013-mediation-server-component.md) e [components for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="f30cc-109">For details about Mediation Server and public switched telephone network (PSTN) gateway requirements, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) and [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="f30cc-110">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="f30cc-110">Hardware Requirements</span></span>

<span data-ttu-id="f30cc-111">Como a conferência da Web e a conferência A/V são colocadas com o servidor front-end, os requisitos de hardware do servidor são os mesmos dos servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="f30cc-111">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server hardware requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="f30cc-112">Para obter detalhes sobre os requisitos de hardware, consulte [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="f30cc-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="f30cc-113">Os seguintes componentes necessários para a conferência discada também têm os mesmos requisitos de hardware que os servidores front-end:</span><span class="sxs-lookup"><span data-stu-id="f30cc-113">The following components required for dial-in conferencing also have the same hardware requirements as Front End Servers:</span></span>

  - <span data-ttu-id="f30cc-114">Serviço de aplicativos</span><span class="sxs-lookup"><span data-stu-id="f30cc-114">Application service</span></span>

  - <span data-ttu-id="f30cc-115">Aplicativo Atendedor de Conferência</span><span class="sxs-lookup"><span data-stu-id="f30cc-115">Conferencing Attendant application</span></span>

  - <span data-ttu-id="f30cc-116">Aplicativo Comunicado de Conferência</span><span class="sxs-lookup"><span data-stu-id="f30cc-116">Conferencing Announcement application</span></span>

<span data-ttu-id="f30cc-117">Os requisitos de hardware para o servidor front-end são os mesmos que para muitas outras funções de servidor no Lync Server 2013 são descritos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f30cc-117">The hardware requirements for Front End Server are the same as for many other server roles in Lync Server 2013 are outlined in the following table.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="f30cc-118">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="f30cc-118">Software Requirements</span></span>

<span data-ttu-id="f30cc-119">Como a conferência da Web e a conferência A/V são colocadas com o servidor front-end, os requisitos de software do servidor são os mesmos dos servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="f30cc-119">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server software requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="f30cc-120">Para obter detalhes sobre os requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="f30cc-120">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="f30cc-121">Para webconferência, o Lync Server 2013 também requer o Office Web Apps e o Office Web Apps Server (anteriormente conhecido como servidor WAC) para lidar com apresentações do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="f30cc-121">For web conferencing, Lync Server 2013 also requires Office Web Apps and the Office Web Apps Server (formerly known as WAC Server) to handle PowerPoint presentations.</span></span> <span data-ttu-id="f30cc-122">Para obter detalhes, consulte [Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="f30cc-122">For details, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="f30cc-123">Para conferência discada, o serviço de aplicativo, o aplicativo de atendedor de conferência e o aplicativo de anúncio de conferência têm os mesmos requisitos do sistema operacional que os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="f30cc-123">For dial-in conferencing, Application service, Conferencing Attendant application, and Conferencing Announcement application have the same operating system requirements as Front End Servers.</span></span> <span data-ttu-id="f30cc-124">Para obter detalhes sobre os requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="f30cc-124">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="f30cc-125">Aplicativo de atendedor de conferência e anúncio de conferência o aplicativo exige que o Windows Media Format Runtime esteja instalado em servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="f30cc-125">Conferencing Attendant application and Conferencing Announcement application require that Windows Media Format Runtime is installed on Front End Servers.</span></span> <span data-ttu-id="f30cc-126">O Tempo de Execução do Windows Media Format é exigido para reproduzir arquivos WMA (áudio do Windows Media) que são usados parar músicas em espera, nomes registrados e avisos.</span><span class="sxs-lookup"><span data-stu-id="f30cc-126">The Windows Media Format Runtime is required to play Windows Media audio (WMA) files that are used for music on hold, recorded names, and prompts.</span></span> <span data-ttu-id="f30cc-127">Exceto para o Windows Server 2012 e o Windows Server 2012 R2, o tempo de execução do Windows Media Format é instalado automaticamente como parte da experiência da área de trabalho do Windows ao executar a instalação, mas talvez seja necessário reiniciar o computador.</span><span class="sxs-lookup"><span data-stu-id="f30cc-127">Except for Windows Server 2012 and Windows Server 2012 R2, the Windows Media Format Runtime is installed automatically as part of the Windows Desktop Experience when you run Setup, but you might need to restart the computer.</span></span> <span data-ttu-id="f30cc-128">Portanto, é recomendável fazer a instalação como parte da Experiência de Desktop do Windows, que inclui o Tempo de Execução do Windows Media Format, antes de executar a Instalação.</span><span class="sxs-lookup"><span data-stu-id="f30cc-128">Therefore, we recommend that you install as part of the Windows Desktop Experience, which includes Windows Media Format Runtime before you run Setup.</span></span> <span data-ttu-id="f30cc-129">O Windows Server 2012 e o Windows Server 2012 R2 exigem o Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="f30cc-129">Windows Server 2012 and Windows Server 2012 R2 requires Microsoft Media Foundation.</span></span>

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a><span data-ttu-id="f30cc-130">Requisitos de porta para a conferência discada</span><span class="sxs-lookup"><span data-stu-id="f30cc-130">Port Requirements for dial-in conferencing</span></span>

<span data-ttu-id="f30cc-p107">A tabela a seguir descreve as portas que são usadas pela conferência discada. Se estiver usando um balanceador de carga, verifique se ele está configurado para as portas usadas por todos os aplicativos que serão executados no pool.</span><span class="sxs-lookup"><span data-stu-id="f30cc-p107">The following table describes the ports that are used by dial-in conferencing. If you use a load balancer, ensure that the load balancer is configured for the ports used by any applications that will run in the pool.</span></span>

<span data-ttu-id="f30cc-133">Essas portas são as configurações padrão que podem ser alteradas com o uso do cmdlet **Set-CsApplicationServer**.</span><span class="sxs-lookup"><span data-stu-id="f30cc-133">These ports are default settings that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="f30cc-134">Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f30cc-134">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f30cc-135">Todas as instâncias do mesmo aplicativo em um pool usam a mesma porta de escuta SIP.</span><span class="sxs-lookup"><span data-stu-id="f30cc-135">All instances of the same application in a pool use the same SIP listening port.</span></span>



</div>

### <a name="ports-used-by-dial-in-conferencing"></a><span data-ttu-id="f30cc-136">Portas usadas pelas conferência discada</span><span class="sxs-lookup"><span data-stu-id="f30cc-136">Ports used by dial-in conferencing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f30cc-137">Número da porta</span><span class="sxs-lookup"><span data-stu-id="f30cc-137">Port number</span></span></th>
<th><span data-ttu-id="f30cc-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="f30cc-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f30cc-139">5072</span><span class="sxs-lookup"><span data-stu-id="f30cc-139">5072</span></span></p></td>
<td><p><span data-ttu-id="f30cc-140">Usado pelo aplicativo de atendedor de conferência para solicitações de escuta SIP</span><span class="sxs-lookup"><span data-stu-id="f30cc-140">Used by Conferencing Attendant application for SIP listening requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f30cc-141">5073</span><span class="sxs-lookup"><span data-stu-id="f30cc-141">5073</span></span></p></td>
<td><p><span data-ttu-id="f30cc-142">Usado pelo aplicativo comunicado de conferência para solicitações de escuta SIP</span><span class="sxs-lookup"><span data-stu-id="f30cc-142">Used by Conferencing Announcement application for SIP listening requests</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a><span data-ttu-id="f30cc-143">Clientes suportados para conferência discada</span><span class="sxs-lookup"><span data-stu-id="f30cc-143">Supported Clients for Dial-In Conferencing</span></span>

<span data-ttu-id="f30cc-144">É possível usar o seguinte cliente para agendar conferências locais que dão suporte ao acesso discado:</span><span class="sxs-lookup"><span data-stu-id="f30cc-144">You can use the following client to schedule on-premises conferences that support dial-in access:</span></span>

  - <span data-ttu-id="f30cc-145">Suplemento de reunião online para Lync 2013 (instalado automaticamente quando você instala o Lync 2013 ou participante)</span><span class="sxs-lookup"><span data-stu-id="f30cc-145">Online Meeting Add-in for Lync 2013 (installed automatically when you install Lync 2013 or Attendee)</span></span>

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a><span data-ttu-id="f30cc-146">Requisitos da página de configurações de conferência discada</span><span class="sxs-lookup"><span data-stu-id="f30cc-146">Dial-in Conferencing Settings page Requirements</span></span>

<span data-ttu-id="f30cc-147">A página de configurações de conferência discada suporta as combinações de sistemas operacionais e navegadores da Web descritos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f30cc-147">The Dial-in Conferencing Settings page supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f30cc-148">Versões de 32 bits e 64 bits dos sistemas operacionais são suportadas.</span><span class="sxs-lookup"><span data-stu-id="f30cc-148">32-bit and 64-bit versions of the operating systems are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="f30cc-149">Sistemas operacionais e navegadores da Web suportados</span><span class="sxs-lookup"><span data-stu-id="f30cc-149">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f30cc-150">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="f30cc-150">Operating system</span></span></th>
<th><span data-ttu-id="f30cc-151">Navegador da Web</span><span class="sxs-lookup"><span data-stu-id="f30cc-151">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f30cc-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="f30cc-152">Windows 7</span></span></p></td>
<td><p><span data-ttu-id="f30cc-153">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="f30cc-153">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="f30cc-154">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="f30cc-154">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="f30cc-155">Firefox</span><span class="sxs-lookup"><span data-stu-id="f30cc-155">Firefox</span></span></p></td>
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
<td><p><span data-ttu-id="f30cc-156">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="f30cc-156">Windows Server 2008 R2</span></span></p></td>
<td><p><span data-ttu-id="f30cc-157">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="f30cc-157">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="f30cc-158">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="f30cc-158">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="f30cc-159">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="f30cc-159">Internet Explorer 7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f30cc-160">Mac OS</span><span class="sxs-lookup"><span data-stu-id="f30cc-160">Mac OS</span></span></p></td>
<td><p><span data-ttu-id="f30cc-161">Firefox</span><span class="sxs-lookup"><span data-stu-id="f30cc-161">Firefox</span></span></p>
<p><span data-ttu-id="f30cc-162">Safari</span><span class="sxs-lookup"><span data-stu-id="f30cc-162">Safari</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a><span data-ttu-id="f30cc-163">Requisitos de arquivo de áudio para conferência discada</span><span class="sxs-lookup"><span data-stu-id="f30cc-163">Audio File Requirements for dial-in conferencing</span></span>

<span data-ttu-id="f30cc-164">O Lync Server 2013 não é compatível com a personalização de prompts de voz e música para conferência discada.</span><span class="sxs-lookup"><span data-stu-id="f30cc-164">Lync Server 2013 does not support customization of voice prompts and music for dial-in conferencing.</span></span> <span data-ttu-id="f30cc-165">No entanto, se você tiver uma forte necessidade de negócios que exija a alteração dos arquivos de áudio padrão, consulte o artigo 961177 da base de dados de conhecimento da Microsoft, [como personalizar prompts de voz ou arquivos de música para conferência de áudio de discagem no Microsoft Office Communications Server 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span><span class="sxs-lookup"><span data-stu-id="f30cc-165">However, if you have a strong business need that requires you to change the default audio files, see Microsoft Knowledge Base article 961177, [How to customize voice prompts or music files for dial-in audio conferencing in Microsoft Office Communications Server 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span></span>

<span data-ttu-id="f30cc-166">Você também pode usar o utilitário de gerenciamento de [voz personalizado do atendedor de conferência do Microsoft Lync Server](https://go.microsoft.com/fwlink/p/?linkid=396880) , que permite aos administradores substituir os prompts de voz padrão usados quando um chamador de telefone ingressar em uma reunião do Lync com prompts personalizados para fornecer uma experiência de entrada de reunião diferente.</span><span class="sxs-lookup"><span data-stu-id="f30cc-166">You can also use the [Microsoft Lync Server Conferencing Attendant Custom Voice Prompts](https://go.microsoft.com/fwlink/p/?linkid=396880) management utility, which enables administrators to replace the default voice prompts used when a phone caller joins a Lync meeting with custom prompts to provide a different meeting entry experience.</span></span> <span data-ttu-id="f30cc-167">Os prompts de voz personalizados podem ser instalados em um servidor que esteja executando o Lync Server 2010 ou o Lync Server 2013, Enterprise ou Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f30cc-167">The custom voice prompts can be installed on a server that is running Lync Server 2010 or Lync Server 2013, either Enterprise or Standard Edition.</span></span>

<span data-ttu-id="f30cc-168">O aplicativo atendedor de conferência e anúncio de conferência têm os seguintes requisitos para arquivos de música em espera, nomes gravados e prompts de áudio:</span><span class="sxs-lookup"><span data-stu-id="f30cc-168">Conferencing Attendant application and Conferencing Announcement application have the following requirements for music on hold, recorded name, and audio prompt files:</span></span>

  - <span data-ttu-id="f30cc-169">Formato de arquivo WMA (áudio do Windows Media)</span><span class="sxs-lookup"><span data-stu-id="f30cc-169">Windows Media Audio (WMA) file format</span></span>

  - <span data-ttu-id="f30cc-170">16 bits mono</span><span class="sxs-lookup"><span data-stu-id="f30cc-170">16-bit mono</span></span>

  - <span data-ttu-id="f30cc-171">48 kbps 2-pass CBR (taxa de bits constante)</span><span class="sxs-lookup"><span data-stu-id="f30cc-171">48 kbps 2-pass CBR (constant bit rate)</span></span>

  - <span data-ttu-id="f30cc-172">Nível da fala a -24 DB</span><span class="sxs-lookup"><span data-stu-id="f30cc-172">Speech level at -24DB</span></span>

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a><span data-ttu-id="f30cc-173">Requisitos do usuário para conferência discada</span><span class="sxs-lookup"><span data-stu-id="f30cc-173">User Requirements for Dial-In Conferencing</span></span>

<span data-ttu-id="f30cc-174">Os usuários de conferências discadas devem ter um número de telefone ou extensão exclusivos atribuídos à respectiva conta.</span><span class="sxs-lookup"><span data-stu-id="f30cc-174">Dial-in conferencing users must have a unique phone number or extension assigned to their account.</span></span> <span data-ttu-id="f30cc-175">Este requisito oferece suporte à autenticação durante a conferência discada.</span><span class="sxs-lookup"><span data-stu-id="f30cc-175">This requirement supports authentication during dial-in conferencing.</span></span> <span data-ttu-id="f30cc-176">Usuários corporativos (ou seja, usuários que têm credenciais de serviços de domínio do Active Directory e contas do Lync Server em sua organização) inserem seus números de telefone (ou ramal) e um número de identificação pessoal (PIN) para discar para conferências como um usuário autenticado.</span><span class="sxs-lookup"><span data-stu-id="f30cc-176">Enterprise users (that is, users who have Active Directory Domain Services credentials and Lync Server accounts within your organization) enter their phone number (or extension) and a personal identification number (PIN) to dial in to conferences as an authenticated user.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

