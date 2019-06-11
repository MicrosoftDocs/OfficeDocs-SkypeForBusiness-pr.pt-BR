---
title: 'Lync Server 2013: Solicitar certificados com antecedência (opcional)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6b376a2c1652dcaf255e39f6d112568b7c3bf31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a><span data-ttu-id="922eb-102">Solicitar certificados com antecedência (opcional) para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="922eb-102">Request certificates in advance (optional) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="922eb-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="922eb-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="922eb-104">Os certificados são necessários para todos os servidores internos que executam o Lync Server 2013, incluindo cada servidor front-end Enterprise Edition, servidor Standard Edition, diretor, servidor de borda e servidor de mediação autônomo.</span><span class="sxs-lookup"><span data-stu-id="922eb-104">Certificates are required for all internal servers that are running Lync Server 2013, including each Enterprise Edition Front End Server, Standard Edition server, Director, Edge Server and stand-alone Mediation Server.</span></span> <span data-ttu-id="922eb-105">Embora uma CA (autoridade de certificação) corporativa interna seja recomendada para servidores internos, você também pode usar uma CA pública.</span><span class="sxs-lookup"><span data-stu-id="922eb-105">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="922eb-106">Para obter detalhes sobre os requisitos de certificado e sobre o uso de uma autoridade de certificação pública, consulte [requisitos de certificado para servidores internos no Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="922eb-106">For details about certificate requirements and about the use of a public CA, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="922eb-107">A instalação do Lync Server 2013 inclui o assistente de certificado, que facilita as tarefas de solicitação, atribuição e instalação de certificados durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="922eb-107">Lync Server 2013 setup includes the Certificate Wizard, which facilitates the tasks of requesting, assigning, and installing certificates during deployment.</span></span> <span data-ttu-id="922eb-108">Se você quiser solicitar certificados antes de instalar os servidores (por exemplo, para economizar tempo durante a implantação real de servidores), poderá fazer isso usando um computador no qual as ferramentas administrativas do Lync Server 2013 estão instaladas ou usando uma solicitação de certificado procedimento definido em sua organização, desde que você certifique-se de que os certificados sejam exportáveis e contenham todos os nomes alternativos de assunto obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="922eb-108">If you want to request certificates prior to installing servers (for instance, to save time during actual deployment of servers), you can do so by using a computer on which the Lync Server 2013 administrative tools are installed or by using a certificate request procedure defined in your organization, as long as you make sure that the certificates are exportable and contain all the required subject alternative names.</span></span> <span data-ttu-id="922eb-109">Solicitar certificados antecipadamente é opcional.</span><span class="sxs-lookup"><span data-stu-id="922eb-109">Requesting certificates in advance is optional.</span></span> <span data-ttu-id="922eb-110">Se você não solicitá-los antecipadamente, será necessário solicitá-los como parte da configuração de cada servidor que exija um certificado.</span><span class="sxs-lookup"><span data-stu-id="922eb-110">If you do not request them in advance, you must request them as part of the setup of each server that requires a certificate.</span></span>

<span data-ttu-id="922eb-111">Esta documentação de implantação fornece procedimentos para usar o assistente de certificado para solicitar certificados como parte do processo de configuração, conforme descrito em [configurar certificados para servidores no Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [configurar certificados para o Diretor no Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md)e [Instale os arquivos do servidor de mediação no lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) seções desta documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="922eb-111">This Deployment documentation provides procedures for using the Certificate Wizard to request certificates as part of the setup process, as described in the [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md), and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) sections of this Deployment documentation.</span></span> <span data-ttu-id="922eb-112">Se você solicitar certificados com antecedência, será preciso modificar os procedimentos de implantação de certificado nessas seções, conforme apropriado, para importar e atribuir os certificados em vez de solicitá-los no momento da implantação.</span><span class="sxs-lookup"><span data-stu-id="922eb-112">If you request certificates in advance, you must modify the certificate deployment procedures in those sections as appropriate to importing and assigning the certificates instead of requesting them at the time of deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="922eb-113">O Lync Server 2013 inclui suporte para certificados SHA-256 para conexões de clientes que executam os sistemas operacionais&nbsp;Windows Vista, windows&nbsp;Server&nbsp;2008, Windows Server 2008 R2 e Windows 7 e o Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="922eb-113">Lync Server 2013 includes support for SHA-256 certificates for connections from clients running the Windows Vista, Windows Server&nbsp;2008, Windows Server&nbsp;2008&nbsp;R2, and Windows 7 operating systems, and Lync Phone Edition.</span></span> <span data-ttu-id="922eb-114">Para dar suporte ao acesso externo usando SHA-256, o certificado externo é emitido por uma autoridade de certificação pública que usa SHA-256.</span><span class="sxs-lookup"><span data-stu-id="922eb-114">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

