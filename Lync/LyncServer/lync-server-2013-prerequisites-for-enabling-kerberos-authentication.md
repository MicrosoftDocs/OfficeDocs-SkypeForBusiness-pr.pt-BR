---
title: 'Lync Server 2013: pré-requisitos para habilitar a autenticação Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5fa366ae27126ead478d66c3beb091581158d1a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="02ecf-102">Pré-requisitos para habilitar a autenticação Kerberos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02ecf-102">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02ecf-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="02ecf-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="02ecf-104">Antes de habilitar a autenticação Kerberos, verifique se você concluiu todas as preparações de configuração e preparação de pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="02ecf-104">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="02ecf-105">O esquema do Active Directory é estendido para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="02ecf-105">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="02ecf-106">A preparação da floresta do Active Directory foi concluída para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="02ecf-106">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="02ecf-107">A preparação do domínio do Active Directory foi concluída para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="02ecf-107">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="02ecf-108">O repositório de gerenciamento central está instalado e disponível com êxito.</span><span class="sxs-lookup"><span data-stu-id="02ecf-108">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="02ecf-109">A topologia foi criada e publicada usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="02ecf-109">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="02ecf-110">Os servidores e as funções que exigem serviços Web foram definidos e implantados, incluindo servidores front-end, servidores Standard Edition e diretores.</span><span class="sxs-lookup"><span data-stu-id="02ecf-110">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="02ecf-111">O IIS (serviços de informações da Internet) é configurado e implantado com os serviços de função recomendados para dar suporte a serviços Web no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="02ecf-111">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="02ecf-112">Depois que os pré-requisitos forem atendidos, você deve estar pronto para criar uma ou mais contas para serviços Web a serem usados para a autenticação Kerberos para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="02ecf-112">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="02ecf-113">No mínimo, você precisa criar uma conta de autenticação Kerberos para cada implantação.</span><span class="sxs-lookup"><span data-stu-id="02ecf-113">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="02ecf-114">No entanto, você pode criar uma conta para cada site, a fim de fornecer a autenticação Kerberos local no site.</span><span class="sxs-lookup"><span data-stu-id="02ecf-114">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="02ecf-115">Você só pode especificar uma conta de autenticação Kerberos por site.</span><span class="sxs-lookup"><span data-stu-id="02ecf-115">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

