---
title: Planejar o roteamento baseado em localização no Skype for Business
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
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: Planejando o roteamento baseado em localização no Skype for Business Server Enterprise Voice, incluindo a interação com toque e delegação simultâneas, e cenários com suporte para roteamento baseado em local.
ms.openlocfilehash: 8c6ce8467c48231ebcab706874e70341ba431fd8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276744"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Planejar o roteamento baseado em localização no Skype for Business

Planejando o roteamento baseado em localização no Skype for Business Server Enterprise Voice, incluindo a interação com toque e delegação simultâneas, e cenários com suporte para roteamento baseado em local.

O roteamento baseado em local torna possível restringir o roteamento de chamadas entre pontos de extremidade VoIP e pontos de extremidade PSTN com base no local das partes na chamada. O roteamento baseado em local é um recurso de gerenciamento de chamadas que controla como as chamadas são roteadas pelo Skype for Business Server. Ele impõe regras de autorização de chamadas se as chamadas podem ser roteadas para os pontos de extremidade PBX ou PSTN com base na localização geográfica do chamador do Skype for Business.

O roteamento baseado na localização introduz um novo conjunto de regras que modifica o roteamento de chamadas PSTN nacionais e internacionais para evitar desvio de tarifas. O roteamento baseado na localização oferece a flexibilidade para abranger essas regras em regiões específicas, gateways específicos ou somente conjunto de usuários específico.

Os cenários a seguir ilustram os principais tipos de restrições de roteamento baseado em local que podem ser forçadas:

- Chamadas de egresso-o roteamento baseado em localização pode impor chamadas feitas para egresso a um gateway PSTN localizado na mesma região onde o chamador é para impedir que o desvio da PSTN seja ignorado, o que impede chamadas para egresso em um gateway PSTN localizado em uma região diferente como chamador.

- Chamadas de ingresso-o roteamento baseado na localização pode evitar chamadas PSTN de entrada para tocar pontos de extremidade do Skype for Business se o gateway PSTN que faz a chamada de entrada não estiver localizado na mesma região que o usuário do Skype for Business chamado.

- Regiões desconhecidas-o roteamento baseado em localização restringe as chamadas PSTN de entrada e saída para e de usuários localizados em locais indeterminados (ou seja, usuários remotos que se conectam pela Internet ou localizados em regiões desconhecidas).

- Regiões internacionais – o roteamento baseado em localização impõe o roteamento de chamadas feitas por meio de gateways PSTN internacionais se um gateway local para o local do usuário não puder ser encontrado.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>Orientação para onde aplicar o roteamento baseado em local

O roteamento baseado em local, dependendo da situação, pode ser aplicado ao local do site da rede de ponto de extremidade do usuário ou no local do site de rede do gateway PSTN. Este tópico fornece orientação sobre como o roteamento baseado em localização é aplicado.

### <a name="applying-location-based-routing-at-the-users-location"></a>Aplicando o roteamento baseado em localização na localização do usuário

O roteamento baseado em local aproveita as mesmas regiões de rede, sites e sub-redes, conforme definido no Skype for Business Server usado por E9-1-1, CAC e bypass de mídia para aplicar restrições de roteamento de chamadas para impedir o bypass de chamada PSTN. A localização de um usuário é determinada pela sub-rede IP do ponto de extremidade do Skype for Business (es) do usuário que está conectado. Cada sub-rede IP está associada a um local de rede que, por sua vez, está agregado a regiões de rede definidas pelo administrador. O roteamento baseado em local é aplicado com base no site de rede do usuário.

As regras de roteamento baseadas em local são aplicadas por site de rede, o que significa que um determinado conjunto de regras será aplicado a todos os pontos de extremidade habilitados para roteamento baseado em local localizado dentro do mesmo local de rede. Os administradores podem aplicar o Roteamento Baseado na Localização aos locais de rede que necessitarem dele.

