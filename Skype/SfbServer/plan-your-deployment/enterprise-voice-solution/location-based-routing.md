---
title: Plano para roteamento baseado em local no Skype para negócios
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: Planejando o roteamento baseado em local no Skype para Business Server Enterprise Voice, incluindo a interação com a delegação e toque simultâneo e os cenários com suporte para roteamento baseado no local.
ms.openlocfilehash: 63b4cbd347bd7151fed36eb3f837ec9b611e2d9c
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250515"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Plano para roteamento baseado em local no Skype para negócios

Planejando o roteamento baseado em local no Skype para Business Server Enterprise Voice, incluindo a interação com a delegação e toque simultâneo e os cenários com suporte para roteamento baseado no local.

Roteamento baseado em local torna possível restringir o roteamento de chamadas entre os pontos de extremidade de VoIP e pontos de extremidade PSTN com base na localização dos participantes na chamada. Roteamento baseado no local é um recurso de gerenciamento de chamada que controla como as chamadas são roteadas pelo Skype para Business Server. Ele aplica regras de autorização de chamada em se as chamadas possam ser roteadas para os pontos de extremidade de PBX ou PSTN com base no Skype para a localização geográfica do chamador de negócios.

O roteamento baseado na localização introduz um novo conjunto de regras que modifica o roteamento de chamadas PSTN nacionais e internacionais para evitar desvio de tarifas. O roteamento baseado na localização oferece a flexibilidade para abranger essas regras em regiões específicas, gateways específicos ou somente conjunto de usuários específico.

Os cenários a seguir ilustram os principais tipos de restrições de que roteamento baseado no local pode impor:

- Chamadas de saída - roteamento baseado no local pode impor chamadas de saída para a saída para um gateway PSTN que está localizado na mesma região como onde o chamador é para impedir que o desvio de tarifas PSTN, que impede chamadas de saída para um gateway PSTN localizado em uma região diferente, como o chamador.

- Chamadas de ingresso - roteamento baseado no local pode impedir que as chamadas PSTN de entrada toquem Skype para pontos de extremidade de negócios se o gateway PSTN roteando a chamada de entrada não estiver localizado na mesma região como o Skype chamado para o usuário de negócios.

- Regiões desconhecidos - roteamento baseado em local restringe chamadas PSTN recebidas e enviadas de e para usuários que estão localizados em indeterminado locais (isto é, remotos usuários se conectando pela Internet ou localizados em regiões desconhecidos).

- Regiões internacionais - roteamento baseado em local impõe o roteamento de chamadas por meio de gateways PSTN internacionais de saída, se não for encontrado um gateway local para o local do usuário.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>Diretrizes para onde aplicar roteamento baseado no local

Roteamento baseado no local, dependendo da situação pode ser aplicado no local de site de rede de ponto de extremidade do usuário ou no local de site de rede do gateway PSTN. Este tópico fornece orientação sobre como baseados em local de roteamento é aplicada.

### <a name="applying-location-based-routing-at-the-users-location"></a>A aplicação de roteamento baseados em local no local do usuário

Local-Based Routing aproveita os mesmos regiões de rede, sites e sub-redes, conforme definido na Skype para Business Server usado pelo E9-1-1, CAC e Bypass de mídia para aplicar as restrições de roteamento de chamada para evitar tarifas PSTN desvio. Localização de um usuário é determinada pela sub-rede do IP do Skype do usuário para negócios endpoint(s) estiver conectado a partir. Cada sub-rede IP está associada a um local de rede que, por sua vez, está agregado a regiões de rede definidas pelo administrador. Roteamento baseado no local é imposto com base no site de rede do usuário.

Regras de roteamento baseados em local são aplicadas em um por cada site de rede, que significa que um determinado conjunto de regras será aplicado a todos os pontos de extremidade habilitados para roteamento baseado no local que estão localizados dentro do mesmo site de rede. Os administradores podem aplicar o Roteamento Baseado na Localização aos locais de rede que necessitarem dele.

