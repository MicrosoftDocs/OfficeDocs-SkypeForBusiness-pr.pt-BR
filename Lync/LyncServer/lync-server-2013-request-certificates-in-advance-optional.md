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
ms.openlocfilehash: fd3bda5e7ea4169af0abb173befc9b91ccfb7c22
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a>Solicitar certificados com antecedência (opcional) para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Os certificados são necessários para todos os servidores internos que executam o Lync Server 2013, incluindo cada servidor de front-ends Enterprise Edition, servidor Standard Edition, diretor, servidor de borda e servidor de mediação autônomo. Embora uma autoridade de certificação empresarial interna seja recomendada para servidores internos, você também pode usar uma autoridade de certificação pública. Para obter detalhes sobre os requisitos de certificado e sobre o uso de uma AC pública, consulte [Certificate Requirements for Internal Servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) na documentação de planejamento.

O programa de instalação do Lync Server 2013 inclui o assistente de certificado, que facilita as tarefas de solicitação, atribuição e instalação de certificados durante a implantação. Se você quiser solicitar certificados antes de instalar servidores (por exemplo, para economizar tempo durante a implantação real de servidores), você pode fazer isso usando um computador no qual as ferramentas administrativas do Lync Server 2013 estão instaladas ou usando uma solicitação de certificado procedimento definido em sua organização, desde que você tenha certeza de que os certificados são exportáveis e que contenham todos os nomes alternativos de entidade necessários. Solicitar certificados com antecedência é opcional. Se você não solicitá-las antecipadamente, deverá solicitá-las como parte da configuração de cada servidor que exija um certificado.

Esta documentação de implantação fornece procedimentos para usar o assistente de certificado para solicitar certificados como parte do processo de instalação, conforme descrito em [configurar certificados para servidores no Lync server 2013](lync-server-2013-configure-certificates-for-servers.md), [configurar certificados para o diretor no Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md)e [instalar os arquivos para o servidor de mediação no Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) seções desta documentação de implantação. Se você solicitar certificados com antecedência, deve modificar os procedimentos de implantação de certificados nestas seções conforme o apropriado, para importar e atribuir os certificados em vez de solicitá-los no momento da implantação.

<div>


> [!NOTE]  
> O Lync Server 2013 inclui suporte para certificados SHA-256 para conexões de clientes que executam os sistemas operacionais&nbsp;Windows Vista, windows&nbsp;Server&nbsp;2008, Windows Server 2008 R2 e Windows 7 e o Lync Phone Edition. Para oferecer suporte a acesso externo usando SHA-256,o certificado externo é emitido por uma AC pública usando SHA-256.



</div>

</div>

<span> </span>

</div>

</div>

</div>

