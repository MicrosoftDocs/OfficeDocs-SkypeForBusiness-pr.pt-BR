---
title: 'Lync Server 2013: Requisitos de Serviços de Informações da Internet (IIS)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcb0350178a19a75ac821a452ef90e10da297677
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="40b87-102">Requisitos de Serviços de Informações da Internet (IIS) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40b87-102">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40b87-103">_**Tópico da última modificação:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="40b87-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="40b87-104">Vários componentes do Lync Server 2013 exigem serviços de informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="40b87-104">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="40b87-105">Este tópico descreve os recursos específicos do IIS necessários para dar suporte ao Lync Server.</span><span class="sxs-lookup"><span data-stu-id="40b87-105">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="40b87-106">Os tópicos desta seção descrevem os requisitos de componentes específicos para o IIS.</span><span class="sxs-lookup"><span data-stu-id="40b87-106">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="40b87-107">Quando a função servidor Web (IIS) estiver habilitada no Windows Server 2008, vários serviços de função serão instalados por padrão.</span><span class="sxs-lookup"><span data-stu-id="40b87-107">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default.</span></span> <span data-ttu-id="40b87-108">A tabela a seguir descreve os serviços de função adicionais que devem ser instalados quando a função do servidor Web (IIS) estiver habilitada no Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="40b87-108">The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40b87-109">Serviço de função</span><span class="sxs-lookup"><span data-stu-id="40b87-109">Role service</span></span></th>
<th><span data-ttu-id="40b87-110">Recurso</span><span class="sxs-lookup"><span data-stu-id="40b87-110">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40b87-111">Recursos HTTP Comuns</span><span class="sxs-lookup"><span data-stu-id="40b87-111">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="40b87-112">Redirecionamento de HTTP</span><span class="sxs-lookup"><span data-stu-id="40b87-112">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b87-113">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="40b87-113">Application Development</span></span></p></td>
<td><p><span data-ttu-id="40b87-114">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="40b87-114">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40b87-115">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="40b87-115">Application Development</span></span></p></td>
<td><p><span data-ttu-id="40b87-116">Extensibilidade .NET</span><span class="sxs-lookup"><span data-stu-id="40b87-116">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b87-117">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="40b87-117">Application Development</span></span></p></td>
<td><p><span data-ttu-id="40b87-118">Extensões ISAPI</span><span class="sxs-lookup"><span data-stu-id="40b87-118">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40b87-119">Desenvolvimento do aplicativo</span><span class="sxs-lookup"><span data-stu-id="40b87-119">Application Development</span></span></p></td>
<td><p><span data-ttu-id="40b87-120">Filtros ISAPI</span><span class="sxs-lookup"><span data-stu-id="40b87-120">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b87-121">Integridade e Diagnósticos</span><span class="sxs-lookup"><span data-stu-id="40b87-121">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="40b87-122">Ferramentas de log</span><span class="sxs-lookup"><span data-stu-id="40b87-122">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40b87-123">Integridade e Diagnósticos</span><span class="sxs-lookup"><span data-stu-id="40b87-123">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="40b87-124">Rastreamento</span><span class="sxs-lookup"><span data-stu-id="40b87-124">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b87-125">Segurança</span><span class="sxs-lookup"><span data-stu-id="40b87-125">Security</span></span></p></td>
<td><p><span data-ttu-id="40b87-126">Autenticação básica</span><span class="sxs-lookup"><span data-stu-id="40b87-126">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40b87-127">Segurança</span><span class="sxs-lookup"><span data-stu-id="40b87-127">Security</span></span></p></td>
<td><p><span data-ttu-id="40b87-128">Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="40b87-128">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b87-129">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="40b87-129">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="40b87-130">Ferramentas e scripts de gerenciamento IIS</span><span class="sxs-lookup"><span data-stu-id="40b87-130">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40b87-131">Ferramentas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="40b87-131">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="40b87-132">Compatibilidade com gerenciamento do IIS 6</span><span class="sxs-lookup"><span data-stu-id="40b87-132">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="segurança" alt="security" /><span data-ttu-id="40b87-134">Observação de segurança:</span><span class="sxs-lookup"><span data-stu-id="40b87-134">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="40b87-135">Se você estiver usando o IIS 7,0 em um sistema operacional Windows Server 2008, a instalação do Lync Server desabilitará a autenticação do modo kernel no IIS.</span><span class="sxs-lookup"><span data-stu-id="40b87-135">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="40b87-136">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="40b87-136">In This Section</span></span>

  - [<span data-ttu-id="40b87-137">Requisitos de IIS para pools Front-End pools e servidores Standard Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40b87-137">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

