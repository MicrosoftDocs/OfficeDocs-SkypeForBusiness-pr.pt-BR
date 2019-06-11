---
title: 'Lync Server 2013: Habilitando a integração com servidor de Office Web Apps e Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling Office Web Apps Server and Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48183790
ms.date: 08/19/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a88a9a1649d8842c9c2c4a1f55aefcfc7853e05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a><span data-ttu-id="58dac-102">Configurando a integração com servidor de Office Web Apps e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58dac-102">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58dac-103">_**Tópico da última modificação:** 2016-08-19_</span><span class="sxs-lookup"><span data-stu-id="58dac-103">_**Topic Last Modified:** 2016-08-19_</span></span>

<span data-ttu-id="58dac-104">O Lync Server 2013 emprega o servidor do Office Web Apps para manipular apresentações do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="58dac-104">Lync Server 2013 employs Office Web Apps Server to handle PowerPoint presentations.</span></span> <span data-ttu-id="58dac-105">Para obter informações sobre as vantagens dessa abordagem, consulte [visão geral de Webconferência no Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="58dac-105">For information about the advantages to this approach, see [Overview of web conferencing in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span></span>

<span data-ttu-id="58dac-106">Para usar esses novos recursos, os administradores devem instalar o Office Web Apps Server e devem configurar o Lync Server 2013 para se comunicar com o servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="58dac-106">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="58dac-107">Esta documentação fornece informações sobre como configurar o Lync Server 2013 para trabalhar com o servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="58dac-107">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="58dac-108">O que essa documentação não fornece é uma informação sobre como instalar o próprio servidor do Office Web Apps; para obter essas informações, consulte o site de implantação do Microsoft Office <http://go.microsoft.com/fwlink/p/?linkid=257525>Web Apps em.</span><span class="sxs-lookup"><span data-stu-id="58dac-108">What this documentation does not provide is information on how to install Office Web Apps Server itself; for that information, see the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="58dac-109">Esse guia inclui informações completas de pré-requisito para o Office Web Apps Server; Observe que o Office Web Apps Server deve ser instalado em um computador autônomo que não esteja executando o Lync Server, o Microsoft SQL Server ou qualquer outro aplicativo de servidor.</span><span class="sxs-lookup"><span data-stu-id="58dac-109">That guide includes complete prerequisite information for Office Web Apps Server; note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, Microsoft SQL Server, or any other server application.</span></span> <span data-ttu-id="58dac-110">(Você não deve ter nenhuma versão do Microsoft Office instalada nesse computador.) Qualquer computador usado para executar o Office Web Apps Server também deve ter um conjunto específico de softwares instalado (incluindo .NET Framework 4,5 e Windows PowerShell 3,0); esses requisitos, juntamente com informações sobre a configuração de certificados e serviços de informações da Internet (IIS), são discutidos em detalhes no site de implantação <http://go.microsoft.com/fwlink/p/?linkid=257525>do Microsoft Office Web Apps em.</span><span class="sxs-lookup"><span data-stu-id="58dac-110">(You must not have any version of Microsoft Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0); these requirements, along with information on configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="58dac-111">A iteração mais recente do Office Web Apps Server é chamada Office Online Server, que é compatível com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58dac-111">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Lync Server 2013.</span></span> <span data-ttu-id="58dac-112">Para obter mais detalhes, consulte a <A href="https://technet.microsoft.com/en-us/library/jj219456(v=office.16).aspx">documentação do Office Online Server</A>.</span><span class="sxs-lookup"><span data-stu-id="58dac-112">For more detail, refer to the <A href="https://technet.microsoft.com/en-us/library/jj219456(v=office.16).aspx">Office Online Server documentation</A>.</span></span>



</div>

<span data-ttu-id="58dac-113">Este documento aborda as seguintes áreas de tópico:</span><span class="sxs-lookup"><span data-stu-id="58dac-113">This document covers the following topic areas:</span></span>

  - [<span data-ttu-id="58dac-114">Configurando o Lync Server 2013 para trabalhar com o servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="58dac-114">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [<span data-ttu-id="58dac-115">Publicando o servidor do Office Web Apps no Lync Server 2013 usando um servidor proxy reverso</span><span class="sxs-lookup"><span data-stu-id="58dac-115">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [<span data-ttu-id="58dac-116">Validando a configuração do servidor do Office Web Apps no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58dac-116">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [<span data-ttu-id="58dac-117">Configurar clientes do Lync Server 2013 para uso com o servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="58dac-117">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

