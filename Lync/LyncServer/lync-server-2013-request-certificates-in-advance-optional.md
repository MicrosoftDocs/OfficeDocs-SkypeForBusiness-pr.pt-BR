---
title: 'Lync Server 2013: Solicitar certificados com antecedência (opcional)'
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
ms.openlocfilehash: 7ee4598f35bb607a9262bfeb7931e2c88e27920c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a>Solicitar certificados com antecedência (opcional) para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Os certificados são necessários para todos os servidores internos que executam o Lync Server 2013, incluindo cada servidor front-end Enterprise Edition, servidor Standard Edition, diretor, servidor de borda e servidor de mediação autônomo. Embora uma CA (autoridade de certificação) corporativa interna seja recomendada para servidores internos, você também pode usar uma CA pública. Para obter detalhes sobre os requisitos de certificado e sobre o uso de uma autoridade de certificação pública, consulte [requisitos de certificado para servidores internos no Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) na documentação de planejamento.

A instalação do Lync Server 2013 inclui o assistente de certificado, que facilita as tarefas de solicitação, atribuição e instalação de certificados durante a implantação. Se você quiser solicitar certificados antes de instalar os servidores (por exemplo, para economizar tempo durante a implantação real de servidores), poderá fazer isso usando um computador no qual as ferramentas administrativas do Lync Server 2013 estão instaladas ou usando uma solicitação de certificado procedimento definido em sua organização, desde que você certifique-se de que os certificados sejam exportáveis e contenham todos os nomes alternativos de assunto obrigatórios. Solicitar certificados antecipadamente é opcional. Se você não solicitá-los antecipadamente, será necessário solicitá-los como parte da configuração de cada servidor que exija um certificado.

Esta documentação de implantação fornece procedimentos para usar o assistente de certificado para solicitar certificados como parte do processo de configuração, conforme descrito em [configurar certificados para servidores no Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [configurar certificados para o diretor no Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md)e [instalar os arquivos do servidor de mediação nas seções do Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) desta documentação de implantação. Se você solicitar certificados com antecedência, será preciso modificar os procedimentos de implantação de certificado nessas seções, conforme apropriado, para importar e atribuir os certificados em vez de solicitá-los no momento da implantação.

<div>


> [!NOTE]  
> O Lync Server 2013 inclui suporte para certificados SHA-256 para conexões de clientes que executam os sistemas operacionais&nbsp;Windows Vista, windows&nbsp;Server&nbsp;2008, Windows Server 2008 R2 e Windows 7 e o Lync Phone Edition. Para dar suporte ao acesso externo usando SHA-256, o certificado externo é emitido por uma autoridade de certificação pública que usa SHA-256.



</div>

</div>

<span> </span>

</div>

</div>

</div>

