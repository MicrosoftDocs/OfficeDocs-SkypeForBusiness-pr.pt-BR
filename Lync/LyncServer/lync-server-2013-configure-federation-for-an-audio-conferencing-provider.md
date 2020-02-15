---
title: 'Lync Server 2013: configurar Federação para um provedor de conferência de áudio'
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
ms.openlocfilehash: 4725e80a00da46b7d446b8b8c938b65c569ef8d1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a>Configurar Federação para um provedor de conferência de áudio no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-07-24_

Se você quiser usar um provedor de serviços de audioconferência (ACP) em sua implantação híbrida (Lync Server local com Lync Online), você precisará configurar a Federação entre sua implantação do Lync local e o parceiro ACP como um servidor parceiro permitido. Você pode configurar a Federação adicionando o domínio de parceiro ACP e o servidor de borda (isso também pode ser chamado de proxy de acesso) à lista de domínios federados para sua implantação local. O parceiro ACP precisará adicionar o FQDN do pool de servidores de borda local à lista de domínios federados permitidos. Entre em contato com seu provedor de ACP para obter o parceiro detailsYour ACP adicional, é necessário adicionar o FQDN do pool de servidores de borda local à lista de domínios federados permitidos.

  - **Adicionar o domínio ACP e o servidor de borda como um domínio federado permitido**
    
    Para adicionar o domínio ACP como um servidor parceiro permitido (domínio federado permitido), siga as etapas em [Configurar suporte para domínios externos permitidos no Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md). Para o servidor de borda, adicione o FQDN do servidor de borda do parceiro ACP. Talvez seja necessário entrar em contato com seu parceiro ACP para obter o FQDN do servidor de borda, que também pode ser mencionado pelo ACP como proxy de acesso.

  - **Forneça o FQDN do seu pool do servidor de borda ao parceiro ACP**
    
    O parceiro ACP precisa configurar a Federação para adicionar seu domínio local como um servidor parceiro permitido adicionando o FQDN do seu pool de servidor de borda como um domínio federado permitido.

</div>

<span> </span>

</div>

</div>

</div>

