---
title: Planejar o Location-Based roteamento no Skype for Business
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
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: Planejamento para roteamento baseado em local no Skype for Business Server Enterprise Voice, incluindo interação com toque e delegação simultâneos e cenários com suporte para roteamento baseado em local.
ms.openlocfilehash: 99a76d3cda40bb1fdc71bdffc7f6c896c96c5cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101477"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Planejar o Location-Based roteamento no Skype for Business

Planejamento para roteamento baseado em local no Skype for Business Server Enterprise Voice, incluindo interação com toque e delegação simultâneos e cenários com suporte para roteamento baseado em local.

Location-Based roteamento possibilita restringir o roteamento de chamadas entre pontos de extremidade VoIP e pontos de extremidade PSTN com base no local das partes na chamada. Location-Based Routing é um recurso de gerenciamento de chamadas que controla como as chamadas são roteadas pelo Skype for Business Server. Ele impõe regras de autorização de chamada sobre se as chamadas podem ser roteados para pontos de extremidade PBX ou PSTN com base na localização geográfica do chamador do Skype for Business.

Location-Based routing introduz um novo conjunto de regras que modifica o roteamento de chamadas PSTN nacionais e internacionais para evitar o desvio de chamada Location-Based Routing fornece a flexibilidade para escopo dessas regras para regiões específicas, gateways específicos ou para um conjunto específico de usuários.

Os cenários a seguir ilustram os principais tipos de restrições que o roteamento Location-Based pode impor:

- Chamadas de saída - o roteamento Location-Based pode impor chamadas de saída para saída a um gateway PSTN localizado na mesma região em que o chamador deve impedir o desvio de chamada PSTN, o que impede chamadas para saída para um gateway PSTN localizado em uma região diferente do chamador.

- Chamadas de entrada - Location-Based Roteamento pode impedir chamadas PSTN de entrada para tocar pontos de extremidade do Skype for Business se o gateway PSTN que roteia a chamada de entrada não estiver localizado na mesma região que o usuário chamado Skype for Business.

- Regiões desconhecidas - Location-Based Roteamento restringe chamadas PSTN de entrada e saída de usuários que estão localizados em locais indeterminados (ou seja, usuários remotos que se conectam da Internet ou localizados em regiões desconhecidas).

- Regiões internacionais - Location-Based Roteamento impõe o roteamento de chamadas de saída por meio de gateways PSTN internacionais se um gateway local para a localização do usuário não puder ser encontrado.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>Diretrizes para onde aplicar Location-Based Routing

Location-Based Roteamento, dependendo da situação, pode ser aplicado no local do site de rede do ponto de extremidade do usuário ou no local do site de rede do gateway PSTN. Este tópico fornece orientações sobre como o roteamento Location-Based é aplicado.

### <a name="applying-location-based-routing-at-the-users-location"></a>Aplicando Location-Based roteamento no local do usuário

Location-Based Roteamento aproveita as mesmas regiões de rede, sites e sub-redes definidas no Skype for Business Server usado pelo E9-1-1, CAC e Desvio de Mídia para aplicar restrições de roteamento de chamadas para impedir o desvio de chamada PSTN. A localização de um usuário é determinada pela sub-rede IP dos pontos de extremidade do Skype for Business do usuário que estão conectados. Cada sub-rede IP é associada a um site de rede, que é agregado em regiões de rede definidas pelo administrador. Location-Based Roteamento é imposto com base no site de rede do usuário.

Location-Based regras de roteamento são aplicadas por site de rede, o que significa que um determinado conjunto de regras será aplicado a todos os pontos de extremidade habilitados para o roteamento Location-Based que estão localizados no mesmo site de rede. Os administradores podem aplicar Location-Based roteamento a sites de rede que o exigem.

