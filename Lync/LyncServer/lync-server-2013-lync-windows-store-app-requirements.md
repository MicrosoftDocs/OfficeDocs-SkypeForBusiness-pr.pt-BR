---
title: 'Lync Server 2013: requisitos de aplicativo da Windows Store do Lync'
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
ms.openlocfilehash: 06d32aa0cf2248c80b8f98d80e8c796818b89a6b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a>Requisitos de aplicativo do Lync Windows Store para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-12-03_

As organizações com uma implantação local do Lync Server devem atender aos seguintes requisitos para dar suporte ao aplicativo Lync da Windows Store.

<div>


> [!NOTE]  
> Para o Lync Server 2010, execute a atualização cumulativa para o Lync Server 2010: fevereiro de 2012 (disponível em <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> https://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2670352</A>) ou posterior em todos os servidores. Para permitir que os usuários ingressem em reuniões, execute a atualização cumulativa do Lync Server 2010: outubro de 2012 (disponível em <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> https://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2737915</A>) nos servidores.



</div>

  - Habilite a descoberta automática, Lync Web App e serviços de tíquete da Web no servidor.

  - Habilitar a autenticação de certificado no servidor front-end ou no pool de front-ends. (O processo de registro do usuário no servidor front-end ou no pool de front-ends é geralmente chamado de registrador). Para obter detalhes, consulte [criar definições de configuração do registrador no Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).

  - Publique os registros de recursos de alias de DNS (CNAME) para o serviço de descoberta automática.

  - Não é mais necessário certificar-se de que o ponto de distribuição de CRL (lista de certificados revogados) para os certificados emitidos para o Lync Server aponta para um recurso HTTP em vez de um recurso LDAP. No entanto, verifique se os computadores cliente têm as atualizações mais recentes do Windows instaladas.

  - Configure proxies HTTP na empresa para permitir o tráfego HTTP relacionado ao Lync Server.Adicione exceções para os serviços descoberta automática, Lync Web App e webticket, se necessário.

  - Em clientes, instale o Windows 8,1 e a versão mais recente do aplicativo Lync da Windows Store para corrigir um problema de entrada que geralmente ocorre ao usar vários domínios (por exemplo, quando o URI do SIP é **UserA@domainZ.com** , mas o servidor de borda é **SIP.domainX.com**).

Se sua organização se inscrever no Lync Online ou no Office 365 e você estiver usando seu próprio nome de domínio, você deve realizar algumas etapas adicionais para configurar sua rede para descoberta automática dos servidores Lync. Os requisitos de configuração de rede são os mesmos para Lync Windows Store app e Lync em dispositivos móveis. Siga as instruções "configurar sua rede" no artigo do wiki do Office 365 "configurar dispositivos do Lync Mobile", disponível em [https://go.microsoft.com/fwlink/?LinkId=271822](https://go.microsoft.com/fwlink/?linkid=271822).

<div>

## <a name="see-also"></a>Confira também


[Implantando o aplicativo Lync da Windows Store no Lync Server 2013](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

