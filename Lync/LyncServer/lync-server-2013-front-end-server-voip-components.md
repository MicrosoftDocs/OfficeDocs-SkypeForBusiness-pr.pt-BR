---
title: 'Lync Server 2013: componentes de VoIP do servidor front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3558d230b1fb767f0e7844be3894b579149c3f6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-server-voip-components-for-lync-server-2013"></a>Componentes de VoIP do servidor front-end para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-01_

Os componentes de VoIP localizados em servidores front-end são os seguintes:

  - Serviço de Conversão

  - Componente de Roteamento de Entrada

  - Componente de Roteamento de Saída

  - Componente de Roteamento da UM do Exchange

  - Componente de roteamento entre clusters

  - [Componente servidor de mediação no Lync Server 2013](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a>Serviço de Conversão

O Serviço de Conversão é o componente de servidor responsável pela conversão de um número discado no formato E.164 ou em outro formato, de acordo com as regras de normalização definidas pelo administrador. Esse serviço pode fazer a conversão para formatos que não sejam o E.164, caso a sua organização use um sistema de numeração particular ou um gateway ou PBX que não dê suporte a E.164.

</div>

<div>

## <a name="inbound-routing-component"></a>Componente de Roteamento de Entrada

O componente de roteamento de entrada manipula chamadas de entrada em grande parte de acordo com as preferências especificadas pelos usuários em seus clientes de voz corporativo. Também facilita a delegação de chamada e chamada simultânea, se configurada pelo usuário. Por exemplo, os usuários especificam se as chamadas não atendidas são encaminhadas ou simplesmente conectadas para notificação. Se o encaminhamento de chamadas estiver habilitado, os usuários poderão especificar se as chamadas não atendidas devem ser encaminhadas para outro número ou para um servidor do Exchange UM que tenha sido configurado para fornecer atendimento de chamada. O componente de roteamento de entrada é instalado por padrão em todos os servidores de front-end e de servidor Standard Edition.

</div>

<div>

## <a name="outbound-routing-component"></a>Componente de Roteamento de Saída

O componente de Roteamento de Saída direciona as chamadas para destinos do PBX ou PSTN. Aplica regras de autorização de chamada para ligadores, conforme definido pela política de voz do usuário, e determina o melhor gateway PSTN para roteamento de cada chamada. O componente de roteamento de saída é instalado por padrão em todos os servidores padrão do servidor e front-end da edição.

A lógica de roteamento usada pelo Componente de Roteamento de Saída é, em grande parte, configurada pelos administradores de rede e de telefonia, de acordo com os requisitos das organizações.

</div>

<div>

## <a name="exchange-um-routing-component"></a>Componente de Roteamento da UM do Exchange

O componente de roteamento de UM do Exchange manipula o roteamento entre o Lync Server e os servidores que executam o Exchange Unified Messaging (UM), para integrar o Lync Server com recursos de Unificação de mensagens

O componente de roteamento do Exchange UM também manipula o redirecionamento de caixa postal pela PSTN se os servidores do Exchange UM não estiverem disponíveis. Se você tiver usuários do Enterprise Voice em sites de filiais que não tenham um link de rede de longa distância adaptável para um site central, o aparelho de ramificação sobreviventes que você implantar no site de filiais permite a impossibilitação da caixa postal para os usuários da filial durante uma falha de WAN. Quando o link de WAN não está disponível, o aparelho de ramificação sobreviventes faz o seguinte:

  - um novo roteamento de chamadas não respondidas sobre o PSTN para o servidor de Unificação de Mensagens do Exchange no site central

  - fornece ao usuário a capacidade de recuperar mensagens de caixa postal sobre o PSTN

  - coloca em fila notificações de chamada perdida e as carrega no servidor de UM do Exchange quando o link de WAN for restaurado.

Para habilitar o redirecionamento de caixa postal, recomendamos que o administrador do Exchange configure o atendedor automático do Exchange UM para aceitar somente mensagens.

Para obter detalhes sobre esses recursos, consulte [planejando a integração de Unificação de mensagens do Exchange no Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e [planejando a resiliência para Enterprise Voice no Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectivamente.

</div>

<div>

## <a name="intercluster-routing-component"></a>Componente de roteamento entre clusters

O componente de roteamento entre clusters é responsável por rotear chamadas ao pool de registradores principal do chamador. Se essa opção não estiver disponível, o componente roteará a chamada para o pool de registradores de backup de quem recebe a chamada. Se os pools de registradores principal e de backup de quem recebe a chamada não puderem ser acessados pela rede IP, o componente de roteamento entre clusters roteará novamente a chamada sobre o PSTN para o número de telefone do usuário.

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a>Outros componentes de Servidor Front-End necessários ao VoIP

Outros componentes residentes no servidor front-end ou no director que fornecem suporte essencial para VoIP, mas não são componentes de VoIP, incluem o seguinte:

  - **Serviços do Usuário.** Realiza a pesquisa de número inverso no telefone de destino para cada chamada de entrada e corresponde esse número ao URI SIP do usuário de destino. Usando esta informação o componente de Roteamento de Entrada distribui a chamada para os pontos de extremidade SIP registrados do usuário. Os serviços de usuário são um componente principal em todos os servidores e directors de front-end.

  - **Replicador do Usuário.** Extrai os números de telefone do usuário dos serviços de domínio Active Directory e os grava em tabelas no banco de dados RTC, onde eles estão disponíveis para os serviços de usuário e o servidor de catálogo de endereços. O Duplicador do usuário é um componente principal em todos os servidores de front-end.

  - **Servidor do Catálogo de Endereço.** Fornece informações da lista de endereços global dos serviços de domínio Active Directory para clientes do Lync Server. Ele também recupera informações de usuário e de contato do banco de dados RTC, grava as informações nos arquivos do catálogo de endereços e, em seguida, armazena os arquivos em uma pasta compartilhada onde eles são baixados pelos clientes do Lync. O servidor de catálogo de endereços grava as informações no banco de dados do RTCAb, que é usada pelo serviço de consulta à Web Catálogo de endereços para responder às consultas de pesquisa de usuários do Microsoft Lync 2010 Mobile. Ele também normaliza os números de telefone do usuário da empresa que são gravados no banco de dados RTC para fins de provisionamento de contatos do usuário no Lync. O serviço de catálogo de endereços é instalado por padrão em todos os servidores de front-end. O serviço de consulta à Web do catálogo de endereços é instalado por padrão com os serviços Web em cada servidor front-end.

</div>

</div>

<span> </span>

</div>

</div>

</div>