As políticas de roteamento de voz podem ser definidas por site de rede para definir um gateway PSTN específico que deve ser usado por todos os usuários localizados no site de rede para chamar números de telefone PSTN. Essas políticas de roteamento de voz terão precedência sobre o roteamento definido pela política de voz do usuário quando o usuário estiver localizado em um site de rede habilitado para roteamento de Location-Based e impedirá o roteamento de chamadas por meio de outros gateways PSTN habilitados para roteamento Location-Based. Quando um usuário do Skype for Business faz uma chamada PSTN, a política de voz do usuário determina se o usuário pode ser autorizado a fazer a chamada. Se a política de voz do usuário permitir que o usuário coloque a chamada, Location-Based Routing determinará de qual gateway PSTN a chamada deverá surgir. Location-Based Routing faz essa determinação com base na localização do usuário.

Um local do usuário pode ser categorizado das seguintes maneiras:

- O usuário está localizado em um site de rede conhecido habilitado para roteamento Location-Based e seu número DID (Direct Inward Dial) termina em um gateway PSTN colocado no mesmo site de rede (ou seja, office). O roteamento de chamadas de saída será por meio da política de roteamento de voz do site de rede no qual o usuário está localizado. Chamadas PSTN de entrada para o usuário são roteados para pontos de extremidade localizados no mesmo site de rede que o gateway PSTN.

- O usuário está localizado em um site de rede conhecido que está em diferente do site de rede onde o gateway PSTN está localizado. (ou seja, o usuário foi para outro escritório corporativo). O roteamento de chamadas de saída estará usando a política de roteamento de voz do site de rede no qual o usuário está localizado. As chamadas PSTN de entrada para o usuário não serão roteados para pontos de extremidade localizados em sites diferentes do gateway PSTN para evitar o desvio de chamada de PSTN.

- Quando um usuário está localizado em um site de rede desconhecido para a implantação do Skype for Business Server, o roteamento de chamadas de saída será baseado na política de voz atribuída ao usuário para gateways PSTN não vinculados a restrições de roteamento Location-Based. As chamadas PSTN de entrada não serão roteados para pontos de extremidade localizados em sites de rede desconhecidos para impedir o desvio de chamada de PSTN.

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Aplicando Location-Based roteamento no local do gateway PSTN

As chamadas roteada por meio de gateways PSTN e PBXs podem exigir Location-Based restrições de roteamento, dependendo da localização desses sistemas. Location-Based Roteamento pode ser habilitado na granularidade por tronco.

Location-Based Routing apresenta o seguinte conjunto de regras quando habilitado em um tronco:

- Quando Location-Based roteamento é habilitado por tronco, as regras definidas nesse tronco serão aplicadas somente a chamadas roteada por esse tronco.

- Para evitar o desvio de tarifas PSTN em que as chamadas se originam de um site de rede diferente do site de rede em que o gateway PSTN está localizado, o roteamento Location-Based apresenta a associação de um site de rede a um determinado tronco. Isso define o site de rede que permite que as chamadas sejam roteados para um determinado tronco.

Os troncos podem ser habilitados para Location-Based roteamento de duas maneiras:

- O tronco é definido para um gateway PSTN que egresse chamadas para a PSTN. As chamadas de entrada roteadas por um tronco desse tipo serão roteadas somente para pontos de extremidade localizados no mesmo site de rede que o tronco.

- O tronco é definido para um par do Servidor de Mediação que não egressa chamadas para a PSTN e serviços usuários com telefones herdado em locais estáticos (ou seja, telefones PBX). Para essa configuração específica, todas as chamadas de entrada roteadas por um tronco desse tipo serão consideradas originadas do mesmo site de rede do tronco. As chamadas dos usuários pbx terão a mesma Location-Based roteamento que os usuários do Skype for Business localizados no mesmo site de rede do tronco. Se dois sistemas PBX localizados em sites de rede separados estão conectados por meio do Skype for Business Server, o roteamento Location-Based permitirá o roteamento de um ponto de extremidade PBX em um site de rede para outro ponto de extremidade PBX no outro site de rede. Esse cenário não será bloqueado por Location-Based Routing. Além desse cenário e de forma semelhante a um usuário do Skype for Business no mesmo local, os pontos de extremidade conectados a um par do Servidor de Mediação com essa configuração poderão fazer ou receber chamadas de e para outro par do Servidor de Mediação que não roteiem chamadas para o PSTN (ou seja, um ponto de extremidade conectado a um PBX diferente) independentemente do site de rede ao qual o par do Servidor de Mediação está associado. Todas as chamadas de entrada, chamadas de saída, transferências de chamadas e encaminhamentos de chamadas envolvendo pontos de extremidade PSTN estarão sujeitas ao Roteamento Baseado em Local para usar somente gateways PSTN definidos como locais para esse ponto do Servidor de Mediação.

