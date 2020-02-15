---
title: 'Lync Server 2013: servidores de borda de áudio/vídeo (A/V)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1262ee1a2db12569538f499731de53a9da133c98
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="f19ef-102">Servidores de borda de áudio/vídeo (A/V) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f19ef-102">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f19ef-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f19ef-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f19ef-p101">O Serviço de borda A/V fornece uma maneira para que seus usuários internos (usuários conectados à sua rede organizacional) compartilhem áudio e vídeo com usuários externos (usuários que não estão conectados à rede organizacional). Além de áudio e vídeo, o serviço de borda A/V fornece suporte para o compartilhamento de área de trabalho e a transferência de arquivos.</span><span class="sxs-lookup"><span data-stu-id="f19ef-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). In addition to audio and video, the A/V Edge service also provides support for such things desktop sharing and file transfer.</span></span>

<span data-ttu-id="f19ef-p102">O serviço de borda A/V é gerenciado principalmente usando a configuração de borda A/V; essas configurações permitem que você gerencie a quantidade máxima de largura de banda que será alocada por porta e usuário, bem como para especificar por quanto tempo um token de autenticação pode ser usado antes de precisar renová-lo. As definições de configuração de borda A/V podem ser aplicadas a sites ou servidores de borda A/V individuais. Ao determinar qual conjunto de configurações terá prioridade, use o seguinte guia:</span><span class="sxs-lookup"><span data-stu-id="f19ef-p102">The A/V Edge service is primarily managed by using A/V Edge configuration; these settings enable you to manage the maximum amount of bandwidth to be allocated per port and per user, and to specify the length of time that an authentication token can be used before that token must be renewed. A/V Edge configuration settings can be applied to sites or to individual A/V Edge servers. When determining which collection of settings will take priority, use the following guide:</span></span>

  - <span data-ttu-id="f19ef-109">As definições configuradas no escopo de serviço (isto é, em um servidor individual ) têm prioridade sobre tudo.</span><span class="sxs-lookup"><span data-stu-id="f19ef-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="f19ef-p103">As definições configuradas no escopo do site têm prioridade sobre as definições configuradas no escopo global. No entanto, as definições de escopo de serviço também substituem as configurações de escopo do site.</span><span class="sxs-lookup"><span data-stu-id="f19ef-p103">Settings configured at the site scope take priority over settings configured at the global scope. However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="f19ef-112">As configurações no escopo global serão usadas somente se não há definições de serviço configuradas no servidor individual e se não há configurações de site para o site onde o servidor está localizado.</span><span class="sxs-lookup"><span data-stu-id="f19ef-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="f19ef-113">O serviço de borda A/V só pode ser gerenciado com o uso do Lync Server PowerShell e dos cmdlets CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f19ef-113">The A/V Edge service can only be managed by using Lync Server PowerShell and the CsAVEdgeConfiguration cmdlets.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f19ef-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="f19ef-114">In This Section</span></span>

  - [<span data-ttu-id="f19ef-115">Retornar as informações de configuração do servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f19ef-115">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [<span data-ttu-id="f19ef-116">Criar ou modificar uma coleção de definições de configuração de servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f19ef-116">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [<span data-ttu-id="f19ef-117">Excluir um conjunto existente de definições de configuração de servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f19ef-117">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