As políticas de roteamento de voz podem ser definidas por local de rede a fim de determinar um gateway PSTN específico que deve ser usado por todos os usuários localizados no local de rede para chamar números de telefone PSTN. Essas políticas de roteamento de voz terão precedência sobre o roteamento definido pela política de voz do usuário quando o usuário estiver localizado em um site de rede habilitado para roteamento baseado em local, e ele impedirá o roteamento de chamadas por meio de outros gateways PSTN habilitados para Roteamento baseado em local. Quando um usuário do Skype for Business coloca uma chamada PSTN, a política de voz do usuário determina se o usuário pode ser autorizado a fazer a chamada. Se a política de voz do usuário permitir que o usuário faça a chamada, o roteamento baseado em local determinará de qual gateway PSTN a chamada deve fazer a saída. O roteamento baseado em local faz essa determinação com base na localização do usuário.

O local de um usuário pode ser categorizado das seguintes maneiras:

- O usuário está localizado em um site de rede conhecido habilitado para roteamento baseado em localização, e seu número DID (Direct Inward Dial) termina em um gateway PSTN colocado no mesmo local de rede (por exemplo, Office). O roteamento das chamadas de saída será feito pela política de roteamento de voz do local de rede em que o usuário está localizado. As chamadas PSTN de entrada para o usuário serão encaminhadas para pontos de extremidade localizados no mesmo local de rede do gateway PSTN.

- O usuário está em um local de rede conhecido que fica em um local de rede diferente do gateway PSTN (isto é, o usuário viajou para outro escritório da empresa). O roteamento das chamadas de saída será feito pela política de roteamento de voz do local de rede em que o usuário está localizado. As chamadas PSTN de entrada para o usuário não serão encaminhadas para pontos de extremidade localizados em locais diferentes do gateway PSTN a fim de impedir bypass das chamadas tarifadas PSTN.

- Quando um usuário está localizado em um site de rede desconhecido para a implantação do Skype for Business Server, o roteamento de chamadas de saída será baseado na política de voz atribuída ao usuário a gateways PSTN não ligados às restrições de roteamento baseadas em localização. As chamadas PSTN de entrada não serão encaminhadas para os pontos de extremidade localizados em locais de rede desconhecidos a fim de impedir bypass de chamadas tarifadas PSTN.

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Aplicando o roteamento baseado em local no local do gateway PSTN

Chamadas roteadas por meio de gateways PSTN e PBXs podem exigir restrições de roteamento baseado em localização, dependendo do local de tais sistemas. O roteamento baseado em localização pode ser habilitado na granularidade com base em cada tronco.

O roteamento baseado em local introduz o seguinte conjunto de regras quando habilitado em um tronco:

- Quando o roteamento baseado em localização estiver habilitado em uma base por tronco, as regras definidas nesse tronco serão aplicadas somente a chamadas roteadas por meio desse tronco.

- Para evitar que as tarifas PSTNs ignorem onde as chamadas são originadas de um site de rede diferente que o site de rede onde o gateway PSTN está localizado, o roteamento baseado em local introduz a associação de um site de rede a um determinado tronco. Isso definirá o local de rede que permite o encaminhamento de chamadas para um tronco específico.

Os troncos podem ser habilitados para roteamento baseado em local de duas maneiras:

- O tronco é definido para um gateway PSTN que egressa chamadas para a PSTN. As chamadas de entrada encaminhadas por um tronco desse tipo serão encaminhadas apenas para os pontos de extremidade localizados dentro do mesmo local de rede do tronco.

