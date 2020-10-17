---
title: 'Lync Server 2013: requisitos técnicos para o grupo de resposta'
description: 'Lync Server 2013: requisitos técnicos para o grupo de resposta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3125ed8c732960e23970229e99bf5a8487eb96a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550317"
---
# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="1da70-103">Requisitos técnicos para o grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1da70-103">Technical requirements for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1da70-104">_**Última modificação do tópico:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="1da70-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="1da70-105">Esta seção descreve os seguintes requisitos técnicos para o aplicativo de grupo de resposta:</span><span class="sxs-lookup"><span data-stu-id="1da70-105">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="1da70-106">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="1da70-106">Hardware requirements</span></span>

  - <span data-ttu-id="1da70-107">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="1da70-107">Software requirements</span></span>

  - <span data-ttu-id="1da70-108">Requisitos de porta</span><span class="sxs-lookup"><span data-stu-id="1da70-108">Port requirements</span></span>

  - <span data-ttu-id="1da70-109">Requisitos do arquivo de áudio</span><span class="sxs-lookup"><span data-stu-id="1da70-109">Audio file requirements</span></span>

  - <span data-ttu-id="1da70-110">Requisitos da ferramenta de configuração do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="1da70-110">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="1da70-111">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="1da70-111">Hardware Requirements</span></span>