## <a name="scenarios-for-location-based-routing"></a>Cenários para roteamento de Location-Based

Location-Based Routing aplica as seguintes regras gerais ao rotear chamadas nos cenários a seguir.

### <a name="outgoing-calls"></a>Chamadas de saída

O roteamento de chamadas de saída de usuários habilitados para Location-Based roteamento é afetado pelo local de rede do ponto de extremidade do usuário. A tabela a seguir ilustra como Location-Based Roteamento afeta o roteamento de chamadas de saída, dependendo do local do ponto de extremidade do chamador.

**Chamador fazendo uma chamada de saída para o PSTN**

||**Ponto de extremidade do usuário localizado em um site de rede habilitado para roteamento Location-Based usuário**|**Ponto de extremidade do usuário localizado em site de rede desconhecido ou não habilitado para roteamento Location-Based usuário**|
|:-----|:-----|:-----|
|Autorização de chamadas de saída  <br/> |A chamada é autorizada com base na política de voz do usuário  <br/> |A chamada é autorizada com base na política de voz do usuário  <br/> |
|Roteamento de chamada de saída  <br/> |A chamada é roteada de acordo com a política de roteamento de voz do site de rede  <br/> |A chamada é roteada de acordo com a política de voz do usuário e somente por troncos não habilitados para roteamento de Location-Based (se disponível)  <br/> |

### <a name="incoming-calls"></a>Chamadas de entrada

O roteamento de chamadas de entrada para usuários habilitados para Location-Based roteamento depende do local do ponto de extremidade do usuário. O roteamento de chamadas de entrada é afetado da seguinte maneira. Se um usuário tiver uma chamada de entrada para um ponto de extremidade localizado em um site de rede habilitado para roteamento Location-Based e o ponto de extremidade estiver localizado no mesmo site de rede que o gateway PSTN, a chamada será roteada. Se um usuário tiver uma chamada de entrada para um ponto de extremidade localizado em um site de rede habilitado para roteamento Location-Based e o ponto de extremidade estiver localizado em um site de rede diferente do gateway PSTN, a chamada não será roteada. Quando um usuário não tem pontos de extremidade localizados no mesmo site de rede do gateway PSTN de onde a chamada de entrada é originada, a chamada de entrada será roteada diretamente para a caixa postal do usuário e uma notificação de chamada perdida será enviada para a parte chamada.

As configurações de encaminhamento de chamadas de um usuário habilitado para roteamento Location-Based continuarão a ser impostas, no entanto, as chamadas encaminhadas estarão sujeitas a restrições de roteamento Location-Based do usuário.

A tabela a seguir ilustra como Location-Based roteamento afeta o roteamento de chamadas de entrada, dependendo do local do ponto de extremidade do chamador. O site de rede do gateway PSTN está habilitado para roteamento Location-Based, e o roteamento Location-Based permite apenas o roteamento de chamadas PSTN para pontos de extremidade no mesmo site de rede.

**Chamador que recebe uma chamada de entrada do PSTN**

||**Ponto de extremidade do chamador localizado no mesmo site de rede que o gateway PSTN**|**Ponto de extremidade do chamador não localizado no mesmo site de rede que o gateway PSTN**|**Ponto de extremidade do chamador localizado em site de rede desconhecido ou não habilitado para roteamento Location-Based**|
|:-----|:-----|:-----|:-----|
|Roteamento de chamada PSTN de entrada  <br/> |A chamada de entrada é roteada para os pontos de extremidade do chamador  <br/> |A chamada de entrada não é roteada para os pontos de extremidade do chamador  <br/> |A chamada de entrada não é roteada para os pontos de extremidade do chamador  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>Transferências de chamada e encaminhamento de chamada