- O tronco é definido para um peer do servidor de mediação que não faz chamadas para os usuários de serviços PSTN e PSTN com telefones herdados em locais estáticos (por exemplo, telefones PBX). Para essa configuração específica, todas as chamadas de entrada encaminhadas por um tronco desse tipo serão consideradas como originadas do mesmo local de rede do tronco. As chamadas de usuários do PBX terão a mesma imposição de roteamento baseada em localização que os usuários do Skype for Business que estão localizados no mesmo site de rede que o tronco. Se dois sistemas PBX localizados em sites de rede separados estiverem conectados pelo Skype for Business Server, o roteamento baseado em local permitirá o roteamento de um ponto de extremidade de PBX em um site de rede para outro ponto de extremidade de PBX no outro site de rede. Esse cenário não será bloqueado pelo roteamento baseado em local. Além desse cenário e de maneira semelhante à de um usuário do Skype for Business no mesmo local, os pontos de extremidade conectados a um servidor de mediação de servidor com essa configuração poderão fazer ou receber chamadas para e de outros pontos do servidor de mediação que não roteiam chamadas t o PSTN (ou seja, um ponto de extremidade conectado a um PBX diferente) independentemente do site de rede ao qual o peer do servidor de mediação está associado. Todas as chamadas recebidas, chamadas de saída, transferências de chamadas e encaminhamentos de chamadas que envolvem pontos de extremidade PSTN estarão sujeitas ao roteamento baseado em localização para usar somente gateways PSTN definidos como locais para o peer do servidor de mediação.

## <a name="scenarios-for-location-based-routing"></a>Cenários do Roteamento Baseado na Localização

O Roteamento Baseado na Localização é aplicável às regras gerais a seguir durante o encaminhamento de chamadas nos seguintes cenários.

### <a name="outgoing-calls"></a>Chamadas de saída

O roteamento de chamadas de saída de usuários habilitados para roteamento baseado em local é afetado pelo local de rede do ponto de extremidade do usuário. A tabela a seguir ilustra como o roteamento baseado em localização afeta o roteamento de chamadas de saída, dependendo da localização do ponto de extremidade do chamador.

**Pessoa fazendo uma chamada de saída para o PSTN**

||**Ponto de extremidade do usuário localizado em um local de rede habilitado para o Roteamento com Base no Local**|**Ponto de extremidade do usuário localizado em um local de rede desconhecido ou não habilitado para o Roteamento com Base no Local**|
|:-----|:-----|:-----|
|Autorização de chamadas de saída  <br/> |A chamada está autorizada com base na política de voz do usuário  <br/> |A chamada está autorizada com base na política de voz do usuário  <br/> |
|Roteamento de chamada de saída  <br/> |A chamada é roteada de acordo com a política de roteamento de voz do site da rede  <br/> |A chamada é roteada de acordo com a política de voz do usuário e somente por troncos não habilitados para roteamento baseado em localização (se disponível)  <br/> |

### <a name="incoming-calls"></a>Chamadas de entrada

O roteamento de chamadas de entrada para usuários habilitados para roteamento baseado em locais depende do local do ponto de extremidade do usuário. Veja a seguir como o roteamento das chamadas de entrada é afetado. Se um usuário tiver uma chamada de entrada para um ponto de extremidade localizado em um site de rede habilitado para roteamento baseado em local, e o ponto de extremidade estiver localizado no mesmo site de rede que o gateway PSTN, a chamada será roteada. Se um usuário tiver uma chamada de entrada para um ponto de extremidade localizado em um site de rede habilitado para roteamento baseado em local, e o ponto de extremidade estiver localizado em um site de rede diferente do que o gateway PSTN, a chamada não será roteada. Quando um usuário não tem pontos de extremidade localizados no mesmo site de rede que o gateway PSTN em que a chamada de entrada é originada, a chamada de entrada será roteada diretamente para o correio de voz do usuário e uma notificação de chamada perdida será enviada para a parte chamada.

As configurações de encaminhamento de chamadas de um usuário habilitado para roteamento baseado em local continuarão a ser impostas, entretanto, as chamadas encaminhadas estarão sujeitas às restrições de roteamento baseadas em localização do usuário.

A tabela a seguir ilustra como o roteamento baseado em localização afeta o roteamento de chamadas recebidas dependendo da localização do ponto de extremidade do chamador. O site de rede do gateway PSTN está habilitado para roteamento baseado em localização, e o roteamento baseado em local permite o roteamento de chamadas PSTN para pontos de extremidade dentro do mesmo site de rede.

**O destinatário da chamada recebe uma chamada de entrada da PSTN**