As políticas de roteamento de voz podem ser definidas por local de rede a fim de determinar um gateway PSTN específico que deve ser usado por todos os usuários localizados no local de rede para chamar números de telefone PSTN. Essas políticas de roteamento de voz terá precedência sobre o roteamento definido pela política de voz do usuário quando o usuário está localizado em um site de rede habilitado para roteamento baseado em local, e isso impedirá o roteamento de chamadas por meio de outros gateways PSTN que estão habilitados para Roteamento baseado em local. Quando um Skype para comercial do usuário faz uma chamada PSTN, a política de voz do usuário determina se o usuário pode ser autorizado a fazer a chamada. Se a política de voz do usuário permite que o usuário fazer a chamada, roteamento baseado em local determina qual gateway PSTN a chamada deve saída de. Roteamento baseado em local torna essa determinação com base no local do usuário.

O local de um usuário pode ser categorizado das seguintes maneiras:

- O usuário está localizado em um site de rede conhecido habilitado para roteamento baseado no local e seu número DID (Direct Inward Dial) termina em um gateway PSTN colocado no mesmo site de rede (isto é, office). O roteamento das chamadas de saída será feito pela política de roteamento de voz do local de rede em que o usuário está localizado. As chamadas PSTN de entrada para o usuário serão encaminhadas para pontos de extremidade localizados no mesmo local de rede do gateway PSTN.

- O usuário está em um local de rede conhecido que fica em um local de rede diferente do gateway PSTN (isto é, o usuário viajou para outro escritório da empresa). O roteamento das chamadas de saída será feito pela política de roteamento de voz do local de rede em que o usuário está localizado. As chamadas PSTN de entrada para o usuário não serão encaminhadas para pontos de extremidade localizados em locais diferentes do gateway PSTN a fim de impedir bypass das chamadas tarifadas PSTN.

- Quando um usuário está localizado em um site de rede for desconhecido para o Skype para implantação de servidor de negócios, o roteamento de chamadas de saída se baseará a política de voz atribuída ao usuário para os gateways PSTN não acoplado a restrições de roteamento baseados em local. As chamadas PSTN de entrada não serão encaminhadas para os pontos de extremidade localizados em locais de rede desconhecidos a fim de impedir bypass de chamadas tarifadas PSTN.

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>A aplicação de roteamento baseados em local no local do gateway PSTN

As chamadas são roteadas por meio de gateways PSTN e PBXs podem exigir a restrições de roteamento baseados em local dependendo do local do tais sistemas. Roteamento baseado no local pode ser habilitado na granularidade em uma base por tronco.

Roteamento baseado em local introduz o seguinte conjunto de regras, quando habilitada em um tronco:

- Quando roteamento baseado no local está habilitado em uma base por tronco, as regras definem em que tronco será aplicado somente para as chamadas roteadas por esse tronco.

- Para impedir que o desvio de tarifas PSTN, onde as chamadas são provenientes de um site de rede diferente que o site de rede onde se encontra o gateway PSTN, roteamento baseado em local apresenta a associação de um site de rede para um determinado tronco. Isso definirá o local de rede que permite o encaminhamento de chamadas para um tronco específico.

Troncos podem ser habilitados para roteamento baseado no local de duas maneiras:

- O tronco é definido para um gateway PSTN que egressa chamadas para a PSTN. As chamadas de entrada encaminhadas por um tronco desse tipo serão encaminhadas apenas para os pontos de extremidade localizados dentro do mesmo local de rede do tronco.