Quando um ponto de extremidade PSTN está envolvido, Location-Based Routing analisa o local do ponto de extremidade do chamador e o ponto de extremidade para o qual a chamada será transferida ou encaminhada (ou seja, destino de transferência/encaminhamento). Location-Based Routing determina se a chamada deve ser transferida ou encaminhada, dependendo do local dos dois pontos de extremidade.

A tabela a seguir ilustra o cenário de um usuário do Skype for Business em uma chamada com um ponto de extremidade PSTN, e o usuário do Skype for Business transfere a chamada para outro usuário do Skype for Business. Dependendo do local do site de rede do ponto de extremidade do transferidor, Location-Based Roteamento afeta o roteamento da transferência de chamada ou encaminhamento.

**Iniciando transferência de chamada ou encaminhamento**

|**Usuário iniciando a transferência/encaminhamento de chamada**|**O ponto de extremidade de destino está no mesmo site de rede que o usuário iniciando a transferência ou encaminhamento de chamada**|**O ponto de extremidade de destino está em um site de rede diferente à medida que o usuário inicia a transferência ou encaminhamento de chamada**|**O ponto de extremidade de destino está em site de rede ou site de rede desconhecido não habilitado para Location-Based Routing**|
|:-----|:-----|:-----|:-----|
|Usuário do Skype for Business  <br/> |O encaminhamento de chamada ou a transferência são permitidos  <br/> |Não é permitido encaminhar ou transferir chamada  <br/> |Não é permitido encaminhar ou transferir chamada  <br/> |

Por exemplo: um usuário do Skype for Business em uma chamada com um ponto de extremidade PSTN transfere a chamada para outro usuário do Skype for Business que está no mesmo site de rede. Nesse caso, a transferência de chamada é permitida.

A tabela a seguir ilustra o cenário de um usuário do Skype for Business em uma chamada com outro usuário do Skype for Business e um dos usuários transfere a chamada para um ponto de extremidade PSTN. Dependendo do local do usuário para o qual a chamada está sendo transferida, a tabela detalha como o roteamento Location-Based afeta a chamada.

**Transferência de chamada ou encaminhamento para o ponto de extremidade PSTN**

|**Destino do ponto de extremidade de transferência/encaminhamento de chamada**|**Usuários do Skype for Business no mesmo site de rede**|**Usuários do Skype for Business em sites de rede diferentes**|**Um ou ambos usuários do Skype for Business em site de rede desconhecido ou site de rede não habilitado para Location-Based Routing**|
|:-----|:-----|:-----|:-----|
|Ponto de extremidade PSTN  <br/> |Encaminhar ou transferir chamadas permitidas pela política de roteamento de voz do site do usuário transferido  <br/> |Encaminhar ou transferir chamadas permitidas pela política de roteamento de voz do site do usuário transferido  <br/> |Encaminhar ou transferir chamadas permitidas pela política de voz do usuário transferido somente por meio de troncos não habilitados para roteamento Location-Based roteamento  <br/> |

Por exemplo: um usuário do Skype for Business em uma chamada com outro usuário do Skype for Business que está no mesmo site de rede transfere a chamada para um ponto de extremidade PSTN e a transferência de chamada é permitida.

### <a name="simultaneous-ringing"></a>Toque simultâneo

Quando a parte chamada tem toque simultâneo habilitado, Location-Based Routing analisa o local da parte de chamada e os pontos de extremidade das partes chamadas para determinar se a chamada deve ser roteada.

A tabela a seguir ilustra um usuário configurado com toque simultâneo, e o destino de toque simultâneo é um usuário no mesmo site de rede, em um site de rede diferente ou em um site de rede desconhecido.

****

