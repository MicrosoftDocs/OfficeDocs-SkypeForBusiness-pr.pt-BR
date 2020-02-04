---
title: 'Lync Server 2013: topologias para telefones IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e05a56d30167f2e20a383cde9fcfaaa70418e650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a>Topologias para telefones IP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-21_

Esta seção fornece uma visão geral do processo de conectividade e explica as diferenças entre como um telefone IP se conecta a uma rede interna e externa.

<div>


> [!NOTE]  
> O Lync Server oferece suporte para os seguintes telefones IP: o Aastra 6721ip Common Area Phone, Aastra 6725ip Desk Phone, HP 4110 IP Phone (Common Area Phone), HP 4120 IP Phone (Phone Desk), Polycom CX600 IP Desk Phone, Polycom CX700 IP Desk Phone, Polycom CX500 IP telefone de área comum e Polycom CX3000 de conferência IP. Desses telefones, tudo menos o Polycom CX700 pode executar o Lync Phone Edition.



</div>

O diagrama a seguir descreve todos os componentes envolvidos na conectividade do dispositivo no ambiente corporativo.

**Topologia interna**

![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")

<div>


> [!NOTE]  
> A figura anterior é uma representação lógica, não uma visão geral física. Por exemplo, os serviços de domínio Active Directory (AD DS) raramente estão localizados na mesma máquina que qualquer componente do Lync Server. O repositório de usuários pode estar localizado no servidor back-end ou nos servidores de arquivamento e monitoramento. O Shell de gerenciamento do Lync Server, o servidor Web e os serviços de atualização são parte da função de servidor front-end.



</div>

O diagrama a seguir fornece uma visão geral dos componentes envolvidos quando o dispositivo está localizado fora da rede corporativa.

**Topologia externa**

![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")

<div>


> [!NOTE]  
> O serviço Web de atualização de dispositivo fornece um site externo e externo, mas somente o externo é mostrado aqui.<BR>A localização do registrador e a URL do serviço Web de atualização de dispositivo para a organização devem ser publicadas no DNS se o acesso externo estiver habilitado. Além disso, o servidor de borda deve ser implantado e configurado corretamente para permitir comunicações externas do dispositivo para o ambiente corporativo e para trás. Isso é omitido do diagrama anterior porque a implantação de borda não é específica da conectividade do dispositivo.



</div>

</div>

<span> </span>

</div>

</div>

</div>

