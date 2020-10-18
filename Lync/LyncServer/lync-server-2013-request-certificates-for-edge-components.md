---
title: 'Lync Server 2013: solicitar certificados para componentes de borda'
description: 'Lync Server 2013: solicitar certificados para componentes de borda.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 461e40921c88f26ce56141a8782ef2a04ce99667
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579007"
---
# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a>Solicitar certificados para componentes de borda no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-07_

Os certificados necessários para dar suporte ao acesso de usuário externo incluem certificados emitidos por uma autoridade de certificação pública e certificados emitidos por uma autoridade corporativa interna:

  - Os certificados necessários para a interface externa do servidor de borda e do proxy reverso devem ser emitidos por uma autoridade de certificação pública.

  - Os ertificados necessários para a interface interna podem ser emitidos por uma autoridade de certificação pública ou uma autoridade de certificação corporativa interna. Recomendamos o uso de uma autoridade de certificação interna do Windows Server 2008, da AC do Windows Server 2008 R2, da autoridade de certificação do Windows Server 2012 ou da autoridade de certificação do Windows Server 2012 R2 para a criação desses certificados para economizar na despesa com o uso de certificados públicos.

<div>


> [!IMPORTANT]  
> Pode levar tempo para processar solicitações de certificados, especialmente as solicitações para autoridades de certificação públicas; portanto, você deve solicitar os certificados para seus Servidores de Borda com antecedência suficiente para garantir que estejam disponíveis quando você inicia a implantação dos componentes do Servidor de Borda. Para obter um resumo dos requisitos de certificado para servidores de borda, consulte <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate Requirements for External User Access in Lync Server 2013</A>.



</div>

Embora você possa optar pelo uso de uma AC pública para o certificado da borda interna, é recomendável o uso de uma AC corporativa interna para os outros certificados, para minimizar o custo de certificados. Para obter um resumo dos requisitos de certificado para servidores de borda, consulte [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

<div>


> [!NOTE]  
> Quando você instala um servidor de borda, a instalação inclui um assistente de certificado que facilita as tarefas de solicitação, atribuição e instalação de certificados, conforme descrito na seção <A href="lync-server-2013-set-up-edge-certificates.md">configurar certificados de borda para o Lync Server 2013</A> . Se quiser solicitar certificados antes de instalar um servidor de borda (por exemplo, para economizar tempo durante a implantação real dos componentes do servidor de borda), você pode usar servidores internos, contanto que os certificados sejam exportáveis e que contenham todos os nomes alternativos de entidade necessários. Esta documentação não fornece procedimentos para usar servidores internos para solicitar certificados.



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a>Solicitar certificados de uma AC pública

A implantação do servidor de borda requer um único certificado público para as interfaces externas de servidores de borda, que é usada para o serviço de borda de acesso, o serviço de borda de Webconferência e o serviço de autenticação A/V. Esse certificado deve ter uma chave privada exportável para garantir que o serviço de autenticação A/V use as mesmas chaves em todos os servidores de borda em um pool. O proxy reverso, que é usado com o Microsoft Internet Security and Acceleration (ISA) Server 2006 ou o Microsoft Forefront Threat Management Gateway 2010, também requer um certificado público.

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a>Solicitar certificados de uma AC empresarial interna

Os certificados necessários para a interface de borda interna podem ser emitidos por uma autoridade de certificação (CA) pública ou interna. Você pode usar uma CA corporativa interna para ajudar a minimizar o custo dos certificados. Se sua organização tiver uma CA interna implantada, os certificados da borda interna deverão ser emitidos por ela. O uso de uma CA corporativa interna para certificados internos pode reduzir o custo dos certificados.

Para obter um resumo dos requisitos de certificado para componentes de borda, consulte [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md). Para obter detalhes sobre como usar uma autoridade de certificação pública para obter certificados, consulte [solicitar certificados para componentes de borda no Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md). Para obter detalhes sobre como solicitar, instalar e atribuir certificados, consulte [set up Edge Certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

