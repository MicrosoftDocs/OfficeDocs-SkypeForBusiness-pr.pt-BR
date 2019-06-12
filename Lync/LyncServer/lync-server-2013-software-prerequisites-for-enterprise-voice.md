---
title: 'Lync Server 2013: Pré-requisitos de software para Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ac981d7a30a85d25d2dfb376cfa34f812e898bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="5ecce-102">Pré-requisitos de software para Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ecce-102">Software prerequisites for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ecce-103">_**Tópico da última modificação:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="5ecce-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="5ecce-104">Verifique se a infraestrutura na qual você pretende implantar o Enterprise Voice atende aos seguintes pré-requisitos de software:</span><span class="sxs-lookup"><span data-stu-id="5ecce-104">Verify that the infrastructure in which you intend to deploy Enterprise Voice meets the following software prerequisites:</span></span>

  - <span data-ttu-id="5ecce-105">O Lync Server 2013 Standard Edition ou Enterprise Edition está instalado e operacional em sua rede.</span><span class="sxs-lookup"><span data-stu-id="5ecce-105">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="5ecce-106">Todos os servidores de borda são implantados e operacionais em sua rede de perímetro, incluindo os servidores de borda executando o serviço de borda de acesso, o serviço de borda A/V, o serviço de borda de Webconferência e um proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="5ecce-106">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers running Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="5ecce-107">O Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 ou Microsoft Exchange Server 2013 é necessário para integrar a Unificação de mensagens do Exchange ao Lync Server e para fornecer notificações avançadas e informações de registro de chamadas para o Pontos de extremidade do Lync.</span><span class="sxs-lookup"><span data-stu-id="5ecce-107">Either Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 or Microsoft Exchange Server 2013 is required for integrating Exchange Unified Messaging with Lync Server and to provide rich notifications and call log information to the Lync endpoints.</span></span>

  - <span data-ttu-id="5ecce-108">Um ou mais usuários foram criados e habilitados para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5ecce-108">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="5ecce-109">Os clientes e dispositivos do Lync foram implantados com êxito.</span><span class="sxs-lookup"><span data-stu-id="5ecce-109">Lync clients and devices have been successfully deployed.</span></span>

  - <span data-ttu-id="5ecce-110">O construtor de topologias está instalado em um servidor na sua rede.</span><span class="sxs-lookup"><span data-stu-id="5ecce-110">Topology Builder is installed on a server on your network.</span></span>

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a><span data-ttu-id="5ecce-111">Próximas etapas: verificar pré-requisitos de segurança e configuração</span><span class="sxs-lookup"><span data-stu-id="5ecce-111">Next Steps: Verify Security and Configuration Prerequisites</span></span>

<span data-ttu-id="5ecce-112">Depois de verificar os pré-requisitos de software para o Enterprise Voice, você pode usar a documentação para continuar preparando-se para a implantação do Enterprise Voice:</span><span class="sxs-lookup"><span data-stu-id="5ecce-112">After verifying software prerequisites for Enterprise Voice, you can use the documentation to continue preparing for deploying Enterprise Voice:</span></span>

1.  <span data-ttu-id="5ecce-113">Verifique a segurança, a configuração do usuário e as perquisites de hardware, conforme descrito em [pré-requisitos de configuração e segurança para o Enterprise Voice no Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="5ecce-113">Verify security, user configuration, and hardware perquisites, as described in [Security and configuration prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).</span></span>

2.  <span data-ttu-id="5ecce-114">Instale o servidor de mediação, conforme descrito em [instalar os arquivos para o servidor de mediação no Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), mas *somente* se você quiser implantar um servidor ou pool autônomo de mediação porque os servidores de mediação são instalados como parte do pool de front-ends ou Processo de implantação do servidor Standard Edition quando posicionado.</span><span class="sxs-lookup"><span data-stu-id="5ecce-114">Install the Mediation Server, as described in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), but *only* if you want to deploy a stand-alone Mediation Server or pool because Mediation Servers are installed as part of the Front End pool or Standard Edition server deployment process when collocated.</span></span>

3.  <span data-ttu-id="5ecce-115">Configure conexões de tronco para fornecer conectividade PSTN para usuários, conforme descrito em Configurando [troncos no Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="5ecce-115">Configure trunk connections to provide PSTN connectivity for users, as described in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