- O tronco é definido para um par de servidor de mediação que não saída chamadas para os usuários PSTN e serviços com os telefones herdados em um estático locais (isto é, telefones PBX). Para essa configuração específica, todas as chamadas de entrada encaminhadas por um tronco desse tipo serão consideradas como originadas do mesmo local de rede do tronco. Chamadas de PBX usuários terão a mesma imposição de roteamento baseados em local como Skype para usuários corporativos localizados no mesmo site do tronco. Se os dois sistemas de PBX, localizados em sites de rede separado estão conectados por meio de Skype para Business Server, roteamento baseado em local permitirá que o roteamento de um ponto de extremidade de PBX em um site de rede para outro ponto de extremidade de PBX no site de rede. Esse cenário não será bloqueado pelo roteamento baseado no local. Além neste cenário e de maneira similar, como um Skype para usuário de negócios no mesmo local, pontos de extremidade conectados a um par de servidor de mediação com esta configuração poderão fazer ou receber chamadas de outro ponto do servidor de mediação que não encaminham chamadas t o PSTN (ou seja, um ponto de extremidade conectado a um PBX diferente) independentemente do site de rede à qual o ponto de servidor de mediação está associado. Todas as chamadas de entrada, chamadas de saída, transferências de chamada e chamada encaminhamentos envolvendo pontos de extremidade PSTN estará sujeito roteamento local para usar somente os gateways PSTN que são definidos como local para tal ponto do servidor de mediação.

## <a name="scenarios-for-location-based-routing"></a>Cenários do Roteamento Baseado na Localização

O Roteamento Baseado na Localização é aplicável às regras gerais a seguir durante o encaminhamento de chamadas nos seguintes cenários.

### <a name="outgoing-calls"></a>Chamadas de saída

O roteamento de chamadas de saída de usuários habilitados para roteamento baseado em local é afetado por local da rede do ponto de extremidade do usuário. A tabela a seguir ilustra como baseados em local roteamento afeta o roteamento de chamadas de saída dependendo do local do ponto de extremidade do chamador.

**Pessoa fazendo uma chamada de saída para o PSTN**

||**Ponto de extremidade do usuário localizado em um local de rede habilitado para o Roteamento com Base no Local**|**Ponto de extremidade do usuário localizado em um local de rede desconhecido ou não habilitado para o Roteamento com Base no Local**|
|:-----|:-----|:-----|
|Autorização de chamadas de saída  <br/> |Chamada será autorizada com base na política de voz do usuário  <br/> |Chamada será autorizada com base na política de voz do usuário  <br/> |
|Roteamento de chamada de saída  <br/> |Chamada é roteada de acordo com a política de roteamento de voz do site de rede  <br/> |Chamada será roteada de acordo com a política de voz do usuário e somente por meio de troncos não habilitados para roteamento baseado em local (se disponível)  <br/> |

### <a name="incoming-calls"></a>Chamadas de entrada

O roteamento de chamadas de entrada para usuários habilitados para roteamento baseado em local depende do local do ponto de extremidade do usuário. Veja a seguir como o roteamento das chamadas de entrada é afetado. Se um usuário tiver uma chamada recebida para um ponto de extremidade localizado em um roteamento baseados em local habilitado para o site de rede e o ponto de extremidade está localizado no mesmo site de rede como o gateway PSTN, a chamada será roteada. Se um usuário tiver uma chamada recebida para um ponto de extremidade localizado em um roteamento baseados em local habilitado para o site de rede e o ponto de extremidade está localizado em um site de rede diferente do que o gateway PSTN, a chamada não será roteada. Quando um usuário não tiver nenhum ponto de extremidade localizado no mesmo site de rede que o gateway PSTN onde a chamada de entrada se origina, a chamada de entrada será roteada diretamente para o correio de voz do usuário e uma notificação de chamada perdida será enviada para a parte chamada.

As configurações de um usuário que está habilitado para roteamento baseado no local de encaminhamento de chamadas continuarão a serem aplicadas, no entanto, o encaminhar chamadas estarão sujeitas restrições de roteamento baseados em local do usuário.

A tabela a seguir ilustra como baseados em local roteamento afeta o roteamento de chamadas de entrada dependendo do local do ponto de extremidade do receptor. O site de rede do gateway PSTN está habilitado para roteamento baseado no local e roteamento baseado em local só permite que o roteamento de chamadas do PSTN para os pontos de extremidade dentro do mesmo site de rede.

**O destinatário da chamada recebe uma chamada de entrada da PSTN**

