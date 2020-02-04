---
title: 'Lync Server 2013: configurar a Federação para um provedor de serviços de audioconferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation for an audio conferencing provider
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn510996(v=OCS.15)
ms:contentKeyID: 60595883
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5c1ca77b2f68a2285fb15d65c19631323a03bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a>Configurar a Federação para um provedor de audioconferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-07-24_

Se quiser usar um ACP (provedor de serviços de audioconferência) na sua implantação híbrida (Lync Server local com o Lync Online), você precisará configurar a Federação entre a implantação do Lync local e o parceiro ACP como um servidor parceiro autorizado. É possível configurar a federação adicionando o domínio do parceiro ACP e o servidor de Borda (também conhecido como Proxy de Acesso) à lista de Domínios de Federação para sua implantação no local. Seu parceiro ACP precisará adicionar o FQDN de seu pool de Servidor de Borda no local à lista de domínios de federação permitidos. Entre em contato com seu provedor de ACP para obter um parceiro detailsYour ACP adicional e, em seguida, precisa adicionar o FQDN do pool de servidores de borda local à lista de domínios federados permitidos.

  - **Adição do domínio ACP e do servidor de borda como um domínio federado permitido**
    
    Para adicionar o domínio ACP como um servidor parceiro permitido (domínio federado permitido), siga as etapas em [Configurar o suporte para domínios externos permitidos no Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md). Para o Servidor de borda, adicione o FQDN do servidor de borda do parceiro ACP. Pode ser necessário entrar em contato com seu parceiro ACP para obter o FQDN do Servidor de Borda, que também pode ser mencionado pelo ACP como Proxy de Acesso.

  - **Forneça o FQDN do seu pool do servidor de borda ao parceiro ACP**
    
    O parceiro ACP precisa configurar a federação para adicionar seu domínio no local como um Servidor Parceiro Permitido, adicionando o FQDN de seu pool de Servidor de Borda como um domínio de Federação permitido.

</div>

<span> </span>

</div>

</div>

</div>

