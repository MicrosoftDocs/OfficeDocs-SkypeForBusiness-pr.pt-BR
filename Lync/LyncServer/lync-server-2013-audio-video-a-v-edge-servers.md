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
ms.openlocfilehash: c99cc3522c13ece937c6e2a0ba06f995431e08d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="5dcdb-102">Servidores de borda de áudio/vídeo (A/V) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5dcdb-102">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5dcdb-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5dcdb-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5dcdb-104">O serviço de borda A/V fornece uma maneira para seus usuários internos (usuários que estão conectados à sua rede organizacional) para compartilhar áudio e vídeo com usuários externos (usuários que não estão conectados à sua rede organizacional).</span><span class="sxs-lookup"><span data-stu-id="5dcdb-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="5dcdb-105">Além de áudio e vídeo, o serviço de borda A/V também oferece suporte para tarefas de compartilhamento de área de trabalho e transferência de arquivos.</span><span class="sxs-lookup"><span data-stu-id="5dcdb-105">In addition to audio and video, the A/V Edge service also provides support for such things desktop sharing and file transfer.</span></span>

<span data-ttu-id="5dcdb-106">O serviço de borda A/V é gerenciado principalmente usando-se A configuração de borda A/V; essas configurações permitem que você gerencie a quantidade máxima de largura de banda a ser alocada por porta e por usuário e especifique o período de tempo que um token de autenticação pode ser usado antes de o token ser renovado.</span><span class="sxs-lookup"><span data-stu-id="5dcdb-106">The A/V Edge service is primarily managed by using A/V Edge configuration; these settings enable you to manage the maximum amount of bandwidth to be allocated per port and per user, and to specify the length of time that an authentication token can be used before that token must be renewed.</span></span> <span data-ttu-id="5dcdb-107">As configurações de borda a/V podem ser aplicadas a sites ou a servidores de borda A/V individuais.</span><span class="sxs-lookup"><span data-stu-id="5dcdb-107">A/V Edge configuration settings can be applied to sites or to individual A/V Edge servers.</span></span> <span data-ttu-id="5dcdb-108">Ao determinar quais conjuntos de configurações terão prioridade, use o seguinte guia:</span><span class="sxs-lookup"><span data-stu-id="5dcdb-108">When determining which collection of settings will take priority, use the following guide:</span></span>

  - <span data-ttu-id="5dcdb-109">As configurações definidas no escopo do serviço (ou seja, em um servidor individual) têm prioridade sobre tudo.</span><span class="sxs-lookup"><span data-stu-id="5dcdb-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="5dcdb-110">As configurações definidas no escopo do site têm prioridade sobre as configurações definidas no escopo global.</span><span class="sxs-lookup"><span data-stu-id="5dcdb-110">Settings configured at the site scope take priority over settings configured at the global scope.</span></span> <span data-ttu-id="5dcdb-111">No entanto, as configurações de escopo do serviço também substituirão as configurações de escopo do site.</span><span class="sxs-lookup"><span data-stu-id="5dcdb-111">However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="5dcdb-112">As configurações no escopo global serão usadas apenas se não houver configurações de serviço configuradas no servidor individual e se não houver configurações de site para o site em que o servidor está localizado.</span><span class="sxs-lookup"><span data-stu-id="5dcdb-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="5dcdb-113">O serviço de borda A/V só pode ser gerenciado usando o Lync Server PowerShell e os cmdlets CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="5dcdb-113">The A/V Edge service can only be managed by using Lync Server PowerShell and the CsAVEdgeConfiguration cmdlets.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5dcdb-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="5dcdb-114">In This Section</span></span>

  - [<span data-ttu-id="5dcdb-115">Retornar as informações de configuração do servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5dcdb-115">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [<span data-ttu-id="5dcdb-116">Criar ou modificar um conjunto de configurações de servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5dcdb-116">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [<span data-ttu-id="5dcdb-117">Excluir uma coleção existente de configurações de servidor de borda A/V no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5dcdb-117">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

