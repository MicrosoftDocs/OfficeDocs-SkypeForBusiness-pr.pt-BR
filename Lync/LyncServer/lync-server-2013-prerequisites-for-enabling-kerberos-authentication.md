---
title: 'Lync Server 2013: Pré-requisitos para habilitar autenticação Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f405daa37007bffba1e02bd10d20d4de907e820e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="021f0-102">Pré-requisitos para habilitar autenticação Kerberos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="021f0-102">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="021f0-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="021f0-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="021f0-104">Antes de habilitar a autenticação Kerberos, certifique-se de concluir todas as preparações de configuração e infraestrutura:</span><span class="sxs-lookup"><span data-stu-id="021f0-104">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="021f0-105">O esquema do Active Directory é estendido para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="021f0-105">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="021f0-106">A preparação da floresta do Active Directory é concluída para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="021f0-106">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="021f0-107">A preparação do domínio do Active Directory foi concluída para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="021f0-107">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="021f0-108">O repositório de gerenciamento central foi instalado e está disponível com êxito.</span><span class="sxs-lookup"><span data-stu-id="021f0-108">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="021f0-109">A topologia foi criada e publicada usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="021f0-109">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="021f0-110">Os servidores e funções que exigem serviços Web foram definidos e implantados, incluindo servidores front-end, servidores de edição padrão e directors.</span><span class="sxs-lookup"><span data-stu-id="021f0-110">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="021f0-111">Os serviços de informações da Internet (IIS) são configurados e implantados com os serviços de função recomendados para dar suporte a serviços Web no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="021f0-111">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="021f0-112">Depois que os pré-requisitos forem atendidos, você deve estar pronto para criar uma ou mais contas para serviços Web a serem usados para a autenticação Kerberos para a implantação.</span><span class="sxs-lookup"><span data-stu-id="021f0-112">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="021f0-113">No mínimo, você precisa criar uma conta de autenticação Kerberos para cada implantação.</span><span class="sxs-lookup"><span data-stu-id="021f0-113">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="021f0-114">No entanto, você pode criar uma conta para cada site para fornecer autenticação Kerberos local no site.</span><span class="sxs-lookup"><span data-stu-id="021f0-114">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="021f0-115">Você só pode especificar uma conta de autenticação Kerberos por site.</span><span class="sxs-lookup"><span data-stu-id="021f0-115">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

