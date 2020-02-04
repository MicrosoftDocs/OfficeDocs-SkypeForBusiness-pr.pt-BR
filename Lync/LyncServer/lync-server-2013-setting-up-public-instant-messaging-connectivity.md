---
title: 'Lync Server 2013: Configurar conectividade de mensagens instantâneas públicas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 871f513170fcb0491f6732751cfc1b23877526b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="ec4a4-102">Configurar conectividade de mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec4a4-102">Setting up public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec4a4-103">_**Tópico da última modificação:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ec4a4-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ec4a4-104">Se a sua organização quiser dar suporte à conectividade de mensagens instantâneas (IM) pública com a AOL, você não poderá usar o assistente de implantação do Lync Server para solicitar o certificado.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-104">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="ec4a4-105">Em vez disso, siga as etapas do procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-105">Instead, perform the steps in the following procedure.</span></span>

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a><span data-ttu-id="ec4a4-106">Configurar a conectividade de mensagens instantâneas públicas</span><span class="sxs-lookup"><span data-stu-id="ec4a4-106">Setting Up Public Instant Messaging Connectivity</span></span>

1.  <span data-ttu-id="ec4a4-107">Em um servidor front-end, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-107">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="ec4a4-108">Expanda Pools de bordas e clique com o botão direito do mouse no seu servidor de borda ou no pool do servidor</span><span class="sxs-lookup"><span data-stu-id="ec4a4-108">Expand Edge pools, then right click your Edge server or Edge server pool.</span></span> <span data-ttu-id="ec4a4-109">Selecione Editar propriedades.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-109">Select Edit properties.</span></span>

2.  <span data-ttu-id="ec4a4-110">Em Editar propriedades em geral, selecione Habilitar Federação para este pool de bordas (porta 5061).</span><span class="sxs-lookup"><span data-stu-id="ec4a4-110">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061).</span></span> <span data-ttu-id="ec4a4-111">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-111">Click OK.</span></span>

3.  <span data-ttu-id="ec4a4-112">Clique em ação, selecione topologia, selecione publicar.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-112">Click Action, select Topology, select Publish.</span></span> <span data-ttu-id="ec4a4-113">Quando solicitado em publicar a topologia, clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-113">When prompted on Publish the topology, click Next.</span></span> <span data-ttu-id="ec4a4-114">Quando a publicação estiver concluída, clique em concluir.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-114">When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="ec4a4-115">No servidor de borda, abra o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-115">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="ec4a4-116">Clique em instalar ou atualizar o Lync Server System e, em seguida, clique em configurar ou remover componentes do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-116">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="ec4a4-117">Clique em executar novamente.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-117">Click Run Again.</span></span>

5.  <span data-ttu-id="ec4a4-118">Em configurar componentes do Lync Server, clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-118">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="ec4a4-119">A tela Resumo mostrará as ações conforme elas são executadas.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-119">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="ec4a4-120">Depois que a implantação for concluída, clique em Exibir log para exibir os arquivos de log disponíveis.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-120">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="ec4a4-121">Clique em concluir para concluir a implantação.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-121">Click Finish to complete the deployment.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="ec4a4-122">Para criar uma solicitação de certificado para a interface externa do servidor de borda para dar suporte à conectividade de mensagem de chat pública com a AOL</span><span class="sxs-lookup"><span data-stu-id="ec4a4-122">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="ec4a4-123">Quando o modelo obrigatório estiver disponível para a autoridade de certificação, use o seguinte cmdlet do Windows PowerShell no servidor de borda para solicitar o certificado</span><span class="sxs-lookup"><span data-stu-id="ec4a4-123">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="ec4a4-124">O nome de certificado padrão do modelo usado para o Lync Server é o servidor Web.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-124">The default certificate name of the template used for Lync Server is Web Server.</span></span> <span data-ttu-id="ec4a4-125">Especifique somente o \<nome\> do modelo se precisar usar um modelo diferente do modelo padrão.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-125">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ec4a4-126">Se a sua organização quiser dar suporte à conectividade de mensagem instantânea pública com a AOL, você deve usar o Windows PowerShell em vez do assistente de certificado para solicitar que o certificado seja atribuído à borda externa do serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-126">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="ec4a4-127">Isso ocorre porque o modelo de servidor Web da autoridade de certificação (CA) que o assistente de certificado usa para solicitar um certificado não oferece suporte à configuração de EKU de cliente.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-127">This is because the Certificate Authority (CA) Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="ec4a4-128">Antes de usar o Windows PowerShell para criar o certificado, o administrador da CA deve criar e implantar um novo modelo compatível com o EKU do cliente.</span><span class="sxs-lookup"><span data-stu-id="ec4a4-128">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