||**Ponto de extremidade do receptor localizado no mesmo site do gateway PSTN**|**Ponto de extremidade do receptor não localizado no mesmo site do gateway PSTN**|**Ponto de extremidade do receptor localizados no site de rede desconhecido ou não habilitado para roteamento baseado no local**|
|:-----|:-----|:-----|:-----|
|Roteamento da chamada PSTN recebida  <br/> |Chamada de entrada é roteada para pontos de extremidade do receptor  <br/> |Chamada de entrada não é roteada para pontos de extremidade do receptor  <br/> |Chamada de entrada não é roteada para pontos de extremidade do receptor  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>Transferências e encaminhamento de chamadas

Quando um ponto de extremidade PSTN está envolvido, roteamento baseado em local analisa o local do ponto de extremidade do calle e o ponto de extremidade em que a chamada será transferida ou encaminhada para (ou seja, o destino de transferência/encaminhar). Roteamento baseado em local determina se a chamada deve ser transferida ou encaminhada dependendo do local de ambos os pontos de extremidade.

A tabela a seguir ilustra o cenário de um Skype para usuário de negócios em uma chamada com um ponto de extremidade PSTN, e o Skype para o usuário de negócios transferirá a chamada para outro Skype para o usuário de negócios. Dependendo do local de site de rede do ponto de extremidade do transferido, roteamento baseado em local afeta o roteamento da transferência de chamada ou encaminhar.

**Iniciando a transferência ou o encaminhamento de chamada**

|**Usuário que inicia a transferência/encaminhamento da chamada**|**O ponto de extremidade de destino está no mesmo local de rede do usuário que inicia a transferência ou o encaminhamento da chamada**|**O ponto de extremidade de destino está em um local de rede diferente do que o do usuário que inicia a transferência ou o encaminhamento da chamada**|**Ponto de extremidade de destino no site de rede desconhecido ou site de rede não está habilitado para roteamento baseado no local**|
|:-----|:-----|:-----|:-----|
|Skype para o usuário de negócios  <br/> |Encaminhamento ou transferência de chamada permitido  <br/> |Encaminhamento ou transferência de chamada não permitido  <br/> |Encaminhamento ou transferência de chamada não permitido  <br/> |

Por exemplo: um Skype para usuário de negócios em uma chamada com um ponto de extremidade PSTN transferirá a chamada para outro Skype para usuário Business que esteja no mesmo site de rede. Nesse caso, a transferência de chamada é permitida.

A tabela a seguir ilustra o cenário de um Skype para usuário de negócios em uma chamada com outra Skype para o usuário de negócios e um dos usuários transferirá a chamada para um ponto de extremidade PSTN. Dependendo do local do usuário para o qual a chamada está sendo transferida, a tabela detalhará como o Roteamento Baseado na Localização afeta a chamada.

**Transferência ou encaminhamento de chamada para um ponto de extremidade PSTN**

|**Destino do ponto de extremidade da transferência/encaminhamento de chamada**|**Skype para usuários comerciais no mesmo site de rede**|**Skype para usuários corporativos em sites de rede diferente**|**Um ou ambos Skype para usuários comerciais no site de rede desconhecido ou não habilitado para roteamento baseado no local de site de rede**|
|:-----|:-----|:-----|:-----|
|Ponto de extremidade PSTN  <br/> |Ligue para frente ou transferência permitido pela política do roteamento de voz do site do usuário transferido  <br/> |Ligue para frente ou transferência permitido pela política do roteamento de voz do site do usuário transferido  <br/> |Ligue para frente ou transferência permitida pela política de voz do usuário transferido somente por meio de troncos não habilitados para roteamento baseado no local  <br/> |

Por exemplo: um Skype para usuário de negócios em uma chamada com outra Skype para usuário Business que esteja no mesmo site de rede transfere a chamada para um ponto de extremidade PSTN e a transferência de chamada é permitida.

### <a name="simultaneous-ringing"></a>Toque simultâneo

Quando a parte chamada tiver habilitado o toque simultâneo, roteamento baseado em local analisa o local da parte chamada e os pontos de extremidade das partes chamados para determinar se a chamada deve ser roteada.

A tabela a seguir ilustra um usuário configurado com toque simultâneo, e o destino do toque simultâneo é um usuário no mesmo local de rede, em um local de rede diferente ou em um local de rede desconhecido.

