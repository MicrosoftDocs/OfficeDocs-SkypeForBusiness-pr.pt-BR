---
title: 'Lync Server 2013: requisitos do aplicativo Lync da Windows Store'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cc1ab2b397111cef1040592f29a11d55e5f1f64
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a>Requisitos do aplicativo Lync da Windows Store para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-12-03_

As organizações com uma implantação local do Lync Server devem atender aos seguintes requisitos para dar suporte ao aplicativo Lync da Windows Store.

<div>


> [!NOTE]  
> Para o Lync Server 2010, execute a atualização cumulativa para o Lync Server 2010: fevereiro de 2012 (disponível em <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> http://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2670352</A>) ou posterior em todos os servidores. Para permitir que os usuários ingressem em reuniões, execute a atualização cumulativa do Lync Server 2010: outubro de 2012 (disponível em <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> http://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2737915</A>) nos servidores.



</div>

  - Habilite a descoberta automática, o Lync Web App e os serviços de tíquete da Web no servidor.

  - Habilite a autenticação de certificado no servidor front-end ou no pool de front-end. (O processo de registro do usuário no servidor front-end ou no pool de front-ends é geralmente chamado de registrador.) Para obter detalhes, consulte [criar configurações de registrador de configuração no Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).

  - Publicar os registros de recursos de alias de DNS (CNAME) do serviço de descoberta automática.

  - Não é mais necessário ter certeza de que o ponto de distribuição da lista de certificados revogados (CRL) dos certificados emitidos para o Lync Server aponta para um recurso HTTP em vez de um recurso LDAP. No entanto, certifique-se de que os computadores cliente tenham as atualizações mais recentes do Windows instaladas.

  - Configurar proxies HTTP na empresa para permitir o tráfego HTTP relacionado ao Lync Server.Adicione exceções para a descoberta automática, Lync Web App e serviços webticket, se necessário.

  - Em clientes, instale o Windows 8,1 e a versão mais recente do aplicativo Lync da Windows Store para corrigir um problema de entrada que geralmente ocorre ao usar vários domínios (por exemplo, quando o URI SIP é **UserA@domainZ.com** , mas o servidor de borda é **SIP.domainX.com**).

Se a sua organização assinar o Lync Online ou o Office 365 e você estiver usando seu próprio nome de domínio, você deve realizar algumas etapas adicionais para configurar a rede para descoberta automática dos servidores do Lync. Os requisitos de configuração de rede são iguais para o aplicativo Lync da Windows Store e Lync em dispositivos móveis. Siga as instruções "configurar sua rede" no artigo do wiki do Office 365 "configurar dispositivos móveis do Lync", disponível em [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822).

<div>

## <a name="see-also"></a>Confira também


[Implantando o aplicativo Lync da Windows Store no Lync Server 2013](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

