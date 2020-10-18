---
title: 'Lync Server 2013: Diretrizes para integração da Unificação de mensagens local'
description: 'Lync Server 2013: Diretrizes para integração da Unificação de mensagens local.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814c927aa36199737712328d3b92c64a8e967a55
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576637"
---
# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Diretrizes para integrar a Unificação de mensagens local e o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-25_

Veja a seguir as diretrizes e práticas recomendadas a serem consideradas ao implantar o Enterprise Voice:

<div>


> [!IMPORTANT]  
> A Unificação de mensagens (UM) do Exchange oferece suporte a IPv6 somente se você também estiver usando o UCMA 4.



</div>

  - Implantar um servidor do Lync Server 2013 Standard Edition ou um pool de front-ends. Para obter detalhes sobre a instalação, consulte [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.

  - Trabalhar com os administradores do Exchange para confirmar que tarefas cada um executará para garantir uma integração tranqüila e bem-sucedida.

  - Implante as funções de servidor de caixa de correio do Exchange em cada floresta de UM (Unificação de mensagens) do Exchange onde você deseja habilitar usuários para UM do Exchange. Para obter detalhes sobre como instalar as funções do Exchange Server, consulte a documentação do Microsoft Exchange Server 2013.
    
    <div>
    

    > [!IMPORTANT]  
    > Quando a Unificação de mensagens (UM) do Exchange está instalada, ela é configurada para usar um certificado autoassinado.<BR>No entanto, o certificado autoassinado não permite que o Lync Server 2013 e o Exchange UM confiem uns com os outros, o que é necessário para solicitar um certificado separado de uma autoridade de certificação em que ambos os servidores confiem.

    
    </div>

  - Se o Lync Server 2013 e o Exchange UM estiverem instalados em florestas diferentes, configure cada floresta do Exchange para confiar na floresta do Lync Server 2013 e na floresta do Lync Server 2013 para confiar em cada floresta do Exchange. Além disso, defina as configurações de UM do Exchange do usuário nos objetos de usuário na floresta do Lync Server 2013, normalmente usando um script ou uma ferramenta entre florestas, como o Identity Lifecycle Manager (ILM).

  - Se necessário, instale o Console de Gerenciamento do Exchange para gerenciar os servidores de Unificação de mensagens.

  - Obtenha números de telefone válidos para o Outlook Voice Access e o atendedor automático.

  - Se você estiver usando uma versão do UM do Exchange anterior ao Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordene nomes para planos de discagem URI SIP de UM do Exchange e planos de discagem do Enterprise Voice.

<div>

## <a name="deploying-redundant-exchange-um-servers"></a>Implantando Servidores Redundantes UM do Exchange

<div>


> [!IMPORTANT]  
> Recomendamos que você implante um mínimo de dois servidores nos quais os serviços de UM do Exchange estão sendo executados para cada plano de discagem de URI SIP da UM do Exchange que você configura para sua organização. Além de fornecer capacidade expandida, a implantação de servidores redundantes oferece alta disponibilidade. No caso de uma falha de servidor, o Lync Server 2013 pode ser configurado para fazer failover para outro servidor.



</div>

As seguintes configurações de exemplo fornecem resiliência de UM do Exchange.

**Exemplo 1: resiliência de UM do Exchange**

![Exemplo 1 de UM do Exchange](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exemplo 1 de UM do Exchange")

No exemplo 1, os servidores UM 1 e 2 do Exchange são ativados no data center de Tukwila e os servidores UM 3 e 4 do Exchange são ativados no data center de Dublin. No caso de uma paralisação um do Exchange no Tukwila, o sistema de nomes de domínio (DNS) um registro para os servidores 1 e 2 deve ser configurado para apontar para os servidores 3 e 4, respectivamente. No caso de uma paralisação um do Exchange em Dublin, os registros DNS A para os servidores 3 e 4 devem ser configurados para apontar para os servidores 1 e 2, respectivamente.

<div>


> [!NOTE]  
> Para o exemplo 1, você deve também atribuir um dos seguintes certificados em cada servidor UM do Exchange: 
> <UL>
> <LI>
> <P>Use um certificado com um caractere curinga no nome de alternativo da entidade (SAN).</P>
> <LI>
> <P>Coloque o FQDN (nome de domínio totalmente qualificado) de cada um dos quatro servidores de UM do Exchange na SAN.</P></LI></UL>



</div>

**Exemplo 2: resiliência de UM do Exchange**

![Exemplo 2 de UM do Exchange](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exemplo 2 de UM do Exchange")

No exemplo 2, sob condições operacionais comuns, os servidores UM 1 e 2 do Exchange são ativados no data center de Tukwila e os servidores UM 3 e 4 do Exchange são ativados no data center de Dublin. Os quatro servidores estão incluídos no plano de discagem de URI do SIP dos usuários de Tukwila; no entanto, os servidores 3 e 4 estão desativados. No caso de uma paralisação UM Exchange em Tukwila, por exemplo, os servidores UM 1 e 2 do Exchange devem ser desativados e os servidores UM 3 e 4 do Exchange devem ser habilitados para que o tráfego UM do Exchange de Tukwila seja roteado para os servidores em Dublin.

Para obter detalhes sobre como habilitar ou desabilitar a Unificação de mensagens no Exchange 2013, consulte "integrar o Exchange 2013 UM com Lync Server" em [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372) .

Para obter detalhes sobre como habilitar ou desabilitar a Unificação de mensagens no Microsoft Exchange Server 2010, consulte:

  - "Habilitar a Unificação de mensagens no Exchange 2010" em [https://go.microsoft.com/fwlink/p/?LinkId=204418](https://go.microsoft.com/fwlink/p/?linkid=204418) .

  - "Desabilitar a Unificação de mensagens no Exchange 2010" em [https://go.microsoft.com/fwlink/p/?LinkId=204416](https://go.microsoft.com/fwlink/p/?linkid=204416) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Processo de implantação para integração de Unificação de mensagens local e Lync Server 2013](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