****

|**Chamadas de entrada do PSTN para**|**Localizado no mesmo local de rede do destinatário da chamada**|**Localizado em um local de rede diferente do chamador**|**Localizados no site de rede desconhecido ou não habilitado para roteamento baseado no local**|
|:-----|:-----|:-----|:-----|
|Skype para o usuário de negócios  <br/> |Toque simultâneo permitido  <br/> |Toque simultâneo não permitido  <br/> |Toque simultâneo não permitido  <br/> |

A tabela a seguir ilustra uma chamada a partir de um Skype para o usuário de negócios (isto é, Skype para o chamador de negócios) no mesmo site de rede, em um site de rede diferente ou de um site de rede desconhecido. O destinatário da chamada tem um ponto de extremidade PSTN (ou seja, um telefone celular) configurado como um destino de toque simultâneo. Neste cenário, o roteamento baseado em local determinará se a chamada deve ser roteada para o destino de Toque simultâneo (isto é, telefone celular) do receptor ou não.

****

|**Destino de toque simultâneo**|**Localizado no mesmo local de rede do destinatário da chamada**|**Localizado em um local de rede diferente do chamador**|**Localizados no site de rede desconhecido ou não habilitado para roteamento baseado no local**|
|:-----|:-----|:-----|:-----|
|Ponto de extremidade PSTN  <br/> |Toque simultâneo permitido por meio da política do roteamento de voz do site do chamador  <br/> |Toque simultâneo permitido por meio da política do roteamento de voz do site do chamador  <br/> |Toque simultâneo permitido por meio da diretiva de voz do chamador para troncos não habilitados para roteamento baseado no local  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Atualização Cumulativa 4 do Skype for Business

Com a Atualização Cumulativa 4, você verá o seguinte:

- Roteamento baseado em local continuará a ser habilitado por meio da diretiva de voz, incluindo Skype para clientes móveis de negócios.

- O comportamento de chamada para Skype para clientes corporativos Mobile será baseado em se elas são habilitadas para roteamento baseado no local e o cliente estão se comunicando. Isso foi projetado para ser estático, mas, em certas situações, pode haver um esforço para associar um cliente Skype for Business Mobile a um gateway PSTN local e permitir determinados comportamentos, como um escalonamento.

- Qualquer que seja o seu sistema operacional, o cliente Skype for Business Mobile deverá ter a mesma funcionalidade.

A tabela a seguir explica alguns dos cenários após a Atualização Cumulativa 4:

|**Usuário de roteamento baseada no local**|**Outros**|**Ação**|**Resultado**|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype para negócios Mobile recebe uma chamada PSTN.  <br/> |A chamada é roteada através de CvW (Telefonar via Trabalho), e não de VoIP.  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype para negócios Mobile faz uma chamada de PSTN de saída.  <br/> |A chamada é roteada através de CvW, e não de VoIP.  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |O Skype for Business Mobile está em uma chamada PSTN. Skype para dispositivos móveis de negócios, em seguida, escalona a chamada para outro usuário ou contato.  <br/> |A chamada é roteada através de VoIP quando o usuário ou o contato é local para o trecho de gateway PSTN.  <br/> Quando o usuário ou o contato está longe do trecho de gateway PSTN, a chamada é roteada por CvW.  <br/> Se o usuário de origem não estiver acessível através de PSTN, a chamada falhará.  <br/> Se o contato de origem for um CAA (Atendedor Automático de Conferência), a chamada será bloqueada.  <br/> |
|Skype for Business Mobile  <br/> |Skype para o cliente de negócios ou usuário federado  <br/> |Um Skype para negócios Mobile inicia uma chamada de voz para outro Skype para o cliente de negócios ou usuário federado.  <br/> |A chamada é concluída através de VoIP.  <br/> |
|Skype for Business Mobile  <br/> |Skype para o cliente de negócios ou usuário federado  <br/> | Um Skype para o cliente de negócios ou usuário federado inicia uma chamada de voz para uma Skype para usuário Business Mobile Location-Based roteamento. <br/> |A chamada é concluída através de VoIP.  <br/> |
|Skype for Business Mobile  <br/> |Skype para o cliente de negócios ou usuário federado  <br/> |Um Skype para o cliente de negócios ou usuário federado é em uma chamada VoIP para um Skype para usuário móvel de negócios. Ambas as partes for escalonada para uma Skype adicional para usuário federado ou de negócios.  <br/> |A chamada é concluída através de VoIP.  <br/> |
|Skype for Business Mobile  <br/> |Usuário federado  <br/> |Um usuário federado estiver na chamada de voz para uma Skype para roteamento Business Mobile Location-Based usuário; um Skype para parte de negócios Mobile for escalonada para um usuário por PSTN.  <br/> |A chamada é bloqueada.  <br/> |
|Skype for Business Mobile  <br/> |Usuário federado  <br/> |Um usuário federado estiver em uma chamada VoIP para um Skype para roteamento Business Mobile Location-Based usuário; ambas as partes for escalonada para um contato CAA.  <br/> |A chamada escalonada é bloqueada com uma mensagem de erro apropriada.  <br/> |
|Skype for Business Mobile  <br/> |Usuário federado  <br/> |Um usuário federado é em uma chamada VoIP para um Skype para roteamento de Business Mobile Location-Based usuário e o usuário federado for escalonada para um usuário por PSTN.  <br/> |O escalonamento será permitido ou não permitido com base em que o serviço de roteamento baseados em local do usuário federado. O Skype para o aplicativo do usuário Business Mobile Location-Based roteamento não executar qualquer ação.  <br/> |

### <a name="delegation"></a>Delegação

Os recursos de delegação no Skype para negócios são afetados pela roteamento baseado em local da seguinte maneira:

- Quando um delegado habilitado para roteamento baseado em local casas uma chamada em nome de um gerente, a política de voz do representante é usada para autorizar a chamada e voz do site do representante política de roteamento será usada para rotear a chamada

- Para as chamadas de entrada PSTN para um gerente, as mesmas regras aplicáveis ao encaminhamento de chamadas ou ao toque simultâneo serão aplicadas conforme descrito nos tópicos Transferências e encaminhamento de chamadas e Toque Simultâneo.

- Quando um delegado define um ponto de extremidade PSTN como um destino de Toque simultâneo, para uma chamada de entrada para o gerente, a política de roteamento de voz do site que está associado ao tronco entrado será usada para rotear a chamada ao ponto de extremidade PSTN do representante.

- Para delegação, isso tem recomendável que o gerente e seus representantes associados para costuma estar localizado no mesmo site de rede.

## <a name="other-planning-considerations"></a>Outras considerações de planejamento

Ao planejar o roteamento baseado em local, você deve considerar o impacto para os cenários a seguir.

### <a name="disaster-recovery"></a>Recuperação de desastres

Durante um failover do pool primário para um pool de backup, bem como ao restaurar operações normais ao pool primário, roteamento baseado em local permanece imposto em todas as vezes durante um procedimento de recuperação de desastres.

### <a name="survivable-branch-appliance"></a>Aparelho de Filial Persistente

Configuração de roteamento baseados em local impacta o planejamento de onde você implanta os gateways associados ao seu aparelhos de filial persistente. O gateway associado ao seu SBA deve estar localizado no mesmo site do seu aparelho de filial persistente; Caso contrário, os usuários hospedados em seu aparelho de filial não terá permissão para fazer chamadas de saída, se o roteamento baseado em local estiver configurado. Quando a conexão WAN entre seu aparelho de filial e o site central é pressionada, restrições de roteamento baseados em local permanece imposta.

## <a name="client-and-server-support-for-location-based-routing"></a>Suporte a cliente e servidor para Roteamento Baseado em Local

Roteamento baseado no local é imposto pela Skype para Business Server. Skype para Business Server pode identificar os sites de rede onde os usuários estão se conectando de dentro da rede corporativa. Como os usuários remotos estão fora da rede corporativa, seu local é considerado desconhecido.