||**Ponto de extremidade do chamador localizado no mesmo local de rede que o gateway PSTN**|**O ponto de extremidade do chamador não está localizado no mesmo local de rede que o gateway PSTN**|**Ponto de extremidade do chamador localizado no site desconhecido de rede ou não habilitado para roteamento baseado em local**|
|:-----|:-----|:-----|:-----|
|Roteamento da chamada PSTN recebida  <br/> |A chamada de entrada é roteada para pontos de extremidade do chamador  <br/> |A chamada de entrada não é roteada para pontos de extremidade do chamador  <br/> |A chamada de entrada não é roteada para pontos de extremidade do chamador  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>Transferência e encaminhamento de chamadas

Quando um ponto de extremidade PSTN está envolvido, o roteamento baseado em localização analisa o local do ponto de extremidade do Calle e o ponto de extremidade onde a chamada será transferida ou encaminhada (ou seja, transferência/destino para encaminhamento). O roteamento baseado em local determina se a chamada deve ser transferida ou encaminhada, dependendo da localização dos dois pontos de extremidade.

A tabela a seguir ilustra o cenário de um usuário do Skype for Business em uma chamada com um ponto de extremidade PSTN, e o usuário do Skype for Business transfere a chamada para outro usuário do Skype for Business. Dependendo do local do site de rede do ponto de extremidade do transportador, o roteamento baseado em local afeta o roteamento da transferência ou encaminhamento de chamadas.

**Iniciando a transferência ou o encaminhamento de chamada**

|**Usuário que inicia a transferência/encaminhamento da chamada**|**O ponto de extremidade de destino está no mesmo local de rede do usuário que inicia a transferência ou o encaminhamento da chamada**|**O ponto de extremidade de destino está em um local de rede diferente do que o do usuário que inicia a transferência ou o encaminhamento da chamada**|**O ponto de extremidade de destino está em um site de rede desconhecido ou site de rede não habilitado para roteamento baseado em local**|
|:-----|:-----|:-----|:-----|
|Usuário do Skype for Business  <br/> |Encaminhamento ou transferência de chamada permitido  <br/> |Encaminhamento ou transferência de chamada não permitido  <br/> |Encaminhamento ou transferência de chamada não permitido  <br/> |

Por exemplo: um usuário do Skype for Business em uma chamada com um ponto de extremidade PSTN transfere a chamada para outro usuário do Skype for Business que esteja no mesmo local de rede. Nesse caso, a transferência de chamada é permitida.

A tabela a seguir ilustra o cenário de um usuário do Skype for Business em uma chamada com outro usuário do Skype for Business e um dos usuários transfere a chamada para um ponto de extremidade PSTN. Dependendo do local do usuário para o qual a chamada está sendo transferida, a tabela detalhará como o Roteamento Baseado na Localização afeta a chamada.

**Transferência ou encaminhamento de chamada para um ponto de extremidade PSTN**

|**Destino do ponto de extremidade da transferência/encaminhamento de chamada**|**Usuários do Skype for Business no mesmo local de rede**|**Usuários do Skype for Business em diferentes sites de rede**|**Um ou ambos os usuários do Skype for Business em um site de rede desconhecido ou site de rede não estão habilitados para roteamento baseado em local**|
|:-----|:-----|:-----|:-----|
|Ponto de extremidade PSTN  <br/> |Encaminhamento de chamadas ou transferência permitida pela política de roteamento de voz do site do usuário transferido  <br/> |Encaminhamento de chamadas ou transferência permitida pela política de roteamento de voz do site do usuário transferido  <br/> |Encaminhamento de chamadas ou transferência permitida pela política de voz do usuário transferido somente por troncos não habilitados para roteamento baseado em local  <br/> |

Por exemplo: um usuário do Skype for Business em uma chamada com outro usuário do Skype for Business que esteja no mesmo local de rede transfere a chamada para um ponto de extremidade PSTN e a transferência de chamadas é permitida.

### <a name="simultaneous-ringing"></a>Toque simultâneo