<span data-ttu-id="1da70-112">O aplicativo grupo de resposta tem os mesmos requisitos de hardware que os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="1da70-112">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="1da70-113">Para obter detalhes sobre os requisitos de hardware, consulte [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="1da70-113">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="1da70-114">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="1da70-114">Software Requirements</span></span>

<span data-ttu-id="1da70-115">O aplicativo grupo de resposta tem os mesmos requisitos de sistema operacional e pré-requisitos de software que os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="1da70-115">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="1da70-116">Para obter detalhes sobre os requisitos de software, consulte [Server and Tools Operating System support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="1da70-116">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="1da70-117">Se você usar os arquivos de áudio do Windows Media (. WMA) para o grupo de resposta e anúncios, todos os servidores front-end ou servidores Standard Editions que executam o aplicativo de grupo de resposta deverão ter o tempo de execução do Windows Media Format instalado para servidores executando o Windows Server 2008 R2 ou o Microsoft Media Foundation para servidores executando o Windows Server 2012 ou o Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1da70-117">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="1da70-118">Para o Windows Server 2008 R2, o tempo de execução do Windows Media Format é instalado como parte da experiência da área de trabalho do Windows.</span><span class="sxs-lookup"><span data-stu-id="1da70-118">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="1da70-119">Para mais detalhes sobre requisitos de áudio, consulte "Requisitos de arquivo de áudio" mais adiante nesta seção.</span><span class="sxs-lookup"><span data-stu-id="1da70-119">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="1da70-120">Requisitos de porta</span><span class="sxs-lookup"><span data-stu-id="1da70-120">Port Requirements</span></span>

<span data-ttu-id="1da70-121">O aplicativo grupo de resposta usa as seguintes portas:</span><span class="sxs-lookup"><span data-stu-id="1da70-121">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="1da70-122">**Porta 5071**     Usado para solicitações de escuta SIP</span><span class="sxs-lookup"><span data-stu-id="1da70-122">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="1da70-123">**Porta 8404**     Usado para comunicações entre servidores</span><span class="sxs-lookup"><span data-stu-id="1da70-123">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1da70-124">Essa porta é usada para o serviço de correspondência e é obrigatório quando o aplicativo grupo de resposta é implantado em um pool que tem mais de um servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="1da70-124">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="1da70-125">Essas portas são as configurações padrão que podem ser alteradas com o uso do cmdlet <STRONG>Set-CsApplicationServer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1da70-125">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="1da70-126">Para obter detalhes sobre esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1da70-126">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="1da70-127">Requisitos do arquivo de áudio</span><span class="sxs-lookup"><span data-stu-id="1da70-127">Audio File Requirements</span></span>

<span data-ttu-id="1da70-128">O aplicativo de grupo de resposta suporta o formato de arquivo Wave (. wav) e o formato de arquivo de áudio do Windows Media (. WMA) para mensagens do grupo de resposta, música em espera ou perguntas de resposta de voz interativa (IVR).</span><span class="sxs-lookup"><span data-stu-id="1da70-128">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="1da70-129">O formato de arquivo de áudio do Windows Media requer que o tempo de execução do Windows Media Format esteja instalado em servidores front-end executando o Windows Server 2008 R2 e o Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="1da70-129">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="1da70-130">Para mais detalhes, consulte "Requisitos de software", anteriormente nesta seção.</span><span class="sxs-lookup"><span data-stu-id="1da70-130">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="1da70-131">Formatos de arquivo wave suportados</span><span class="sxs-lookup"><span data-stu-id="1da70-131">Supported Wave File Formats</span></span>

<span data-ttu-id="1da70-132">Todos os arquivos wave devem atender aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="1da70-132">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="1da70-133">Arquivo de 8 ou 16 bits</span><span class="sxs-lookup"><span data-stu-id="1da70-133">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="1da70-134">Formato de modulação de código de pulso linear (LPCM), A-Law ou mu-Law</span><span class="sxs-lookup"><span data-stu-id="1da70-134">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="1da70-135">Mono ou estéreo</span><span class="sxs-lookup"><span data-stu-id="1da70-135">Mono or stereo</span></span>

  - <span data-ttu-id="1da70-136">4 MB ou menos</span><span class="sxs-lookup"><span data-stu-id="1da70-136">4MB or less</span></span>

<span data-ttu-id="1da70-137">Para o melhor desempenho de arquivos wave, um  arquivo Wave mono, de 16 kHz e 16 bits é recomendado.</span><span class="sxs-lookup"><span data-stu-id="1da70-137">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="1da70-138">Formatos de arquivo de áudio Windows Media</span><span class="sxs-lookup"><span data-stu-id="1da70-138">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="1da70-139">Se você utilizar um arquivo de áudio Windows Media, considere utilizar taxas de bit baixos e verifique o desempenho do sistema sob carga.</span><span class="sxs-lookup"><span data-stu-id="1da70-139">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="1da70-140">Você pode utilizar o Microsoft Expression Encoder 4 para converter um arquivo para o formato Windows Media Audio.</span><span class="sxs-lookup"><span data-stu-id="1da70-140">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="1da70-141">Para baixar o Expression Encoder 4, consulte [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) .</span><span class="sxs-lookup"><span data-stu-id="1da70-141">To download Expression Encoder 4, see [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="1da70-142">Requisitos de ferramenta de configuração de Grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="1da70-142">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="1da70-143">A ferramenta de configuração do grupo de resposta oferece suporte às combinações de sistemas operacionais e navegadores da Web descritos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="1da70-143">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1da70-p107">Há suporte para as versões de 32 bits e 64 bits dos sistemas operacionais. Somente versões de 32 bits do Internet Explorer são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="1da70-p107">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="1da70-146">Sistemas operacionais e navegadores da Web suportados</span><span class="sxs-lookup"><span data-stu-id="1da70-146">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1da70-147">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="1da70-147">Operating system</span></span></th>
<th><span data-ttu-id="1da70-148">Navegador da Web</span><span class="sxs-lookup"><span data-stu-id="1da70-148">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1da70-149">Windows Vista com Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="1da70-149">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="1da70-150">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="1da70-150">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="1da70-151">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="1da70-151">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="1da70-152">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="1da70-152">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1da70-153">Windows 7</span><span class="sxs-lookup"><span data-stu-id="1da70-153">Windows 7</span></span></p>
<p><span data-ttu-id="1da70-154">Windows 7 com Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="1da70-154">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="1da70-155">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="1da70-155">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="1da70-156">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="1da70-156">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1da70-157">Windows Server 2008 com Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="1da70-157">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="1da70-158">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="1da70-158">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="1da70-159">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="1da70-159">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="1da70-160">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="1da70-160">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1da70-161">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="1da70-161">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="1da70-162">Windows Server 2008 R2 com Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="1da70-162">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="1da70-163">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="1da70-163">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="1da70-164">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="1da70-164">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="1da70-165">Console de agente do Grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="1da70-165">Response Group Agent Console</span></span>

<span data-ttu-id="1da70-166">O console de agente suporta as combinações de sistemas operacionais e navegadores da web descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="1da70-166">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1da70-p108">Versões 32 bits ou 64 bits do sistema operacional são suportadas. Apenas versões 32 bits do Internet Explorer são suportadas.</span><span class="sxs-lookup"><span data-stu-id="1da70-p108">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="1da70-169">Sistemas operacionais e navegadores da Web suportados</span><span class="sxs-lookup"><span data-stu-id="1da70-169">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1da70-170">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="1da70-170">Operating system</span></span></th>
<th><span data-ttu-id="1da70-171">Navegador da Web</span><span class="sxs-lookup"><span data-stu-id="1da70-171">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1da70-172">Windows Vista com Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="1da70-172">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="1da70-173">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="1da70-173">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="1da70-174">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="1da70-174">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="1da70-175">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="1da70-175">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1da70-176">Windows 7</span><span class="sxs-lookup"><span data-stu-id="1da70-176">Windows 7</span></span></p>
<p><span data-ttu-id="1da70-177">Windows 7 com Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="1da70-177">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="1da70-178">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="1da70-178">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="1da70-179">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="1da70-179">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="1da70-180">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="1da70-180">Firefox 10.0</span></span></p>
<p><span data-ttu-id="1da70-181">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="1da70-181">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1da70-182">Windows Server 2008 com Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="1da70-182">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="1da70-183">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="1da70-183">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="1da70-184">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="1da70-184">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="1da70-185">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="1da70-185">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1da70-186">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="1da70-186">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="1da70-187">Windows Server 2008 R2 com Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="1da70-187">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="1da70-188">Internet Explorer 8 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="1da70-188">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="1da70-189">Internet Explorer 9 (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="1da70-189">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="1da70-190">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="1da70-190">Firefox 10.0</span></span></p>
<p><span data-ttu-id="1da70-191">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="1da70-191">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

