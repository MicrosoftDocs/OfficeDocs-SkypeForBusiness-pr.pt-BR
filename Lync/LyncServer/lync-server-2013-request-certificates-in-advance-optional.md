---
title: 'Lync Server 2013: solicitar certificados com antecedência (opcional)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7e671fe61f5d8b9e43593bf99e0ecf0e1e37109
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511958"
---
# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a><span data-ttu-id="41591-102">Solicitar certificados com antecedência (opcional) para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41591-102">Request certificates in advance (optional) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41591-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="41591-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="41591-104">Os certificados são necessários para todos os servidores internos que executam o Lync Server 2013, incluindo cada servidor de front-ends Enterprise Edition, servidor Standard Edition, diretor, servidor de borda e servidor de mediação autônomo.</span><span class="sxs-lookup"><span data-stu-id="41591-104">Certificates are required for all internal servers that are running Lync Server 2013, including each Enterprise Edition Front End Server, Standard Edition server, Director, Edge Server and stand-alone Mediation Server.</span></span> <span data-ttu-id="41591-105">Embora uma autoridade de certificação empresarial interna seja recomendada para servidores internos, você também pode usar uma autoridade de certificação pública.</span><span class="sxs-lookup"><span data-stu-id="41591-105">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="41591-106">Para obter detalhes sobre os requisitos de certificado e sobre o uso de uma AC pública, consulte [Certificate Requirements for Internal Servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="41591-106">For details about certificate requirements and about the use of a public CA, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="41591-107">O programa de instalação do Lync Server 2013 inclui o assistente de certificado, que facilita as tarefas de solicitação, atribuição e instalação de certificados durante a implantação.</span><span class="sxs-lookup"><span data-stu-id="41591-107">Lync Server 2013 setup includes the Certificate Wizard, which facilitates the tasks of requesting, assigning, and installing certificates during deployment.</span></span> <span data-ttu-id="41591-108">Se você quiser solicitar certificados antes de instalar servidores (por exemplo, para economizar tempo durante a implantação real de servidores), poderá fazer isso usando um computador no qual as ferramentas administrativas do Lync Server 2013 estão instaladas ou usando um procedimento de solicitação de certificado definido em sua organização, contanto que os certificados sejam exportáveis e contenham todos os nomes alternativos de entidade necessários.</span><span class="sxs-lookup"><span data-stu-id="41591-108">If you want to request certificates prior to installing servers (for instance, to save time during actual deployment of servers), you can do so by using a computer on which the Lync Server 2013 administrative tools are installed or by using a certificate request procedure defined in your organization, as long as you make sure that the certificates are exportable and contain all the required subject alternative names.</span></span> <span data-ttu-id="41591-109">Solicitar certificados com antecedência é opcional.</span><span class="sxs-lookup"><span data-stu-id="41591-109">Requesting certificates in advance is optional.</span></span> <span data-ttu-id="41591-110">Se você não solicitá-las antecipadamente, deverá solicitá-las como parte da configuração de cada servidor que exija um certificado.</span><span class="sxs-lookup"><span data-stu-id="41591-110">If you do not request them in advance, you must request them as part of the setup of each server that requires a certificate.</span></span>

<span data-ttu-id="41591-111">Esta documentação de implantação fornece procedimentos para usar o assistente de certificado para solicitar certificados como parte do processo de instalação, conforme descrito em [configurar certificados para servidores no Lync server 2013](lync-server-2013-configure-certificates-for-servers.md), [configurar certificados para o diretor no Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md)e [instalar os arquivos para o servidor de mediação no Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) seções desta documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="41591-111">This Deployment documentation provides procedures for using the Certificate Wizard to request certificates as part of the setup process, as described in the [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md), and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) sections of this Deployment documentation.</span></span> <span data-ttu-id="41591-112">Se você solicitar certificados com antecedência, deve modificar os procedimentos de implantação de certificados nestas seções conforme o apropriado, para importar e atribuir os certificados em vez de solicitá-los no momento da implantação.</span><span class="sxs-lookup"><span data-stu-id="41591-112">If you request certificates in advance, you must modify the certificate deployment procedures in those sections as appropriate to importing and assigning the certificates instead of requesting them at the time of deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="41591-113">O Lync Server 2013 inclui suporte para certificados SHA-256 para conexões de clientes que executam os sistemas operacionais Windows Vista, Windows Server &nbsp; 2008, Windows server &nbsp; 2008 &nbsp; R2 e Windows 7 e o Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="41591-113">Lync Server 2013 includes support for SHA-256 certificates for connections from clients running the Windows Vista, Windows Server&nbsp;2008, Windows Server&nbsp;2008&nbsp;R2, and Windows 7 operating systems, and Lync Phone Edition.</span></span> <span data-ttu-id="41591-114">Para oferecer suporte a acesso externo usando SHA-256,o certificado externo é emitido por uma AC pública usando SHA-256.</span><span class="sxs-lookup"><span data-stu-id="41591-114">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