Quando a parte chamada tem o toque simultâneo habilitado, o roteamento baseado em local analisa o local da parte de chamada e os pontos de extremidade das partes chamadas para determinar se a chamada deve ser roteada.

A tabela a seguir ilustra um usuário configurado com toque simultâneo, e o destino do toque simultâneo é um usuário no mesmo local de rede, em um local de rede diferente ou em um local de rede desconhecido.

****

|**Chamadas de entrada do PSTN para**|**Localizado no mesmo local de rede do destinatário da chamada**|**Localizado em um local de rede diferente do chamador**|**Localizado no site desconhecido de rede ou não habilitado para roteamento baseado em local**|
|:-----|:-----|:-----|:-----|
|Usuário do Skype for Business  <br/> |Toque simultâneo permitido  <br/> |Toque simultâneo não permitido  <br/> |Toque simultâneo não permitido  <br/> |

A tabela a seguir ilustra uma chamada de um usuário do Skype for Business (por exemplo, Skype for Business Caller) no mesmo site de rede, em um site de rede diferente ou em um site de rede desconhecido. O destinatário da chamada tem um ponto de extremidade PSTN (ou seja, um telefone celular) configurado como um destino de toque simultâneo. Nesse cenário, o roteamento baseado em localização determinará se a chamada deve ser roteada para o destino de toque simultâneo (isto é, o celular) do receptor ou não.

****

|**Destino de toque simultâneo**|**Localizado no mesmo local de rede do destinatário da chamada**|**Localizado em um local de rede diferente do chamador**|**Localizado no site desconhecido de rede ou não habilitado para roteamento baseado em local**|
|:-----|:-----|:-----|:-----|
|Ponto de extremidade PSTN  <br/> |Toque simultâneo permitido por meio da política de roteamento de voz do site do chamador  <br/> |Toque simultâneo permitido por meio da política de roteamento de voz do site do chamador  <br/> |O toque simultâneo é permitido pela política de voz do chamador para troncos não habilitados para roteamento baseado em local  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Atualização Cumulativa 4 do Skype for Business

Com a Atualização Cumulativa 4, você verá o seguinte:

- O roteamento baseado em local continuará a ser habilitado por meio da política de voz, incluindo clientes móveis do Skype for Business.

- O comportamento de chamadas para clientes móveis do Skype for Business será baseado se eles estiverem habilitados para roteamento baseado no local e o cliente de comunicação. Isso foi projetado para ser estático, mas, em certas situações, pode haver um esforço para associar um cliente Skype for Business Mobile a um gateway PSTN local e permitir determinados comportamentos, como um escalonamento.

- Qualquer que seja o seu sistema operacional, o cliente Skype for Business Mobile deverá ter a mesma funcionalidade.

A tabela a seguir explica alguns dos cenários após a Atualização Cumulativa 4:

|**Usuário de roteamento baseado em local**|**Outros**|**Ação**|**Resultado**|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |O Skype for Business Mobile recebe uma chamada PSTN de entrada.  <br/> |A chamada é roteada através de CvW (Telefonar via Trabalho), e não de VoIP.  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |O Skype for Business Mobile faz uma chamada PSTN de saída.  <br/> |A chamada é roteada através de CvW, e não de VoIP.  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |O Skype for Business Mobile está em uma chamada PSTN. O Skype for Business Mobile então encaminha a chamada para outro usuário ou contato.  <br/> |A chamada é roteada através de VoIP quando o usuário ou o contato é local para o trecho de gateway PSTN.  <br/> Quando o usuário ou o contato está longe do trecho de gateway PSTN, a chamada é roteada por CvW.  <br/> Se o usuário de origem não estiver acessível através de PSTN, a chamada falhará.  <br/> Se o contato de origem for um CAA (Atendedor Automático de Conferência), a chamada será bloqueada.  <br/> |
|Skype for Business Mobile  <br/> |Cliente Skype for Business ou usuário federado  <br/> |Um Skype for Business Mobile inicia uma chamada de voz para outro cliente Skype for Business ou usuário federado.  <br/> |A chamada é concluída através de VoIP.  <br/> |
|Skype for Business Mobile  <br/> |Cliente Skype for Business ou usuário federado  <br/> | Um cliente Skype for Business ou um usuário federado inicia uma chamada de voz para um usuário de roteamento baseado em local móvel do Skype for Business. <br/> |A chamada é concluída através de VoIP.  <br/> |
|Skype for Business Mobile  <br/> |Cliente Skype for Business ou usuário federado  <br/> |Um cliente Skype for Business ou um usuário federado está em uma chamada VoIP para um usuário móvel do Skype for Business. Qualquer uma das partes é escalonada para outro usuário federado ou Skype for Business.  <br/> |A chamada é concluída através de VoIP.  <br/> |
|Skype for Business Mobile  <br/> |Usuário federado  <br/> |Um usuário federado está em uma chamada de voz para um usuário de roteamento baseado em localização do Skype for Business Mobile; um participante do Skype for Business Mobile é encaminhado para um usuário PSTN.  <br/> |A chamada é bloqueada.  <br/> |
|Skype for Business Mobile  <br/> |Usuário federado  <br/> |Um usuário federado está em uma chamada de VoIP para um usuário de roteamento baseado em localização do Skype for Business Mobile; qualquer uma das partes é escalonada para um contato do CAA.  <br/> |A chamada escalonada é bloqueada com uma mensagem de erro apropriada.  <br/> |
|Skype for Business Mobile  <br/> |Usuário federado  <br/> |Um usuário federado está em uma chamada de VoIP para um usuário de roteamento baseado em local do Skype for Business Mobile, e o usuário federado se Escalona para um usuário PSTN.  <br/> |O escalonamento será permitido ou impossibilitado com base no roteamento baseado em localização do usuário federado. O aplicativo do usuário de roteamento baseado em local móvel do Skype for Business não executará nenhuma ação.  <br/> |

### <a name="delegation"></a>Delegação

Os recursos de delegação do Skype for Business são afetados pelo roteamento baseado em local da seguinte maneira:

- Quando um representante habilitado para roteamento baseado em localização colocar uma chamada em nome de um gerente, a política de voz do representante será usada para autorizar a chamada e a política de roteamento de voz do site do representante será usada para direcionar a chamada

- Para as chamadas de entrada PSTN para um gerente, as mesmas regras aplicáveis ao encaminhamento de chamadas ou ao toque simultâneo serão aplicadas conforme descrito nos tópicos Transferências e encaminhamento de chamadas e Toque Simultâneo.

- Quando um representante define um ponto de extremidade PSTN como um destino de toque simultâneo, para uma chamada recebida para o gerente, a política de roteamento de voz do site que está associado ao tronco de entrada será usada para direcionar a chamada para o ponto de extremidade PSTN do representante.

- Para delegação, é recomendável que o Gerenciador e seus representantes associados estejam geralmente localizados no mesmo site de rede.

## <a name="other-planning-considerations"></a>Outras considerações de planejamento

Ao planejar o roteamento baseado em localização, considere o impacto para os cenários a seguir.

### <a name="disaster-recovery"></a>Recuperação de desastres

Durante um failover do pool primário para um pool de backup, bem como ao restaurar operações normais para o pool primário, o roteamento baseado em local permanecerá em vigor a qualquer momento durante um desastre e procedimento de recuperação.

### <a name="survivable-branch-appliance"></a>Aparelho de Filial Persistente

Configurar o roteamento baseado em local impacta o planejamento de onde você implanta os gateways associados a seus aparelhos de ramificação sobreviventes. O gateway associado a seu SBA deve estar localizado no mesmo site de rede que o seu aparelho de ramificação sobreviventes; caso contrário, os usuários hospedados em seu aparelho de ramificação sobreviventes não terão permissão para fazer chamadas de saída se o roteamento baseado em localização estiver configurado. Quando a conexão WAN entre seu aparelho de ramificação sobreviventes e o site central está inativa, as restrições de roteamento baseadas em local permanecem impostas.