|**Chamada PSTN de entrada para**|**Localizado no mesmo site de rede que o chamador**|**Localizado em um site de rede diferente do chamador**|**Localizado em site de rede desconhecido ou não habilitado para roteamento Location-Based.**|
|:-----|:-----|:-----|:-----|
|Usuário do Skype for Business  <br/> |Anel simultâneo permitido  <br/> |Anel simultâneo não permitido  <br/> |Anel simultâneo não permitido  <br/> |

A tabela a seguir ilustra uma chamada de um usuário do Skype for Business (ou seja, chamador do Skype for Business) no mesmo site de rede, em um site de rede diferente ou em um site de rede desconhecido. O chamador tem um ponto de extremidade PSTN (ou seja, celular) configurado como um destino de anel simultâneo. Nesse cenário, Location-Based Routing determinará se a chamada deve ser roteada para o destino de anel simultâneo (ou seja, celular) do chamador ou não.

****

|**Destino de anel simultâneo**|**Localizado no mesmo site de rede que o chamador**|**Localizado em um site de rede diferente do chamador**|**Localizado em site de rede desconhecido ou não habilitado para roteamento Location-Based.**|
|:-----|:-----|:-----|:-----|
|Ponto de extremidade PSTN  <br/> |Toque simultâneo permitido por meio da política de roteamento de voz do site do chamador  <br/> |Toque simultâneo permitido por meio da política de roteamento de voz do site do chamador  <br/> |Anel simultâneo permitido por meio da política de voz do chamador para troncos não habilitados para roteamento Location-Based  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Atualização Cumulativa 4 do Skype for Business

Com a Atualização Cumulativa 4, você verá o seguinte:

- Location-Based Roteamento continuará habilitado por meio da Política de Voz, incluindo clientes skype for Business Mobile.

- O comportamento de chamada para clientes skype for Business Mobile será baseado em se eles estão habilitados para roteamento Location-Based e o cliente de comunicação. Isso foi projetado para ser estático, mas pode haver, em determinadas situações, um esforço para associar um cliente skype for Business Mobile a um gateway PSTN local e permitir determinados comportamentos, como uma escalada

- Independentemente do seu sistema operacional, seu cliente Skype for Business Mobile deve ter a mesma funcionalidade.

A tabela a seguir o acompanhará em alguns dos cenários pós-cumulativo da Atualização 4:

|**Usuário de roteamento baseado em local**|**Outra parte**|**Ação**|**Resultado**|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |O Skype for Business Mobile recebe uma chamada PSTN de entrada.  <br/> |A chamada é roteada por Meio de Chamada via Trabalho (CvW) e não por VoIP.  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |O Skype for Business Mobile faz uma chamada PSTN de saída.  <br/> |A chamada é roteada por CvW e não por VoIP.  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |O Skype for Business Mobile está em uma chamada PSTN. O Skype for Business Mobile escalona a chamada para outro usuário ou contato.  <br/> |A chamada é roteada via VoIP se o usuário ou contato for local para a etapa de gateway PSTN.  <br/> Se o usuário ou contato estiver remoto da etapa de gateway PSTN, a chamada será roteada via CvW.  <br/> Se o usuário de destino não estiver acessível por meio da PSTN, a chamada falhará.  <br/> Se o contato de destino for um Atendedor Automático (CAA), a chamada será bloqueada.  <br/> |
|Skype for Business Mobile  <br/> |Cliente skype for Business ou usuário federado  <br/> |Um Skype for Business Mobile inicia uma chamada de voz para outro cliente do Skype for Business ou usuário federado.  <br/> |A chamada é concluída por meio de VoIP.  <br/> |
|Skype for Business Mobile  <br/> |Cliente skype for Business ou usuário federado  <br/> | Um cliente do Skype for Business ou usuário federado inicia uma chamada de voz para um usuário de roteamento do Skype for Business Mobile Location-Based Roteamento. <br/> |A chamada é concluída por meio de VoIP.  <br/> |
|Skype for Business Mobile  <br/> |Cliente skype for Business ou usuário federado  <br/> |Um cliente do Skype for Business ou um usuário federado está em uma chamada VoIP para um usuário do Skype for Business Mobile. Uma das partes é escalonada para um usuário adicional do Skype for Business ou Federado.  <br/> |A chamada é concluída por meio de VoIP.  <br/> |
|Skype for Business Mobile  <br/> |Usuário federado  <br/> |Um Usuário Federado está em chamada de voz para um usuário de roteamento do Skype for Business Mobile Location-Based Roteamento; uma parte do Skype for Business Mobile é escalonada para um usuário PSTN.  <br/> |A chamada está bloqueada.  <br/> |
|Skype for Business Mobile  <br/> |Usuário federado  <br/> |Um usuário federado está em uma chamada VoIP para um usuário de roteamento de Location-Based Skype for Business Mobile; qualquer parte é escalada para um contato CAA.  <br/> |A chamada escalonada é bloqueada, com uma mensagem de erro apropriada.  <br/> |
|Skype for Business Mobile  <br/> |Usuário federado  <br/> |Um usuário federado está em uma chamada VoIP para um usuário de roteamento do Skype for Business Mobile Location-Based e o usuário federado é escalado para um usuário PSTN.  <br/> |A escalonamento será permitida ou não permitida com base no Location-Based roteamento do usuário federado. O aplicativo do usuário de roteamento do Skype for Business Mobile Location-Based não toma nenhuma ação.  <br/> |

