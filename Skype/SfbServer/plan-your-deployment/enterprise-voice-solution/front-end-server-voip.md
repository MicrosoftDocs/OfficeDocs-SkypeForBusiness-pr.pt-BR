---
title: Componentes VoIP do Servidor Front-End no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: Saiba mais sobre os componentes do Enterprise Voice que estão localizados em servidores Front End Skype para Business Server, incluindo o serviço de tradução e vários componentes de roteamento.
ms.openlocfilehash: a95b437128f7ddb8dd78462d3a8443e972dd75bc
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="front-end-server-voip-components-for-skype-for-business-server-2015"></a>Componentes VoIP do Servidor Front-End no Skype for Business Server 2015
 
Saiba mais sobre os componentes do Enterprise Voice que estão localizados em servidores Front End Skype para Business Server, incluindo o serviço de tradução e vários componentes de roteamento.
  
Os componentes de VoIP localizados nos servidores Front-End são:
  
- Serviço de Conversão
    
- Componente de Roteamento de Entrada
    
- Componente de Roteamento de Saída
    
- Componente de Roteamento da UM do Exchange
    
- Componente de roteamento entre clusters
    
- [Componente do servidor de mediação no Skype para Business Server 2015](mediation-server.md)
    
## <a name="translation-service"></a>Serviço de Conversão

O Serviço de Conversão é o componente de servidor responsável pela conversão de um número discado no formato E.164 ou em outro formato, de acordo com as regras de normalização definidas pelo administrador. Esse serviço pode fazer a conversão para formatos que não sejam o E.164, caso a sua organização use um sistema de numeração particular ou um gateway ou PBX que não dê suporte a E.164.
  
## <a name="inbound-routing-component"></a>Componente de Roteamento de Entrada

O componente de roteamento de entrada trata as chamadas de entrada basicamente de acordo com as preferências especificadas pelos usuários em seus clientes Enterprise Voice. Também facilita a delegação de chamada e chamada simultânea, se configurada pelo usuário. Por exemplo, os usuários especificam se as chamadas não atendidas são encaminhadas ou simplesmente conectadas para notificação. Se o encaminhamento de chamadas está habilitado, os usuários podem especificar se as chamadas não atendidas devem ser encaminhadas para outro número ou para um servidor de UM do Exchange que foi configurado para fornecer atendimento de chamadas. O componente de roteamento de entrada é instalado por padrão em todos os servidores Standard Edition e servidores Front-End. 
  
## <a name="outbound-routing-component"></a>Componente de Roteamento de Saída

O componente de Roteamento de Saída direciona as chamadas para destinos do PBX ou PSTN. Ele aplica regras de autorização de chamada, conforme definido pela política de voz do usuário, aos chamadores e determina o gateway PSTN ideal para cada chamada de roteamento. O componente de roteamento de saída é instalado por padrão em todos os servidores Standard Edition e servidores Front-End.
  
A lógica de roteamento usada pelo Componente de Roteamento de Saída é, em grande parte, configurada pelos administradores de rede e de telefonia, de acordo com os requisitos das organizações. 
  
## <a name="exchange-um-routing-component"></a>Componente de Roteamento da UM do Exchange

O componente de roteamento UM do Exchange manipula o roteamento entre Skype para Business Server e os servidores que executam o Exchange Unified Messaging (UM), para integrar o Skype para Business Server com os recursos de Unificação de mensagens. 
  
O componente de roteamento UM do Exchange também trata do reencaminhamento de caixa postal no PSTN se servidores UM do Exchange não estiver disponíveis. Se você tiver usuários do Enterprise Voice em sites de filiais que não possuem uma WAN resiliente vincular a um site central, o aparelho de filial persistente que ser implantado no site da filial fornece persistência da caixa postal para usuários de filiais durante uma interrupção da WAN. Quando o link de WAN não estiver disponível, o aparelho de filial persistente faz o seguinte:
  
- um novo roteamento de chamadas não respondidas sobre o PSTN para o servidor de Unificação de Mensagens do Exchange no site central
    
- fornece ao usuário a capacidade de recuperar mensagens de caixa postal sobre o PSTN
    
- coloca em fila notificações de chamada perdida e as carrega no servidor de UM do Exchange quando o link de WAN for restaurado.
    
Para habilitar o redirecionamento de correio de voz, é recomendável que o administrador do Exchange configure Exchange UM AA (atendedor automático) para aceitar apenas mensagens.
  
Para obter detalhes sobre esses recursos, consulte [On-Premises Exchange Unified Messaging Integration](http://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) e [Planning for Enterprise Voice Resiliency](http://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx), respectivamente.
  
## <a name="intercluster-routing-component"></a>Componente de roteamento entre clusters

O componente de roteamento entre clusters é responsável pelo roteamento de chamadas para o pool de registradores primário do receptor. Se não estiver disponível, o componente roteia a chamada para o pool registrador de backup do receptor. Se os pools de registradores primários e de backup do receptor estão inacessíveis pela rede IP, o componente de roteamento entre clusters redireciona a chamada no PSTN para o número de telefone do usuário.
  
## <a name="other-front-end-server-components-required-for-voip"></a>Outros componentes de Servidor Front-End necessários ao VoIP

Outros componentes residentes no servidor Front-End ou diretor que fornecem suporte essencial para VoIP, mas não são componentes VoIP, incluem o seguinte:
  
- **Serviços do Usuário.** Realiza a pesquisa de número inverso no telefone de destino para cada chamada de entrada e corresponde esse número ao URI SIP do usuário de destino. Usando essa informação, o componente de roteamento de entrada distribui a chamada para os pontos de extremidade de SIP registrados desse usuário. Serviços do usuário é um componente essencial em todos os servidores Front-End e diretores.
    
- **Replicador do Usuário.** Extrai os números de telefone do usuário dos serviços de domínio Active Directory e os grava em tabelas no banco de dados RTC, onde eles estão disponíveis para os serviços de usuário e o servidor do catálogo de endereços. Replicador de usuário é um componente essencial em todos os servidores Front-End.
    
- **Servidor do Catálogo de Endereço.** Fornece informações da lista de endereços global dos serviços de domínio do Active Directory para Skype para clientes Business Server. Ele também recupera informações de usuário e contato do banco de dados RTC, grava as informações para os arquivos do catálogo de endereços e, em seguida, armazena os arquivos em uma pasta compartilhada onde elas são baixadas pelo Skype para clientes corporativos. O servidor de catálogo de endereços grava as informações no banco de dados RTCAb, que é usado pelo serviço Address Book Web Query para responder a consultas de pesquisa do usuário de Skype para negócios móveis. Opcionalmente, ele normaliza números de telefone do usuário de empresa que são gravados no banco de dados RTC para fins de provisionamento de contatos do usuário no Skype para negócios. O serviço de catálogo de endereços é instalado por padrão em todos os servidores Front-End. O serviço Address Book Web Query é instalado por padrão com os serviços Web em cada servidores Front-End.
    

