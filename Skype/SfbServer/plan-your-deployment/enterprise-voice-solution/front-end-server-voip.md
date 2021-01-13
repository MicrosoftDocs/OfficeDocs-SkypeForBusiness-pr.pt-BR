---
title: Componentes VoIP do Servidor Front End para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: Saiba mais sobre os componentes do Enterprise Voice localizados nos Servidores front-end no Skype for Business Server, incluindo o serviço de tradução e vários componentes de roteamento.
ms.openlocfilehash: fcf1e30c0f6bbe0a292de54e4cc4b264774f9c7f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825651"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>Componentes VoIP do Servidor Front End para o Skype for Business Server

Saiba mais sobre os componentes do Enterprise Voice localizados nos Servidores front-end no Skype for Business Server, incluindo o serviço de tradução e vários componentes de roteamento.

Os componentes VoIP localizados em Servidores Front-End são os seguinte:

- Serviço de Conversão

- Componente de Roteamento de Entrada

- Componente de Roteamento de Saída

- Componente de Roteamento da UM do Exchange

- Componente de roteamento entre clusters

- [Componente do Servidor de Mediação no Skype for Business Server](mediation-server.md)

## <a name="translation-service"></a>Serviço de Conversão

O Serviço de Conversão é o componente de servidor responsável pela conversão de um número discado no formato E.164 ou em outro formato, de acordo com as regras de normalização definidas pelo administrador. Esse serviço pode fazer a conversão para formatos que não sejam o E.164, caso a sua organização use um sistema de numeração particular ou um gateway ou PBX que não dê suporte a E.164.

## <a name="inbound-routing-component"></a>Componente de Roteamento de Entrada

O componente de Roteamento de Entrada lida com chamadas de entrada em grande parte de acordo com as preferências especificadas pelos usuários em seus clientes do Enterprise Voice. Também facilita a delegação de chamada e chamada simultânea, se configurada pelo usuário. Por exemplo, os usuários especificam se as chamadas não atendidas são encaminhadas ou simplesmente conectadas para notificação. Se o encaminhamento de chamadas estiver habilitado, os usuários poderão especificar se as chamadas não respondidas devem ser encaminhadas para outro número ou para um servidor um do Exchange que tenha sido configurado para fornecer atendimento de chamadas. O componente de Roteamento de Entrada é instalado por padrão em todos os servidores Standard Edition e Servidores Front-End.

## <a name="outbound-routing-component"></a>Componente de Roteamento de Saída

O componente de Roteamento de Saída direciona as chamadas para destinos do PBX ou PSTN. Ele aplica regras de autorização de chamada, conforme definido pela política de voz do usuário, aos chamadores e determina o gateway PSTN ideal para rotear cada chamada. O componente roteamento de saída é instalado por padrão em todos os servidores Standard Edition e servidores front-end.

A lógica de roteamento usada pelo Componente de Roteamento de Saída é, em grande parte, configurada pelos administradores de rede e de telefonia, de acordo com os requisitos das organizações.

## <a name="exchange-um-routing-component"></a>Componente de Roteamento da UM do Exchange

O componente de roteamento de UM do Exchange lida com o roteamento entre o Skype for Business Server e os servidores que executam a Unificação de Mensagens (UM) do Exchange, para integrar o Skype for Business Server aos recursos de Unificação de Mensagens.

O componente de roteamento de UM do Exchange também trata do re-roteamento da caixa postal pela PSTN se os servidores um do Exchange não estão disponíveis. Se você tiver usuários do Enterprise Voice em sites de filial que não possuem um link WAN resiliente para um site central, o Aparelho de Filial Persistente implantado no site de filial fornece a sobrevivência da caixa postal para usuários de filiais durante uma paralisação wan. Quando o link WAN está indisponível, o Aparelho de FilialVivível faz o seguinte:

- faz um novo roteamento de chamadas não respondidas sobre o PSTN para o servidor de Unificação de Mensagens do Exchange no site central

- fornece ao usuário a capacidade de recuperar mensagens de caixa postal sobre o PSTN

- coloca em fila notificações de chamada perdida e as carrega no servidor de UM do Exchange quando o link de WAN for restaurado.

Para habilitar o re-redirecionamento de caixa postal, recomendamos que seu administrador do Exchange configure o AA (Exchange UM Auto Attendant) para aceitar apenas mensagens.

Para obter detalhes sobre esses recursos, consulte [On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) e [Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx), respectivamente.

## <a name="intercluster-routing-component"></a>Componente de roteamento entre clusters

O componente de roteamento entre grupo é responsável pelo roteamento de chamadas para o pool de Registradores Registradores principal do chamador. Se não estiver disponível, o componente encaminha a chamada para o pool de Registradores De backup do destinatário da chamada. Se os pools do Registrador principal e de backup do destinatário da chamada não podem ser acessíveis pela rede IP, o componente de roteamento entre grupo redireciona a chamada sobre o PSTN para o número de telefone do usuário.

## <a name="other-front-end-server-components-required-for-voip"></a>Outros componentes de Servidor Front-End necessários ao VoIP

Outros componentes que residem no Servidor de Front End ou diretor que oferecem suporte essencial para VoIP, mas não são componentes VoIP, incluem o seguinte:

- **Serviços do Usuário.** Realiza a pesquisa de número inverso no telefone de destino para cada chamada de entrada e corresponde esse número ao URI SIP do usuário de destino. Usando essas informações, o componente de Roteamento de Entrada distribui a chamada para os pontos de extremidade SIP registrados desse usuário. Os Serviços do Usuário são um componente principal em todos os Servidores e Diretores front-end.

- **Replicador do Usuário.** Extrai os números de telefone do usuário dos Serviços de Domínio Active Directory e grava-os em tabelas no banco de dados RTC, onde eles estão disponíveis para os Serviços do Usuário e o Servidor do Address Book. O Replicador de usuários é um componente principal em todos os Servidores Front-End.

- **Servidor do Catálogo de Endereço.** Fornece informações da lista de endereços global dos Serviços de Domínio Active Directory para clientes do Skype for Business Server. Ele também recupera informações de usuário e contato do banco de dados RTC, grava as informações nos arquivos do Address Book e armazena os arquivos em uma pasta compartilhada onde eles são baixados pelos clientes do Skype for Business. O Servidor de Agenda grava as informações no banco de dados RTCAb, que é usado pelo serviço de Consulta à Web do Address Book para responder às consultas de pesquisa do usuário do Skype for Business Mobile. Opcionalmente, normaliza os números de telefone de usuários corporativos gravados no banco de dados RTC para fins de provisionamento de contatos do usuário no Skype for Business. O serviço de Agendamento de Endereços é instalado por padrão em todos os Servidores Front-End. O serviço de Consulta à Web do Address Book é instalado por padrão com os serviços Web em cada Servidor Front-End.