### <a name="delegation"></a>Delegação

Os recursos de delegação no Skype for Business são afetados pelo Location-Based roteamento da seguinte maneira:

- Quando um representante habilitado para Location-Based Roteamento faz uma chamada em nome de um gerente, a política de voz do representante é usada para autorizar a chamada e a política de roteamento de voz do site do representante será usada para rotear a chamada

- Para chamadas PSTN de entrada para um gerente, as mesmas regras aplicáveis para encaminhamento de chamadas ou toque simultâneo serão aplicadas conforme descrito nos tópicos Transferências e encaminhamento de chamadas e toque simultâneo.

- Quando um representante define um ponto de extremidade PSTN como um destino de anel simultâneo, para uma chamada de entrada para o gerente, a política de roteamento de voz do site associado ao tronco de entrada será usada para rotear a chamada para o ponto de extremidade PSTN do representante.

- Para delegação, é recomendável que o gerente e seus representantes associados sejam geralmente localizados no mesmo site de rede.

## <a name="other-planning-considerations"></a>Outras considerações de planejamento

Ao planejar Location-Based roteamento, considere o impacto para os seguintes cenários.

### <a name="disaster-recovery"></a>Recuperação de Desastres

Durante um failover do pool principal para um pool de backup, bem como ao restaurar operações normais para o pool principal, o roteamento de Location-Based permanece imposto sempre durante um procedimento de desastre e recuperação.

### <a name="survivable-branch-appliance"></a>Aplicativo de Filial Persistente

A configuração Location-Based roteamento afeta o planejamento de onde você implanta os gateways associados aos seus Aparelhos de Filial Desaviváveis. O gateway associado ao seu SBA deve estar localizado no mesmo site de rede que seu Aparelho de Filial Desavivável; caso contrário, os usuários que estão em casa em seu Aparelho de Filial Desavivável não terão permissão para fazer chamadas de saída se Location-Based roteamento estiver configurado. Quando a conexão WAN entre seu Aparelho de Filial E o site central estiver inativa, Location-Based restrições de roteamento permanecerão impostas.

## <a name="client-and-server-support-for-location-based-routing"></a>Suporte para cliente e servidor para roteamento Location-Based cliente

Location-Based Roteamento é imposto pelo Skype for Business Server. O Skype for Business Server pode identificar os sites de rede de onde os usuários estão se conectando dentro da rede corporativa. Como os usuários remotos estão fora da rede corporativa, sua localização é considerada desconhecida.

### <a name="server-support"></a>Suporte a servidor

