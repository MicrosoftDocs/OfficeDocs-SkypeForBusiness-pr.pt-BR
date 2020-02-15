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
ms.openlocfilehash: 69761715846cd65a44fe34c9c8465101e9ceb681
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a>Topologias para telefones IP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-21_

Esta seção fornece uma visão geral do processo de conectividade e explica as diferenças entre como um telefone IP se conecta em uma rede interna e externa.

<div>


> [!NOTE]  
> O Lync Server oferece suporte para os seguintes telefones IP: o telefone de área comum do Aastra 6721ip, Aastra 6725ip de telefone, telefone IP HP 4110 (telefone de área comum), HP 4120 IP Phone (telefone de mesa), telefone de mesa de IP de Polycom CX600, telefone de rede IP do Polycom CX700, Polycom CX500 IP telefone de área comum e telefone de conferência IP Polycom CX3000. Desses telefones, todos exceto o Polycom CX700 podem executar o Lync Phone Edition.



</div>

O diagrama a seguir descreve todos os componentes envolvidos na conectividade do dispositivo dentro do ambiente empresarial.

**Topologia Interna**

![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")

<div>


> [!NOTE]  
> A figura anterior é uma representação local, não visão geral física. Por exemplo, os serviços de domínio do Active Directory (AD DS) raramente estão localizados na mesma máquina que os componentes do Lync Server. O repositório de usuários pode estar localizado no Servidor de Back-End ou nos Servidores de Arquivamento e Monitoramento. O Shell de gerenciamento do Lync Server, o servidor Web e os serviços de atualização são todos parte da função de servidor front-end.



</div>

O diagrama a seguir fornece uma visão geral dos componentes envolvidos quando o dispositivo está localizado fora da rede corporativa.

**Topologia Externa**

![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")

<div>


> [!NOTE]  
> O serviço da Web de Atualização de Dispositivo oferece um site externo e interno, mas apenas o externo é mostrado aqui.<BR>O local do Registrador e a URL do Web Service de atualização de dispositivos para a organização devem ser publicados no DNS se o acesso externo deve ser habilitado. Além disso, o Servidor de Borda deve implantado e configurado corretamente para permitir comunicações externas do dispositivo para o ambiente corporativo e vice-versa. Isto é omitido no diagrama anterior porque a implantação de Borda não é específica para conectividade do dispositivo.



</div>

</div>

<span> </span>

</div>

</div>

</div>

