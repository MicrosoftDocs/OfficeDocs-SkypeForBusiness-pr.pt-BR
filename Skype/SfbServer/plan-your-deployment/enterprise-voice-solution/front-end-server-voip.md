---
title: Componentes voIP do servidor front-end para Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: Saiba mais sobre os Enterprise Voice que estão localizados em Servidores Front-End em Skype for Business Server, incluindo o serviço de tradução e vários componentes de roteamento.
ms.openlocfilehash: 7af507cc7d00f06ac59543e87b4241a53d932193
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385469"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>Componentes voIP do servidor front-end para Skype for Business Server

Saiba mais sobre os Enterprise Voice que estão localizados em Servidores Front-End em Skype for Business Server, incluindo o serviço de tradução e vários componentes de roteamento.

Os componentes VoIP localizados em Servidores Front-End são os seguinte:

- Serviço de Conversão

- Componente de Roteamento de Entrada

- Componente de Roteamento de Saída

- Componente de Roteamento da UM do Exchange

- Componente de roteamento entre clusters

- [Componente do Servidor de Mediação Skype for Business Server](mediation-server.md)

## <a name="translation-service"></a>Serviço de Conversão

O Serviço de Conversão é o componente de servidor responsável pela conversão de um número discado no formato E.164 ou em outro formato, de acordo com as regras de normalização definidas pelo administrador. Esse serviço pode fazer a conversão para formatos que não sejam o E.164, caso a sua organização use um sistema de numeração particular ou um gateway ou PBX que não dê suporte a E.164.

## <a name="inbound-routing-component"></a>Componente de Roteamento de Entrada

O componente roteamento de entrada lida com chamadas de entrada em grande parte de acordo com as preferências especificadas pelos usuários em seus Enterprise Voice clientes. Também facilita a delegação de chamada e chamada simultânea, se configurada pelo usuário. Por exemplo, os usuários especificam se as chamadas não atendidas são encaminhadas ou simplesmente conectadas para notificação. Se o encaminhamento de chamadas estiver habilitado, os usuários poderão especificar se as chamadas não respondidas devem ser encaminhadas para outro número ou para um servidor de UM Exchange que foi configurado para fornecer atendimento de chamadas. O componente roteamento de entrada é instalado por padrão em todos os servidores Edição Standard e Servidores Front-End.

## <a name="outbound-routing-component"></a>Componente de Roteamento de Saída

O componente de Roteamento de Saída direciona as chamadas para destinos do PBX ou PSTN. Ele aplica regras de autorização de chamada, conforme definido pela política de voz do usuário, aos chamadores e determina o gateway PSTN ideal para rotear cada chamada. O componente roteamento de saída é instalado por padrão em todos os servidores Edição Standard e Servidores Front-End.

A lógica de roteamento usada pelo Componente de Roteamento de Saída é, em grande parte, configurada pelos administradores de rede e de telefonia, de acordo com os requisitos das organizações.

## <a name="exchange-um-routing-component"></a>Componente de Roteamento da UM do Exchange

O Exchange de roteamento de UM lida com o roteamento entre Skype for Business Server e servidores executando Exchange Unificação de Mensagens (UM), para integrar Skype for Business Server com recursos de Unificação de Mensagens.

O Exchange de roteamento de UM também lida com o redirecionar de caixa postal pela PSTN se Exchange servidores de UM não estão disponíveis. Se você tiver Enterprise Voice usuários em sites de filial que não tenham um link WAN resiliente para um site central, o Aparelho de Filial Persistente implantado no site de filial fornece sobrevivência de caixa postal para usuários de filial durante uma inatividade wan. Quando o link WAN está indisponível, o Aparelho de Filial Suportável faz o seguinte:

- faz um novo roteamento de chamadas não respondidas sobre o PSTN para o servidor de Unificação de Mensagens do Exchange no site central

- fornece ao usuário a capacidade de recuperar mensagens de caixa postal sobre o PSTN

- coloca em fila notificações de chamada perdida e as carrega no servidor de UM do Exchange quando o link de WAN for restaurado.

Para habilitar o redirecionamento de caixa postal, recomendamos que o administrador do Exchange configure Exchange um Atendedor Automático (AA) para aceitar apenas mensagens.

Para obter detalhes sobre esses recursos, consulte [On-Premises Exchange Unified Messaging Integration](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration) e [Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency), respectivamente.

## <a name="intercluster-routing-component"></a>Componente de roteamento entre clusters

O componente de roteamento Entrecluster é responsável pelo roteamento de chamadas para o pool de Registradores principal do chamador. Se isso não estiver disponível, o componente encaminha a chamada para o pool de Registradores de backup do chamador. Se os pools de Registradores primários e de backup do chamador não são acessíveis na rede IP, o componente de roteamento Entrecluster redireciona a chamada pelo PSTN para o número de telefone do usuário.

## <a name="other-front-end-server-components-required-for-voip"></a>Outros componentes de Servidor Front-End necessários ao VoIP

Outros componentes que residem no Servidor front-end ou diretor que fornecem suporte essencial para VoIP, mas não são componentes VoIP, incluem o seguinte:

- **Serviços do Usuário.** Realiza a pesquisa de número inverso no telefone de destino para cada chamada de entrada e corresponde esse número ao URI SIP do usuário de destino. Usando essas informações, o componente de Roteamento de Entrada distribui a chamada para os pontos de extremidade SIP registrados pelo usuário. Os Serviços do Usuário são um componente principal em todos os Servidores e Diretores front-end.

- **Replicador do Usuário.** Extrai números de telefone do usuário dos Serviços de Domínio do Active Directory e os grava em tabelas no banco de dados RTC, onde eles estão disponíveis para Serviços de Usuário e Servidor de Livro de Endereços. O Replicador de Usuários é um componente principal em todos os Servidores Front-End.

- **Servidor do Catálogo de Endereço.** Fornece informações de lista de endereços globais dos Serviços de Domínio do Active Directory para Skype for Business Server clientes. Ele também recupera informações de usuário e contato do banco de dados RTC, grava as informações nos arquivos do Livro de Endereços e armazena os arquivos em uma pasta compartilhada onde são baixados por clientes Skype for Business. O Servidor de Livro de Endereços grava as informações no banco de dados RTCAb, que é usado pelo serviço de Consulta Da Web do Livro de Endereços para responder às consultas de pesquisa do usuário Skype for Business celular. Ele, opcionalmente, normaliza os números de telefone do usuário corporativo gravados no banco de dados RTC com a finalidade de provisionar contatos de usuários no Skype for Business. O serviço de Livro de Endereços é instalado por padrão em todos os Servidores Front-End. O serviço de Consulta Web do Livro de Endereços é instalado por padrão com os serviços Web em cada Servidor Front-End.