## <a name="client-and-server-support-for-location-based-routing"></a>Suporte a cliente e servidor para Roteamento Baseado em Local

O roteamento baseado em local é imposto pelo Skype for Business Server. O Skype for Business Server pode identificar os sites de rede dos quais os usuários estão se conectando dentro da rede corporativa. Como os usuários remotos estão fora da rede corporativa, seu local é considerado desconhecido.

### <a name="server-support"></a>Suporte a servidor

O roteamento baseado em localização requer que o Skype for Business Server ou o Lync Server 2013 CU1 seja implantado em todos os pools de front-end e servidores Standard Edition em uma determinada topologia. Se essas versões do servidor não estiverem instaladas, as restrições de roteamento baseadas em local não poderão ser totalmente impostas.

A tabela a seguir identifica a combinação de funções de servidor e versões com suporte para roteamento baseado em local.

****

|**Versão do pool**|**Versão do Servidor de Mediação**|**Compatível**|
|:-----|:-----|:-----|
|Skype for Business Server ou Lync Server 2013 atualização cumulativa de fevereiro de 2013  <br/> |Skype for Business Server ou Lync Server 2013 atualização cumulativa de fevereiro de 2013  <br/> |sim  <br/> |
|Skype for Business Server ou Lync Server 2013 atualização cumulativa de fevereiro de 2013  <br/> |Lync Server 2013  <br/> |não  <br/> |
|Skype for Business Server ou Lync Server 2013 atualização cumulativa de fevereiro de 2013  <br/> |Lync Server 2010  <br/> |não  <br/> |
|Skype for Business Server ou Lync Server 2013 atualização cumulativa de fevereiro de 2013  <br/> |Office Communications Server 2007 R2  <br/> |não  <br/> |
|Lync Server 2013  <br/> |qualquer um  <br/> |não  <br/> |
|Lync Server 2010  <br/> |qualquer um  <br/> |não  <br/> |
|Office Communications Server 2007 R2  <br/> |qualquer um  <br/> |não  <br/> |

### <a name="client-support"></a>Suporte de Cliente

A tabela a seguir identifica os clientes com suporte para o roteamento baseado em localização.

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
|Lync móvel 2013  <br/> |não  <br/> |O VoIP deve ser desabilitado para os clientes do Lync Mobile 2013 se usado por usuários com roteamento baseado em local habilitado.  <br/> |
|Lync móvel 2010  <br/> |sim  <br/> ||

> [!NOTE]
> Para desabilitar o VoIP para clientes do Skype for Business, atribua uma política de mobilidade com a configuração, áudio/vídeo IP, desabilitada para todos os usuários habilitados para roteamento baseado em local. Para obter mais detalhes sobre política de mobilidade, consulte [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).

## <a name="capabilities-not-supported-by-location-based-routing"></a>Recursos não suportados pelo Roteamento Baseado em Local

O roteamento baseado em localização não se aplica aos seguintes tipos de interações. O roteamento baseado em local não é imposto quando os pontos de extremidade do Skype for Business interagem com pontos de extremidade PSTN usando esses recursos.

- Discagem PSTN para conferências

- Chamadas PSTN de entrada e saída por meio do grupo de resposta

- Estacionamento de chamada ou recuperação de chamadas PSTN por meio do estacionamento de chamada

- Chamadas PSTN de entrada para o serviço de anúncio

- Chamadas PSTN de entrada recuperadas por meio do recebimento de chamada de grupo

Para impor regras de roteamento baseado em localização aos tipos de interações na lista a seguir, você deve habilitar o roteamento baseado em local para a conferência:

- Discagem de saída PSTN de conferências

- Escalonamentos de conversas de áudio ponto a ponto para conferências envolvendo pontos de extremidade PSTN

- Transferências consultivas envolvendo pontos de extremidade PSTN

Para habilitar o roteamento baseado em local para a conferência, consulte [roteamento baseado em local para conferência](https://technet.microsoft.com/library/e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3.aspx).


