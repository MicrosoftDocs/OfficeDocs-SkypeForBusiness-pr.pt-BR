---
title: 'Lync Server 2013: Habilitando o servidor do Office Web Apps e o Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Office Web Apps Server and Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48183790
ms.date: 08/19/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89ec4337bd4bc728f9737ecb75bb29075831bc09
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528538"
---
# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a><span data-ttu-id="54d40-102">Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54d40-102">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54d40-103">_**Última modificação do tópico:** 2016-08-19_</span><span class="sxs-lookup"><span data-stu-id="54d40-103">_**Topic Last Modified:** 2016-08-19_</span></span>

<span data-ttu-id="54d40-104">O Lync Server 2013 emprega o servidor do Office Web Apps para lidar com apresentações do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="54d40-104">Lync Server 2013 employs Office Web Apps Server to handle PowerPoint presentations.</span></span> <span data-ttu-id="54d40-105">Para obter informações sobre as vantagens dessa abordagem, consulte [Overview of Web Conferencing in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="54d40-105">For information about the advantages to this approach, see [Overview of web conferencing in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span></span>

<span data-ttu-id="54d40-106">Para usar esses novos recursos, os administradores devem instalar o Office Web Apps Server e devem configurar o Lync Server 2013 para se comunicar com o servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="54d40-106">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="54d40-107">Esta documentação fornece informações sobre como configurar o Lync Server 2013 para funcionar com o servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="54d40-107">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="54d40-108">O que esta documentação não fornece é informações sobre como instalar o próprio servidor do Office Web Apps; para essas informações, consulte o site de implantação do Microsoft Office Web Apps em <https://go.microsoft.com/fwlink/p/?linkid=257525> .</span><span class="sxs-lookup"><span data-stu-id="54d40-108">What this documentation does not provide is information on how to install Office Web Apps Server itself; for that information, see the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="54d40-109">Esse guia inclui informações completas de pré-requisito para o servidor do Office Web Apps; Observe que o servidor do Office Web Apps deve ser instalado em um computador autônomo que não esteja executando o Lync Server, o Microsoft SQL Server ou qualquer outro aplicativo de servidor.</span><span class="sxs-lookup"><span data-stu-id="54d40-109">That guide includes complete prerequisite information for Office Web Apps Server; note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, Microsoft SQL Server, or any other server application.</span></span> <span data-ttu-id="54d40-110">(Você não deve ter nenhuma versão do Microsoft Office instalada nesse computador.) Qualquer computador usado para executar o servidor do Office Web Apps também deve ter um conjunto específico de software instalado (incluindo o .NET Framework 4,5 e o Windows PowerShell 3,0); esses requisitos, juntamente com as informações sobre a configuração de certificados e os serviços de informações da Internet (IIS), são discutidos em detalhes no site de implantação do Microsoft Office Web Apps em <https://go.microsoft.com/fwlink/p/?linkid=257525> .</span><span class="sxs-lookup"><span data-stu-id="54d40-110">(You must not have any version of Microsoft Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0); these requirements, along with information on configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="54d40-111">A iteração mais recente do servidor do Office Web Apps é chamada de servidor do Office Online, com suporte no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="54d40-111">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Lync Server 2013.</span></span> <span data-ttu-id="54d40-112">Para obter mais detalhes, consulte a <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">documentação do servidor do Office Online</A>.</span><span class="sxs-lookup"><span data-stu-id="54d40-112">For more detail, refer to the <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">Office Online Server documentation</A>.</span></span>



</div>

<span data-ttu-id="54d40-113">Este documento abrange as seguintes áreas de tópico:</span><span class="sxs-lookup"><span data-stu-id="54d40-113">This document covers the following topic areas:</span></span>

  - [<span data-ttu-id="54d40-114">Configurando o Lync Server 2013 para funcionar com o servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="54d40-114">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [<span data-ttu-id="54d40-115">Publicar o servidor do Office Web Apps no Lync Server 2013 usando um servidor de proxy reverso</span><span class="sxs-lookup"><span data-stu-id="54d40-115">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [<span data-ttu-id="54d40-116">Validando a configuração do servidor do Office Web Apps no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54d40-116">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [<span data-ttu-id="54d40-117">Configurando clientes do Lync Server 2013 para uso com o servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="54d40-117">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

