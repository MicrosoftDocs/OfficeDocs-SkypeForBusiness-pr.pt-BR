---
title: Componentes de VoIP do servidor front-end para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: Saiba mais sobre os componentes do Enterprise Voice localizados em servidores front-end no Skype for Business Server, incluindo serviço de tradução e vários componentes de roteamento.
ms.openlocfilehash: d28beb809e172ea5d778e0cf8273cb232b7cf67c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276849"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>Componentes de VoIP do servidor front-end para o Skype for Business Server

Saiba mais sobre os componentes do Enterprise Voice localizados em servidores front-end no Skype for Business Server, incluindo serviço de tradução e vários componentes de roteamento.

Os componentes de VoIP localizados em servidores front-end são os seguintes:

- Serviço de Conversão

- Componente de Roteamento de Entrada

- Componente de Roteamento de Saída

- Componente de Roteamento da UM do Exchange

- Componente de roteamento entre clusters

- [Componente do servidor de mediação no Skype for Business Server](mediation-server.md)

## <a name="translation-service"></a>Serviço de Conversão

O Serviço de Conversão é o componente de servidor responsável pela conversão de um número discado no formato E.164 ou em outro formato, de acordo com as regras de normalização definidas pelo administrador. Esse serviço pode fazer a conversão para formatos que não sejam o E.164, caso a sua organização use um sistema de numeração particular ou um gateway ou PBX que não dê suporte a E.164.

## <a name="inbound-routing-component"></a>Componente de Roteamento de Entrada

O componente de roteamento de entrada manipula chamadas de entrada em grande parte de acordo com as preferências especificadas pelos usuários em seus clientes de voz corporativo. Também facilita a delegação de chamada e chamada simultânea, se configurada pelo usuário. Por exemplo, os usuários especificam se as chamadas não atendidas são encaminhadas ou simplesmente conectadas para notificação. Se o encaminhamento de chamadas estiver habilitado, os usuários poderão especificar se as chamadas não atendidas devem ser encaminhadas para outro número ou para um servidor do Exchange UM que tenha sido configurado para fornecer atendimento de chamada. O componente de roteamento de entrada é instalado por padrão em todos os servidores de front-end e de servidor Standard Edition.

## <a name="outbound-routing-component"></a>Componente de Roteamento de Saída

O componente de Roteamento de Saída direciona as chamadas para destinos do PBX ou PSTN. Ele aplica regras de autorização de chamadas, conforme definido pela política de voz do usuário, aos chamadores e determina o gateway PSTN ideal para direcionar cada chamada. O componente de roteamento de saída é instalado por padrão em todos os servidores padrão do servidor e front-end da edição.

A lógica de roteamento usada pelo Componente de Roteamento de Saída é, em grande parte, configurada pelos administradores de rede e de telefonia, de acordo com os requisitos das organizações.

## <a name="exchange-um-routing-component"></a>Componente de Roteamento da UM do Exchange

O componente de roteamento de UM do Exchange manipula o roteamento entre o Skype for Business Server e os servidores que executam o Exchange Unified Messaging (UM), para integrar o Skype for Business Server a recursos de Unificação de mensagens.

O componente de roteamento do Exchange UM também manipula o redirecionamento de caixa postal pela PSTN se os servidores do Exchange UM não estiverem disponíveis. Se você tiver usuários do Enterprise Voice em sites de filiais que não tenham um link de rede de longa distância adaptável para um site central, o aparelho de ramificação sobreviventes que você implantar no site de filiais permite a impossibilitação da caixa postal para os usuários da filial durante uma falha de WAN. Quando o link de WAN não está disponível, o aparelho de ramificação sobreviventes faz o seguinte:

- um novo roteamento de chamadas não respondidas sobre o PSTN para o servidor de Unificação de Mensagens do Exchange no site central

- fornece ao usuário a capacidade de recuperar mensagens de caixa postal sobre o PSTN

- coloca em fila notificações de chamada perdida e as carrega no servidor de UM do Exchange quando o link de WAN for restaurado.

Para habilitar o redirecionamento de caixa postal, recomendamos que o administrador do Exchange configure o atendedor automático do Exchange UM para aceitar somente mensagens.

Para obter detalhes sobre esses recursos, consulte [On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) e [Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx), respectivamente.

## <a name="intercluster-routing-component"></a>Componente de roteamento entre clusters

O componente de roteamento InterCluster é responsável por direcionar chamadas para o pool de registradores primários do chamador. Se isso não estiver disponível, o componente direcionará a chamada para o pool de registradores de backup do chamador. Se os pools de registradores primário e de backup do chamador estiverem inacessíveis na rede IP, o componente de roteamento InterCluster redirecionará a chamada pela PSTN para o número de telefone do usuário.

## <a name="other-front-end-server-components-required-for-voip"></a>Outros componentes de Servidor Front-End necessários ao VoIP

Outros componentes residentes no servidor front-end ou no director que fornecem suporte essencial para VoIP, mas não são componentes de VoIP, incluem o seguinte:

- **Serviços do Usuário.** Realiza a pesquisa de número inverso no telefone de destino para cada chamada de entrada e corresponde esse número ao URI SIP do usuário de destino. Usando essas informações, o componente de roteamento de entrada distribui a chamada aos pontos de extremidade SIP registrados do usuário. Os serviços de usuário são um componente principal em todos os servidores e directors de front-end.

- **Replicador do Usuário.** Extrai os números de telefone do usuário dos serviços de domínio Active Directory e os grava em tabelas no banco de dados RTC, onde eles estão disponíveis para os serviços de usuário e o servidor de catálogo de endereços. O Duplicador do usuário é um componente principal em todos os servidores de front-end.

- **Servidor do Catálogo de Endereço.** Fornece informações da lista de endereços global dos serviços de domínio do Active Directory para os clientes do Skype for Business Server. Ele também recupera as informações de usuário e de contato do banco de dados RTC, grava as informações nos arquivos do catálogo de endereços e, em seguida, armazena os arquivos em uma pasta compartilhada onde eles são baixados pelos clientes do Skype for Business. O servidor de catálogo de endereços grava as informações no banco de dados do RTCAb, que é usada pelo serviço de consulta à Web Catálogo de endereços para responder às consultas de pesquisa de usuários do Skype for Business Mobile. Ele também normaliza os números de telefone do usuário da empresa que são gravados no banco de dados RTC para fins de provisionamento de contatos do usuário no Skype for Business. O serviço de catálogo de endereços é instalado por padrão em todos os servidores de front-end. O serviço de consulta à Web do catálogo de endereços é instalado por padrão com os serviços Web em cada servidor front-end.