### <a name="server-support"></a>Suporte a servidor

Roteamento baseado em local requer que o Skype para Business Server ou o Lync Server 2013 CU1 é implantado em todos os pools de Front-End e servidores Standard Edition em uma determinada topologia. Se essas versões do servidor não estiverem instaladas, restrições de roteamento baseado no local não podem ser impostas totalmente.

A tabela a seguir identifica a combinação das funções de servidor e de versões que é suportada para roteamento baseado no local.

****

|**Versão do pool**|**Versão do Servidor de Mediação**|**Compatível**|
|:-----|:-----|:-----|
|Skype para atualização cumulativa Business Server ou o Lync Server 2013 de fevereiro de 2013  <br/> |Skype para atualização cumulativa Business Server ou o Lync Server 2013 de fevereiro de 2013  <br/> |sim  <br/> |
|Skype para atualização cumulativa Business Server ou o Lync Server 2013 de fevereiro de 2013  <br/> |Lync Server 2013  <br/> |não  <br/> |
|Skype para atualização cumulativa Business Server ou o Lync Server 2013 de fevereiro de 2013  <br/> |Lync Server 2010  <br/> |não  <br/> |
|Skype para atualização cumulativa Business Server ou o Lync Server 2013 de fevereiro de 2013  <br/> |Office Communications Server 2007 R2  <br/> |não  <br/> |
|Lync Server 2013  <br/> |qualquer um  <br/> |não  <br/> |
|Lync Server 2010  <br/> |qualquer um  <br/> |não  <br/> |
|Office Communications Server 2007 R2  <br/> |qualquer um  <br/> |não  <br/> |

### <a name="client-support"></a>Suporte de Cliente

A tabela a seguir identifica os clientes que suporta roteamento baseado no local.

****

|**Tipo de cliente**|**Compatível**|**Detalhes**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |sim  <br/> ||
|Lync 2013  <br/> |sim  <br/> ||
|Lync 2010  <br/> |sim  <br/> ||
|Office Communicator 2007 R2  <br/> |não  <br/> ||
|Lync Phone Edition  <br/> |sim  <br/> ||
|Lync Attendant  <br/> |sim  <br/> ||
|Lync para Windows 8  <br/> |não  <br/> ||
|Lync Mobile 2013  <br/> |não  <br/> |VoIP deve ser desabilitado para clientes do Lync Mobile 2013 se utilizado por usuários com o roteamento baseados em local habilitado.  <br/> |
|O Lync Mobile 2010  <br/> |sim  <br/> ||

> [!NOTE]
> Para desativar o VoIP para Skype para clientes corporativos, atribua uma política de mobilidade com a configuração, de áudio/vídeo IP desabilitada para todos os usuários habilitados para roteamento baseado no local. Para obter mais detalhes sobre a política de mobilidade, consulte [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).

## <a name="capabilities-not-supported-by-location-based-routing"></a>Recursos não suportados pelo Roteamento Baseado em Local

Roteamento baseado no local não se aplica aos seguintes tipos de interações. Roteamento baseado no local não é imposto quando Skype para pontos de extremidade de negócios interagem com pontos de extremidade PSTN usando esses recursos.

- Discagem PSTN para conferências

- Chamadas PSTN de entrada e saída por meio do grupo de resposta

- Estacionamento de chamada ou recuperação de chamadas PSTN por meio do estacionamento de chamada

- Chamadas PSTN de entrada para o serviço de anúncio

- Chamadas PSTN de entrada recuperadas por meio do recebimento de chamada de grupo

Para impor regras de roteamento baseados em local aos tipos de interações na lista a seguir, você deve habilitar o roteamento baseado no local para a conferência:

- Discagem de saída PSTN de conferências

- Escalonamentos de conversas de áudio ponto a ponto para conferências envolvendo pontos de extremidade PSTN

- Transferências consultivas envolvendo pontos de extremidade PSTN

Para habilitar o roteamento baseado no local para conferência, consulte [roteamento baseado no local para a conferência](https://technet.microsoft.com/library/e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3.aspx).