Location-Based Routing exige que o Skype for Business Server ou o Lync Server 2013 CU1 seja implantado em todos os pools de Front-End e servidores Standard Edition em uma determinada topologia. Se essas versões do servidor não estão instaladas, as restrições de roteamento baseadas em localização não poderão ser totalmente impostas.

A tabela a seguir identifica a combinação de funções de servidor e versões com suporte para Location-Based Routing.

****

|**Versão do pool**|**Versão do Servidor de Mediação**|**Com suporte**|
|:-----|:-----|:-----|
|Atualização Cumulativa do Skype for Business Server ou Lync Server 2013 fevereiro de 2013  <br/> |Atualização Cumulativa do Skype for Business Server ou Lync Server 2013 fevereiro de 2013  <br/> |sim  <br/> |
|Atualização Cumulativa do Skype for Business Server ou Lync Server 2013 fevereiro de 2013  <br/> |Lync Server 2013  <br/> |não  <br/> |
|Atualização Cumulativa do Skype for Business Server ou Lync Server 2013 fevereiro de 2013  <br/> |Lync Server 2010  <br/> |não  <br/> |
|Atualização Cumulativa do Skype for Business Server ou Lync Server 2013 fevereiro de 2013  <br/> |Office Communications Server 2007 R2  <br/> |não  <br/> |
|Lync Server 2013  <br/> |qualquer  <br/> |não  <br/> |
|Lync Server 2010  <br/> |qualquer  <br/> |não  <br/> |
|Office Communications Server 2007 R2  <br/> |qualquer  <br/> |não  <br/> |

### <a name="client-support"></a>Suporte para Cliente

A tabela a seguir identifica os clientes com suporte Location-Based Routing.

****

|**Tipo de cliente**|**Com suporte**|**Detalhes**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |sim  <br/> ||
|Lync 2013  <br/> |sim  <br/> ||
|Lync 2010  <br/> |sim  <br/> ||
|Office Communicator 2007 R2  <br/> |não  <br/> ||
|Lync Phone Edition  <br/> |sim  <br/> ||
|Lync Attendant  <br/> |sim  <br/> ||
|Lync para Windows 8  <br/> |não  <br/> ||
|Lync Mobile 2013  <br/> |não  <br/> |O VoIP deve ser desabilitado para clientes do Lync Mobile 2013, se usado por usuários com o roteamento Location-Based habilitado.  <br/> |
|Lync Mobile 2010  <br/> |sim  <br/> ||

> [!NOTE]
> Para desabilitar o VoIP para clientes do Skype for Business, atribua uma política de mobilidade com a configuração, IP Audio/Video, desabilitada para todos os usuários habilitados para Location-Based Routing. Para obter mais detalhes sobre a política de mobilidade, consulte [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).

## <a name="capabilities-not-supported-by-location-based-routing"></a>Recursos não suportados pelo Location-Based Routing

Location-Based Routing não se aplica aos seguintes tipos de interações. Location-Based o roteamento não é imposto quando os pontos de extremidade do Skype for Business interagem com pontos de extremidade PSTN usando esses recursos.

- Discagem PSTN para conferências

- Chamadas PSTN de entrada e saída por meio do Grupo de Resposta

- Estacionamento de chamadas ou recuperação de chamadas PSTN por meio do Estacionamento de Chamadas

- Chamadas PSTN de entrada para o Serviço de Comunicado

- Chamadas PSTN de entrada recuperadas por meio de Recebimento de Chamadas de Grupo

Para impor Location-Based regras de roteamento aos tipos de interações na lista a seguir, você deve habilitar Location-Based Roteamento para Conferência:

- Discagem PSTN de conferências

- Escalonamentos de conversas de áudio ponto a ponto para conferência envolvendo pontos de extremidade PSTN

- Transferências consultivas envolvendo pontos de extremidade PSTN

Para habilitar Location-Based roteamento para conferência, consulte [Roteamento](/previous-versions/office/lync-server-2013/lync-server-2013-location-based-routing-for-conferencing)baseado em local para conferência.