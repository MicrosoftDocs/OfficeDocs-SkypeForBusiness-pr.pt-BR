---
title: 'Lync Server 2013: Solicitar certificados para componentes de borda'
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
ms.openlocfilehash: 096603b48e6a3636a397c4abf7c19c2b4237f132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a>Solicitar certificados para componentes de borda no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-07_

Os certificados necessários para dar suporte a acesso externo a usuários incluem certificados emitidos por uma CA (autoridade de certificação) pública e certificados emitidos por uma CA corporativa interna:

  - Os certificados necessários para a interface externa do servidor de borda e o proxy reverso devem ser emitidos por uma CA pública.

  - Os certificados necessários para a interface interna podem ser emitidos por uma CA pública ou por uma CA corporativa interna. Recomendamos o uso de uma autoridade de certificação interna do Windows Server 2008, da autoridade de certificação do Windows Server 2008 R2, da autoridade de certificação do Windows Server 2012 ou da autoridade de certificação do Windows Server 2012 R2 para a criação desses certificados para economizar na despesa de usar certificados públicos.

<div>


> [!IMPORTANT]  
> Pode levar tempo para processar solicitações de certificado, especialmente solicitações para CAs públicas, portanto, você deve solicitar certificados para seus servidores de borda cedo o suficiente para garantir que estejam disponíveis quando você iniciar a implantação de seus componentes de servidor de borda. Para obter um resumo dos requisitos de certificado para servidores de borda, consulte <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">requisitos de certificado para acesso de usuários externos no Lync Server 2013</A>.



</div>

Embora você possa optar por usar uma autoridade de certificação pública para o certificado de borda interno, recomendamos que use uma CA corporativa interna para esses outros certificados, em vez de minimizar o custo dos certificados. Para obter um resumo dos requisitos de certificado para servidores de borda, consulte [requisitos de certificado para acesso de usuários externos no Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

<div>


> [!NOTE]  
> Quando você instala um servidor de borda, o programa de instalação inclui um assistente de certificado que facilita as tarefas de solicitação, atribuição e instalação de certificados, conforme descrito na seção <A href="lync-server-2013-set-up-edge-certificates.md">configurar certificados de borda para o Lync Server 2013</A> . Se você deseja solicitar certificados antes de instalar um servidor de borda (por exemplo, para economizar tempo durante a implantação real dos componentes do servidor de borda), é possível fazer isso usando servidores internos, desde que você garanta que os certificados sejam exportáveis e contenham todos os nomes alternativos de assunto obrigatórios. Esta documentação não fornece procedimentos para usar servidores internos para solicitar certificados.



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a>Solicitar certificados de uma CA pública

A implantação do servidor de borda requer um único certificado público para as interfaces externas de servidores de borda, que é usada para o serviço de borda de acesso, o serviço de borda de Webconferência e para o serviço de autenticação A/V. Esse certificado deve ter uma chave privada exportável para garantir que o serviço de autenticação A/V use as mesmas chaves em todos os servidores de borda em um pool. O proxy inverso, que é usado com o Microsoft Internet Security and Acceleration (ISA) Server 2006 ou o Microsoft Forefront Threat Management Gateway 2010, também requer um certificado público.

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a>Solicitar certificados de uma CA corporativa interna

Os certificados necessários para a interface de borda interna podem ser emitidos por uma CA (autoridade de certificação) pública ou uma CA interna. Você pode usar uma CA corporativa interna para ajudar a minimizar o custo dos certificados. Se a sua organização tiver uma CA interna implantada, os certificados para a borda interna deverão ser emitidos pela CA interna. Usar uma CA corporativa interna para certificados internos pode reduzir o custo dos certificados.

Para obter um resumo dos requisitos de certificado para componentes de extremidade, consulte [requisitos de certificado para acesso de usuários externos no Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md). Para obter detalhes sobre como usar uma autoridade de certificação pública para obter certificados, consulte [solicitar certificados para componentes Edge no Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md). Para obter detalhes sobre como solicitar, instalar e atribuir certificados, consulte [configurar certificados de borda para o Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

