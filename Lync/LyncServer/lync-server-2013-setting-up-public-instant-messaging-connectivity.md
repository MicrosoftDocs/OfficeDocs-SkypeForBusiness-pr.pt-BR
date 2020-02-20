---
title: 'Lync Server 2013: Configurando conectividade de mensagens instantâneas públicas'
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
ms.openlocfilehash: 4887e419e45f6b6fb165dc7efff407332f3e150a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="19dfd-102">Configurando a conectividade de mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19dfd-102">Setting up public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19dfd-103">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="19dfd-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="19dfd-p101">Se sua organização desejar oferecer suporte à conectividade pública de mensagens instantâneas com o AOL, você não pode usar o Assistente de Implantação do Lync Server para solicitar o certificado. Em vez disso, siga o procedimento abaixo.</span><span class="sxs-lookup"><span data-stu-id="19dfd-p101">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate. Instead, perform the steps in the following procedure.</span></span>

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a><span data-ttu-id="19dfd-106">Configurando a conectividade para redes públicas de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="19dfd-106">Setting Up Public Instant Messaging Connectivity</span></span>

1.  <span data-ttu-id="19dfd-p102">Em um servidor Front End, abra o Construtor de Topologias. Expanda os pools de borda e clique em seu servidor de borda ou pool de servidor de borda. Selecione as Editar propriedades.</span><span class="sxs-lookup"><span data-stu-id="19dfd-p102">On a Front End server, open Topology Builder. Expand Edge pools, then right click your Edge server or Edge server pool. Select Edit properties.</span></span>

2.  <span data-ttu-id="19dfd-p103">Em Editar Propriedades, sob Geral, selecione Habilitar Federação para este pool de borda (Porta 5061). Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="19dfd-p103">In Edit Properties under General, select Enable federation for this Edge pool (Port 5061). Click OK.</span></span>

3.  <span data-ttu-id="19dfd-p104">Clique em Ação, selecione Topologia, selecione Publicar. Quando a mensagem sobre Publicar a topologia surgir, clique em Próxima. Quando Publicar for concluído, clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="19dfd-p104">Click Action, select Topology, select Publish. When prompted on Publish the topology, click Next. When the Publish is finished, click Finish.</span></span>

4.  <span data-ttu-id="19dfd-p105">No servidor de borda, abra o Assistente de Implantação do Lync Server. Clique em Instalar ou Atualizar Sistema do Lync Server; em seguida, clique em Instalação ou Remover Componentes do Lync Server. Clique em Executar Novamente.</span><span class="sxs-lookup"><span data-stu-id="19dfd-p105">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="19dfd-p106">Em Componentes de Configuração Lync Server, clique em Próxima. A tela de resumo mostrará as ações conforme forem executadas. Quando a implantação for concluída, clique em Exibir Log para ver os arquivos de log disponíveis. Clique em Concluir para finalizar a implantação.</span><span class="sxs-lookup"><span data-stu-id="19dfd-p106">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="19dfd-122">Para criar uma solicitação de certificado para a interface externa do Servidor de Borda para oferecer suporte à conectividade pública de IM com o AOL</span><span class="sxs-lookup"><span data-stu-id="19dfd-122">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="19dfd-123">Quando o modelo necessário estiver disponível para a autoridade de certificação, use o seguinte cmdlet Windows PowerShell no Servidor de Borda para solicitar o certificado:</span><span class="sxs-lookup"><span data-stu-id="19dfd-123">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="19dfd-124">O nome de certificado padrão do modelo usado para o Lync Server é o servidor Web.</span><span class="sxs-lookup"><span data-stu-id="19dfd-124">The default certificate name of the template used for Lync Server is Web Server.</span></span> <span data-ttu-id="19dfd-125">Só especifique o \<nome\> do modelo se você precisar usar um modelo diferente do modelo padrão.</span><span class="sxs-lookup"><span data-stu-id="19dfd-125">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="19dfd-126">Se sua organização quiser suportar a conectividade pública de IM com o AOL, você deve usar o Windows PowerShell em vez do assistente de certificado para solicitar que o certificado seja atribuído à borda externa do serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="19dfd-126">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="19dfd-127">Isso ocorre porque o modelo de Servidor Web da Autoridade (CA) usado pelo Assistente de Certificados para solicitar um certificado não oferece suporte à configuração de cliente EKU.</span><span class="sxs-lookup"><span data-stu-id="19dfd-127">This is because the Certificate Authority (CA) Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="19dfd-128">Antes de usar o Windows PowerShell para criar o certificado, o administrador da autoridade de certificação deve criar e implantar um novo modelo que dê suporte ao EKU do cliente.</span><span class="sxs-lookup"><span data-stu-id="19dfd-128">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

