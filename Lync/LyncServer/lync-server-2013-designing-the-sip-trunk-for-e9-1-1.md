---
title: 'Lync Server 2013: projetando o tronco SIP para E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 920eecbdb456e3b643da9f935e2586dea7e6e165
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a>Projetando o tronco SIP para E9-1-1 no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-03_

O Lync Server usa troncos SIP para conectar uma chamada de emergência ao provedor de serviços E9-1-1. Você pode configurar os troncos SIP do serviço de emergência para E9-1-1 em um local central, em vários locais centrais ou em cada filial. No entanto, se o link da WAN entre o local do chamador e o local que hospeda o tronco SIP do serviço de emergência não estiver disponível, uma chamada colocada por um usuário no site desconectado precisará de um registro de uso de telefone especial na política de voz do usuário que roteará a chamada ao ECRC por meio do gateway da PSTN (Rede Telefônica Pública Comutada) local. O mesmo é verdadeiro se os limites de chamadas simultâneas do serviço de controle de admissão chamada estão em vigor.

<div>


> [!NOTE]  
> Há duas maneiras de implementar um tronco SIP em um ambiente do Lync Server: 
> <UL>
> <LI>
> <P>Use servidores de mediação de hospedagem múltipla que usam suas interfaces de roteamento público voltadas para fora para se comunicar com o provedor de tronco SIP.</P>
> <LI>
> <P>Use um SBC (controlador de borda de sessão) no local para fornecer um ponto de demarcação seguro entre os servidores de mediação e os serviços do provedor de tronco SIP.</P></LI></UL>Se você escolher o último método, certifique-se de que a marca e o modelo do SBC escolhidos foram certificados e oferecem suporte à transmissão de dados de localização PIDF-LO (objeto Local de formato de dados de informação de presença) como parte de seu SIP INVITE. Caso contrário, as chamadas chegarão no provedor de serviços de emergência retirado das suas informações de localização. Para obter detalhes sobre SBCs certificados, consulte "infraestrutura qualificada para o Microsoft <A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A>Lync" em.<BR>Os provedores de serviços E9-1-1 fornecem acesso a um par de SBCs para redundância. Você precisa tomar várias decisões em relação à topologia do servidor de mediação e à configuração de roteamento de chamadas. Você tratará os SBCs como pares iguais e utilizará o roteamento em rodízio para chamadas entre eles ou designará um SBC como primário e outro secundário?



</div>

Para obter detalhes sobre como implantar um tronco SIP no Lync Server, consulte [como implementar o tronco SIP no Lync server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md). As seguintes perguntas ajudaram você a implantar troncos SIP para E9-1-1.

  - **Você deve implantar o tronco SIP em uma conexão de concessão dedicada ou uma conexão compartilhada com a Internet?**  
    É importante que as chamadas de emergência sejam sempre conectadas. Uma linha dedicada fornece uma conexão que não será garantida por outro tráfego na rede e permite que você implemente a QoS (Qualidade de Serviço). Lembre-se de que, se você estiver se conectando a provedores de serviços de emergência por meio da Internet pública, será preciso garantir a confidencialidade das chamadas de emergência, a criptografia IPSec será necessária.

<!-- end list -->

  - **Sua implantação do E9-1-1 foi projetada para tolerância a desastres?**  
    Como esta é uma solução de emergência, a resiliência é importante. Implante seus servidores de mediação principal e secundário e troncos SIP em locais tolerantes a desastres. É uma boa ideia implantar o servidor de mediação principal mais próximo dos usuários com suporte e rotear chamadas de failover pelo servidor de mediação secundário (localizado em um local geográfico diferente).

<!-- end list -->

  - **Você deve implantar um tronco SIP separado para cada filial?**  
    O Lync Server oferece várias estratégias para lidar com a resiliência de voz em filiais, incluindo: redes de dados resistentes, implantação de um tronco SIP em cada filial ou envio de chamadas para o gateway local durante interrupções. Para obter detalhes, consulte [Branch site SIP trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).

<!-- end list -->

  - **O CAC (serviço de controle de admissão de chamada) está habilitado?**  
    O Lync Server não gerencia as chamadas de emergência de forma diferente de uma chamada comum. Por essa razão, o gerenciamento de largura de banda ou o CAC (serviço de controle de admissão de chamada) pode ter um impacto negativo em uma configuração de E9-1-1. As chamadas de emergência serão bloqueadas ou roteadas para o gateway PSTN local se um CAC estiver habilitado e for excedido o limite configurado em um link no qual as chamadas de emergência estão sendo roteadas. Como acima, tais chamadas não terão dados de localização e devem ser direcionadas manualmente para o ECRC.

</div>

<span> </span>

</div>

</div>

</div>

