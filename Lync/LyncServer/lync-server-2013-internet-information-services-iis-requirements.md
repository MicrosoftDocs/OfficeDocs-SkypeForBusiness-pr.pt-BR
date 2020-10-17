---
title: 'Lync Server 2013: requisitos dos serviços de informações da Internet (IIS)'
description: 'Lync Server 2013: requisitos dos serviços de informações da Internet (IIS).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd8de55fa4611c3ab29eac7d7c28c522b418e77d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543987"
---
# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="28cee-103">Requisitos dos serviços de informações da Internet (IIS) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28cee-103">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28cee-104">_**Última modificação do tópico:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="28cee-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="28cee-105">Vários componentes do Lync Server 2013 exigem serviços de informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="28cee-105">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="28cee-106">Este tópico descreve os recursos específicos do IIS necessários para oferecer suporte ao Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28cee-106">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="28cee-107">Os tópicos desta seção descrevem os requisitos de componentes específicos para o IIS.</span><span class="sxs-lookup"><span data-stu-id="28cee-107">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="28cee-p102">Quando a função Servidor Web (IIS) está habilitada no Windows Server 2008, vários serviços de função são instalados por padrão. A tabela a seguir descreve os serviços de função adicionais que devem ser instalados quando a função Servidor Web (IIS) está habilitada no Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="28cee-p102">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default. The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="28cee-110">Serviço de função</span><span class="sxs-lookup"><span data-stu-id="28cee-110">Role service</span></span></th>
<th><span data-ttu-id="28cee-111">Recurso</span><span class="sxs-lookup"><span data-stu-id="28cee-111">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28cee-112">Recursos de HTTP comuns</span><span class="sxs-lookup"><span data-stu-id="28cee-112">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="28cee-113">Redirecionamento HTTP</span><span class="sxs-lookup"><span data-stu-id="28cee-113">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28cee-114">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="28cee-114">Application Development</span></span></p></td>
<td><p><span data-ttu-id="28cee-115">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="28cee-115">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28cee-116">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="28cee-116">Application Development</span></span></p></td>
<td><p><span data-ttu-id="28cee-117">Extensibilidade .NET</span><span class="sxs-lookup"><span data-stu-id="28cee-117">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28cee-118">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="28cee-118">Application Development</span></span></p></td>
<td><p><span data-ttu-id="28cee-119">Extensões ISAPI</span><span class="sxs-lookup"><span data-stu-id="28cee-119">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28cee-120">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="28cee-120">Application Development</span></span></p></td>
<td><p><span data-ttu-id="28cee-121">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="28cee-121">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28cee-122">Integridade e Diagnósticos</span><span class="sxs-lookup"><span data-stu-id="28cee-122">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="28cee-123">Ferramentas de log</span><span class="sxs-lookup"><span data-stu-id="28cee-123">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28cee-124">Integridade e Diagnósticos</span><span class="sxs-lookup"><span data-stu-id="28cee-124">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="28cee-125">Rastreia</span><span class="sxs-lookup"><span data-stu-id="28cee-125">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28cee-126">Segurança</span><span class="sxs-lookup"><span data-stu-id="28cee-126">Security</span></span></p></td>
<td><p><span data-ttu-id="28cee-127">Autenticação básica</span><span class="sxs-lookup"><span data-stu-id="28cee-127">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28cee-128">Segurança</span><span class="sxs-lookup"><span data-stu-id="28cee-128">Security</span></span></p></td>
<td><p><span data-ttu-id="28cee-129">Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="28cee-129">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28cee-130">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="28cee-130">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="28cee-131">Ferramentas e scripts de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="28cee-131">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28cee-132">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="28cee-132">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="28cee-133">Compatibilidade com gerenciamento do IIS 6</span><span class="sxs-lookup"><span data-stu-id="28cee-133">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="segurança" alt="security" /><span data-ttu-id="28cee-135">Observação de segurança:</span><span class="sxs-lookup"><span data-stu-id="28cee-135">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="28cee-136">Se você estiver usando o IIS 7,0 em um sistema operacional Windows Server 2008, a instalação do Lync Server desabilita a autenticação de modo kernel no IIS.</span><span class="sxs-lookup"><span data-stu-id="28cee-136">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="28cee-137">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="28cee-137">In This Section</span></span>

  - [<span data-ttu-id="28cee-138">Requisitos de IIS para pools front-end e servidores Standard Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28cee-138">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

