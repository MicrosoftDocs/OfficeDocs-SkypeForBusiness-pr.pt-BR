---
title: Planejar o roteamento Location-Based no Skype for Business
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
description: Planejamento de roteamento baseado em local no Skype for Business Server Enterprise Voice, incluindo interação com toque simultâneo e delegação e cenários com suporte para roteamento baseado em local.
ms.openlocfilehash: 473ed77dce8edaee3b43822adcb8920027795d9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825551"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Planejar o roteamento Location-Based no Skype for Business

Planejamento de roteamento baseado em local no Skype for Business Server Enterprise Voice, incluindo interação com toque simultâneo e delegação e cenários com suporte para roteamento baseado em local.

Location-Based roteamento possibilita restringir o roteamento de chamadas entre pontos de extremidade VoIP e pontos de extremidade PSTN com base no local das partes na chamada. Location-Based roteamento é um recurso de gerenciamento de chamadas que controla como as chamadas são roteadas pelo Skype for Business Server. Ele impõe regras de autorização de chamada sobre se as chamadas podem ser roteados para pontos de extremidade PBX ou PSTN com base na localização geográfica do chamador do Skype for Business.

Location-Based Roteamento apresenta um novo conjunto de regras que modifica o roteamento de chamadas PSTN nacionais e internacionais para evitar o desvio de chamada tarifada. Location-Based roteamento fornece a flexibilidade para definir o escopo dessas regras para regiões específicas, gateways específicos ou apenas para um conjunto específico de usuários.

Os cenários a seguir ilustram os principais tipos de restrições Location-Based o Roteamento pode impor:

- Chamadas de saída - o Roteamento de Location-Based pode impor chamadas de saída para saída para um gateway PSTN localizado na mesma região em que o chamador deve impedir o desvio de chamada tarifada PSTN, o que impede chamadas para sair de um gateway PSTN localizado em uma região diferente do chamador.

- Chamadas de entrada - o roteamento de Location-Based pode impedir que as chamadas PSTN de entrada torçam os pontos de extremidade do Skype for Business se o gateway PSTN que encaminha a chamada de entrada não estiver localizado na mesma região que o usuário chamado Skype for Business.

- Regiões desconhecidas - o Roteamento Location-Based restringe as chamadas PSTN de entrada e saída de e para usuários localizados em locais indeterminados (ou seja, usuários remotos que se conectam da Internet ou estão localizados em regiões desconhecidas).

- Regiões internacionais - Location-Based roteamento impõe o roteamento de chamadas de saída através de gateways PSTN internacionais se não for possível encontrar um gateway local para o local do usuário.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>Diretrizes para onde aplicar o roteamento Location-Based local

Location-Based roteamento dependendo da situação pode ser aplicado no local de rede do ponto de extremidade do usuário ou no local de rede do gateway PSTN. Este tópico fornece orientações sobre como o roteamento Location-Based é aplicado.

### <a name="applying-location-based-routing-at-the-users-location"></a>Aplicando Location-Based roteamento no local do usuário

Location-Based Routing utiliza as mesmas regiões de rede, sites e sub-redes conforme definido no Skype for Business Server usado pelo E9-1-1, CAC e Bypass de Mídia para aplicar restrições de roteamento de chamada para evitar bypass de chamada tarifada PSTN. A localização de um usuário é determinada pela sub-rede IP dos pontos de extremidade do Skype for Business do usuário que estão conectados. Cada sub-rede IP é associada a um site de rede, que é agregado em regiões de rede definidas pelo administrador. Location-Based roteamento é imposto com base no local de rede do usuário.

Location-Based Regras de roteamento são aplicadas por local de rede, o que significa que um determinado conjunto de regras será aplicado a todos os pontos de extremidade habilitados para o Roteamento Location-Based localizados no mesmo local de rede. Os administradores podem aplicar Location-Based Roteamento a sites de rede que o exigem.

As políticas de roteamento de voz podem ser definidas por local de rede para definir um gateway PSTN específico que deve ser usado por todos os usuários localizados no local de rede para chamar números de telefone PSTN. Essas políticas de roteamento de voz terão precedência sobre o roteamento definido pela política de voz do usuário quando o usuário estiver localizado em um local de rede habilitado para Roteamento Location-Based e impedirá o roteamento de chamadas por meio de outros gateways PSTN habilitados para o Roteamento Location-Based. Quando um usuário do Skype for Business faz uma chamada PSTN, a política de voz do usuário determina se o usuário pode ser autorizado a fazer a chamada. Se a política de voz do usuário permitir que o usuário estrute a chamada, o roteamento de Location-Based determinará de qual gateway PSTN a chamada deve egressar. Location-Based roteamento faz essa determinação com base na localização do usuário.

Um local de usuário pode ser categorizado das seguintes maneiras:

- O usuário está localizado em um local de rede conhecido habilitado para o Roteamento Location-Based e seu número DID (Direct Inward Dial) termina em um gateway PSTN colocado no mesmo local de rede (ou seja, escritório). O roteamento de chamadas de saída será por meio da política de roteamento de voz do local de rede no qual o usuário está localizado. As chamadas PSTN de entrada para o usuário são roteados para pontos de extremidade localizados no mesmo local de rede que o gateway PSTN.

- O usuário está localizado em um local de rede conhecido que está em um local diferente do local de rede onde o gateway PSTN está localizado. (ou seja, o usuário percorreu outro escritório corporativo). O roteamento de chamadas de saída será usando a política de roteamento de voz do local de rede no qual o usuário está localizado. As chamadas PSTN de entrada para o usuário não serão roteados para pontos de extremidade localizados em locais diferentes do gateway PSTN para impedir o desvio de chamada tarifada PSTN.

- Quando um usuário está localizado em um local de rede desconhecido para a implantação do Skype for Business Server, o roteamento de chamadas de saída será baseado na política de voz atribuída ao usuário para gateways PSTN não vinculados a restrições de Roteamento Location-Based. As chamadas PSTN de entrada não serão roteados para pontos de extremidade localizados em locais de rede desconhecidos para impedir o desvio de chamada tarifada PSTN.

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Aplicando Location-Based roteamento no local do gateway PSTN

As chamadas roteados por meio de gateways PSTN e PBXs podem exigir Location-Based de roteamento de acordo com a localização desses sistemas. Location-Based roteamento pode ser habilitado na granularidade por tronco.

Location-Based Roteamento apresenta o seguinte conjunto de regras quando habilitado em um tronco:

- Quando Location-Based roteamento é habilitado por tronco, as regras definidas nesse tronco serão aplicadas somente às chamadas roteados por esse tronco.

- Para evitar o bypass de chamadas tarifadas PSTN de onde as chamadas se originam de um local de rede diferente do local de rede onde o gateway PSTN está localizado, o Roteamento Location-Based introduz a associação de um local de rede a um determinado tronco. Isso define o local de rede que permite que as chamadas sejam roteados para um determinado tronco.

Os troncos podem ser habilitados para Location-Based roteamento de duas maneiras:

- O tronco é definido para um gateway PSTN que egresse chamadas para a PSTN. As chamadas de entrada roteadas por um tronco desse tipo serão roteadas somente para pontos de extremidade localizados no mesmo local de rede do tronco.

- O tronco é definido para um par de Servidor de Mediação que não egressa chamadas para a PSTN e serviços a usuários com telefones herdado em locais estáticos (ou seja, telefones PBX). Para essa configuração específica, todas as chamadas de entrada roteadas por um tronco desse tipo serão consideradas originadas do mesmo local de rede do tronco. As chamadas de usuários de PBX terão a mesma imposição de roteamento Location-Based que os usuários do Skype for Business localizados no mesmo local de rede do tronco. Se dois sistemas PBX localizados em locais de rede separados são conectados por meio do Skype for Business Server, o Roteamento Location-Based permitirá o roteamento de um ponto de extremidade PBX em um local de rede para outro ponto de extremidade PBX no outro local de rede. Este cenário não será bloqueado pelo Roteamento Location-Based. Além desse cenário e de forma semelhante a um usuário do Skype for Business no mesmo local, os pontos de extremidade conectados a um par do Servidor de Mediação com essa configuração poderão fazer ou receber chamadas de e para outro par do Servidor de Mediação que não encaminham chamadas para o PSTN (ou seja, um ponto de extremidade conectado a um PBX diferente) independentemente do local de rede ao qual o par do Servidor de Mediação está associado. Todas as chamadas de entrada, chamadas de saída, transferências de chamadas e encaminhamentos de chamadas envolvendo pontos de extremidade PSTN estarão sujeitas ao Roteamento Baseado em Local para usar apenas gateways PSTN definidos como locais para esse par de Servidor de Mediação.

## <a name="scenarios-for-location-based-routing"></a>Cenários de roteamento Location-Based local

Location-Based roteamento aplica as seguintes regras gerais ao rotear chamadas nos cenários a seguir.

### <a name="outgoing-calls"></a>Chamadas de saída

O roteamento de chamadas de saída de usuários habilitados para Location-Based roteamento é afetado pelo local de rede do ponto de extremidade do usuário. A tabela a seguir ilustra como o roteamento Location-Based afeta o roteamento de chamadas de saída, dependendo do local do ponto de extremidade do chamador.

**Chamador fazendo uma chamada de saída para a PSTN**

||**Ponto de extremidade do usuário localizado em um local de rede habilitado para roteamento Location-Based usuário**|**Ponto de extremidade do usuário localizado em um local de rede desconhecido ou não habilitado para roteamento Location-Based usuário**|
|:-----|:-----|:-----|
|Autorização de chamadas de saída  <br/> |A chamada é autorizada com base na política de voz do usuário  <br/> |A chamada é autorizada com base na política de voz do usuário  <br/> |
|Roteamento de chamada de saída  <br/> |A chamada é roteada de acordo com a política de roteamento de voz do local de rede  <br/> |A chamada é roteada de acordo com a política de voz do usuário e somente por troncos não habilitados para o Roteamento Location-Based (se disponível)  <br/> |

### <a name="incoming-calls"></a>Chamadas de entrada

O roteamento de chamadas de entrada para usuários habilitados para Location-Based roteamento depende do local do ponto de extremidade do usuário. O roteamento de chamadas de entrada é afetado da seguinte maneira. Se um usuário tiver uma chamada de entrada para um ponto de extremidade localizado em um local de rede habilitado para Roteamento Location-Based e o ponto de extremidade estiver localizado no mesmo local de rede que o gateway PSTN, a chamada será roteada. Se um usuário tiver uma chamada de entrada para um ponto de extremidade localizado em um local de rede habilitado para Roteamento Location-Based e o ponto de extremidade estiver localizado em um local de rede diferente do gateway PSTN, a chamada não será roteada. Quando um usuário não tiver pontos de extremidade localizados no mesmo local de rede do gateway PSTN de onde a chamada de entrada se origina, a chamada de entrada será roteada diretamente para a caixa postal do usuário e uma notificação de chamada perdida será enviada para a parte chamada.

As configurações de encaminhamento de chamadas de um usuário que está habilitado para o Roteamento do Location-Based continuarão a ser impostas, no entanto, as chamadas encaminhadas estarão sujeitas às restrições de roteamento Location-Based do usuário.

A tabela a seguir ilustra como Location-Based roteamento afeta o roteamento de chamadas de entrada, dependendo do local do ponto de extremidade do chamador. O local de rede do gateway PSTN está habilitado para o Roteamento Location-Based, e o Roteamento Location-Based só permite o roteamento de chamadas PSTN para pontos de extremidade dentro do mesmo local de rede.

**Receptor de chamada recebendo uma chamada de entrada da PSTN**

||**Ponto de extremidade do destinatário da chamada localizado no mesmo local de rede que o gateway PSTN**|**O ponto de extremidade do destinatário da chamada não está localizado no mesmo local de rede que o gateway PSTN**|**Ponto de extremidade do destinatário da chamada localizado em um local de rede desconhecido ou não habilitado para roteamento Location-Based usuário**|
|:-----|:-----|:-----|:-----|
|Roteamento de chamada PSTN de entrada  <br/> |A chamada de entrada é roteada para os pontos de extremidade do destinatário da chamada  <br/> |A chamada de entrada não é roteada para os pontos de extremidade do destinatário da chamada  <br/> |A chamada de entrada não é roteada para os pontos de extremidade do destinatário da chamada  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>Transferências de chamada e encaminhamento de chamada

Quando um ponto de extremidade PSTN está envolvido, o Roteamento do Location-Based analisa o local do ponto de extremidade do chamador e o ponto de extremidade para o qual a chamada será transferida ou encaminhada (ou seja, destino de transferência/encaminhamento). Location-Based roteamento determina se a chamada deve ser transferida ou encaminhada dependendo do local dos dois pontos de extremidade.

A tabela a seguir ilustra o cenário de um usuário do Skype for Business em uma chamada com um ponto de extremidade PSTN, e o usuário do Skype for Business transfere a chamada para outro usuário do Skype for Business. Dependendo do local do local de rede do ponto de extremidade do destinatário da transferência, o roteamento Location-Based afeta o roteamento da transferência ou encaminhamento de chamadas.

**Iniciando a transferência ou encaminhamento de chamada**

|**Usuário iniciando a transferência/encaminhamento de chamada**|**O ponto de extremidade de destino está no mesmo local de rede que o usuário que inicia a transferência ou encaminhamento de chamada**|**O ponto de extremidade de destino está em um local de rede diferente do usuário que inicia a transferência ou encaminhamento de chamada**|**O ponto de extremidade de destino está em um local de rede desconhecido ou em um local de rede não habilitado para roteamento Location-Based local**|
|:-----|:-----|:-----|:-----|
|Usuário do Skype for Business  <br/> |O encaminhamento de chamada ou transferência é permitido  <br/> |O encaminhamento ou a transferência de chamada não é permitido  <br/> |O encaminhamento ou a transferência de chamada não é permitido  <br/> |

Por exemplo: um usuário do Skype for Business em uma chamada com um ponto de extremidade PSTN transfere a chamada para outro usuário do Skype for Business que está no mesmo local de rede. Nesse caso, a transferência de chamada é permitida.

A tabela a seguir ilustra o cenário de um usuário do Skype for Business em uma chamada com outro usuário do Skype for Business, e um dos usuários transfere a chamada para um ponto de extremidade PSTN. Dependendo do local do usuário para o qual a chamada está sendo transferida, a tabela detalha como o roteamento Location-Based afeta a chamada.

**Transferência ou encaminhamento de chamada para o ponto de extremidade PSTN**

|**Destino do ponto de extremidade de transferência/encaminhamento de chamada**|**Usuários do Skype for Business no mesmo local de rede**|**Usuários do Skype for Business em diferentes locais de rede**|**Um ou ambos os usuários do Skype for Business em um local de rede ou local de rede desconhecido não habilitado para o Roteamento Location-Based Local**|
|:-----|:-----|:-----|:-----|
|Ponto de extremidade PSTN  <br/> |Encaminhamento de chamadas ou transferência permitido pela política de roteamento de voz do site do usuário transferido  <br/> |Encaminhamento de chamadas ou transferência permitido pela política de roteamento de voz do site do usuário transferido  <br/> |Encaminhamento de chamadas ou transferência permitido pela política de voz do usuário transferido somente através de troncos não habilitados para roteamento Location-Based dados  <br/> |

Por exemplo: um usuário do Skype for Business em uma chamada com outro usuário do Skype for Business que está no mesmo local de rede transfere a chamada para um ponto de extremidade PSTN e a transferência de chamada é permitida.

### <a name="simultaneous-ringing"></a>Toque simultâneo

Quando a parte chamada tem o toque simultâneo habilitado, o Roteamento Location-Based analisa o local do chamador e os pontos de extremidade das partes chamadas para determinar se a chamada deve ser encaminhada.

A tabela a seguir ilustra um usuário configurado com toque simultâneo, e o destino do toque simultâneo é um usuário no mesmo local de rede, em um local de rede diferente ou em um local de rede desconhecido.

****

|**Chamada PSTN de entrada para**|**Localizado no mesmo local de rede que o destinatário da chamada**|**Localizado em um local de rede diferente do destinatário da chamada**|**Localizado em um local de rede desconhecido ou não habilitado para roteamento Location-Based local**|
|:-----|:-----|:-----|:-----|
|Usuário do Skype for Business  <br/> |Toque simultâneo permitido  <br/> |Toque simultâneo não permitido  <br/> |Toque simultâneo não permitido  <br/> |

A tabela a seguir ilustra uma chamada de um usuário do Skype for Business (ou seja, chamador do Skype for Business) no mesmo local de rede, em um local de rede diferente ou em um local de rede desconhecido. O chamado tem um ponto de extremidade PSTN (ou seja, telefone celular) configurado como um destino de toque simultâneo. Neste cenário, o roteamento Location-Based determinará se a chamada deve ser roteada para o destino de toque simultâneo (ou seja, telefone celular) do chamador ou não.

****

|**Destino de toque simultâneo**|**Localizado no mesmo local de rede que o destinatário da chamada**|**Localizado em um local de rede diferente do destinatário da chamada**|**Localizado em um local de rede desconhecido ou não habilitado para roteamento Location-Based local**|
|:-----|:-----|:-----|:-----|
|Ponto de extremidade PSTN  <br/> |Toque simultâneo permitido por meio da política de roteamento de voz do site do chamador  <br/> |Toque simultâneo permitido por meio da política de roteamento de voz do site do chamador  <br/> |Toque simultâneo permitido através da política de voz do chamador para troncos não habilitados para roteamento Location-Based  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Atualização cumulativa 4 do Skype for Business

Com a Atualização Cumulativa 4, você verá o seguinte:

- Location-Based roteamento continuará sendo habilitado por meio da Política de Voz, incluindo clientes do Skype for Business Mobile.

- O comportamento de chamadas para clientes Skype for Business Mobile será baseado em se eles estão habilitados para o Roteamento Location-Based e o cliente que está se comunicando. Isso foi projetado para ser estático, mas pode haver, em determinadas situações, um esforço para associar um cliente Skype for Business Mobile a um gateway PSTN local e permitir determinados comportamentos, como um escalonamento

- Independentemente do sistema operacional, o cliente Skype for Business Mobile deve ter a mesma funcionalidade.

A tabela a seguir o acompanhará em alguns dos cenários de Atualização Pós-Cumulativa 4:

|**Usuário de roteamento baseado em local**|**Outra parte**|**Ação**|**Resultado**|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |O Skype for Business Mobile recebe uma chamada PSTN de entrada.  <br/> |A chamada é roteada via CvW (Chamada via Trabalho) e não por VoIP.  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |O Skype for Business Mobile faz uma chamada PSTN de saída.  <br/> |A chamada é roteada por CvW, e não por VoIP.  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |O Skype for Business Mobile está em uma chamada PSTN. O Skype for Business Mobile escalona a chamada para outro usuário ou contato.  <br/> |A chamada é roteada via VoIP se o usuário ou contato for local para o trecho do gateway PSTN.  <br/> Se o usuário ou contato estiver remoto do trecho de gateway PSTN, a chamada será roteada via CvW.  <br/> Se o usuário de destino não estiver acessível por meio da PSTN, a chamada falhará.  <br/> Se o contato de destino for um CaA (Atendente Automático de Conferência), a chamada será bloqueada.  <br/> |
|Skype for Business Mobile  <br/> |Cliente do Skype for Business ou usuário federado  <br/> |Um Skype for Business Mobile inicia uma chamada de voz para outro cliente do Skype for Business ou usuário federado.  <br/> |A chamada é concluída via VoIP.  <br/> |
|Skype for Business Mobile  <br/> |Cliente do Skype for Business ou usuário federado  <br/> | Um cliente do Skype for Business ou usuário federado inicia uma chamada de voz para um usuário de Roteamento de Location-Based Skype for Business Mobile. <br/> |A chamada é concluída via VoIP.  <br/> |
|Skype for Business Mobile  <br/> |Cliente do Skype for Business ou usuário federado  <br/> |Um cliente do Skype for Business ou um usuário federado está em uma chamada VoIP para um usuário do Skype for Business Mobile. Qualquer uma das partes escalona para um usuário adicional do Skype for Business ou Federado.  <br/> |A chamada é concluída via VoIP.  <br/> |
|Skype for Business Mobile  <br/> |Usuário federado  <br/> |Um Usuário Federado está em chamada de voz para um usuário de Roteamento de Location-Based Skype for Business Mobile; uma parte do Skype for Business Mobile escalona para um usuário PSTN.  <br/> |A chamada está bloqueada.  <br/> |
|Skype for Business Mobile  <br/> |Usuário federado  <br/> |Um usuário federado está em uma chamada VoIP para um usuário de Roteamento de Location-Based Skype for Business Mobile; qualquer uma das partes escalona para um contato CAA.  <br/> |A chamada escalonada é bloqueada, com uma mensagem de erro apropriada.  <br/> |
|Skype for Business Mobile  <br/> |Usuário federado  <br/> |Um usuário federado está em uma chamada VoIP para um usuário de Roteamento de Location-Based do Skype for Business Mobile e o usuário federado escalona para um usuário PSTN.  <br/> |O escalonamento será permitido ou não com base no roteamento Location-Based do usuário federado. O aplicativo do usuário de roteamento Location-Based Skype for Business Mobile não toma nenhuma ação.  <br/> |

### <a name="delegation"></a>Delegação

Os recursos de delegação no Skype for Business são afetados pelo Location-Based roteamento da seguinte maneira:

- Quando um representante habilitado para o roteamento de Location-Based faz uma chamada em nome de um gerente, a política de voz do representante é usada para autorizar a chamada e a política de roteamento de voz do local do representante será usada para rotear a chamada

- Para chamadas PSTN de entrada para um gerente, as mesmas regras aplicáveis para encaminhamento de chamadas ou toque simultâneo serão aplicadas conforme descrito nos tópicos Transferências e encaminhamento de chamadas e toque simultâneo.

- Quando um representante define um ponto de extremidade PSTN como um destino de toque simultâneo, para uma chamada de entrada para o gerente, a política de roteamento de voz do local associado ao tronco de entrada será usada para rotear a chamada para o ponto de extremidade PSTN do representante.

- Para delegação, é recomendável que o gerente e seus representantes associados normalmente estão localizados no mesmo local de rede.

## <a name="other-planning-considerations"></a>Outras considerações de planejamento

Ao planejar Location-Based Roteamento, você deve considerar o impacto nos cenários a seguir.

### <a name="disaster-recovery"></a>Recuperação de Desastres

Durante um failover do pool primário para um pool de backup, bem como ao restaurar operações normais para o pool primário, o Roteamento Location-Based permanece sempre aplicado durante um procedimento de recuperação e desastre.

### <a name="survivable-branch-appliance"></a>Aplicativo de Filial Persistente

A configuração Location-Based roteamento afeta o planejamento de onde você implanta os gateways associados aos Seus Aparelhos de FilialVivíveis. O gateway associado ao SBA deve estar localizado no mesmo local de rede que seu Aparelho de Filial Survivível; Caso contrário, os usuários que estão em seu Aparelho de FilialVivível não poderão fazer chamadas de saída se o Roteamento Location-Based estiver configurado. Quando a conexão WAN entre seu Aparelho de Filial Survivable e o site central estiver inocável, as restrições Location-Based roteamento permanecerão impostas.

## <a name="client-and-server-support-for-location-based-routing"></a>Suporte a cliente e servidor para roteamento Location-Based cliente

Location-Based roteamento é imposto pelo Skype for Business Server. O Skype for Business Server pode identificar os sites de rede onde os usuários estão se conectando dentro da rede corporativa. Como os usuários remotos estão fora da rede corporativa, sua localização é considerada desconhecida.

### <a name="server-support"></a>Suporte a servidor

Location-Based Routing exige que o Skype for Business Server ou o Lync Server 2013 CU1 seja implantado em todos os pools de Front-End e servidores Standard Edition em uma determinada topologia. Se essas versões do servidor não estão instaladas, as restrições de Roteamento Baseado em Local não poderão ser totalmente impostas.

A tabela a seguir identifica a combinação de funções de servidor e versões com suporte para o Roteamento Location-Based Local.

****

|**Versão do pool**|**Versão do Servidor de Mediação**|**Com suporte**|
|:-----|:-----|:-----|
|Atualização cumulativa de fevereiro de 2013 do Skype for Business Server ou Lync Server 2013  <br/> |Atualização cumulativa de fevereiro de 2013 do Skype for Business Server ou Lync Server 2013  <br/> |sim  <br/> |
|Atualização cumulativa de fevereiro de 2013 do Skype for Business Server ou Lync Server 2013  <br/> |Lync Server 2013  <br/> |não  <br/> |
|Atualização cumulativa de fevereiro de 2013 do Skype for Business Server ou Lync Server 2013  <br/> |Lync Server 2010  <br/> |não  <br/> |
|Atualização cumulativa de fevereiro de 2013 do Skype for Business Server ou Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |não  <br/> |
|Lync Server 2013  <br/> |qualquer  <br/> |não  <br/> |
|Lync Server 2010  <br/> |qualquer  <br/> |não  <br/> |
|Office Communications Server 2007 R2  <br/> |qualquer  <br/> |não  <br/> |

### <a name="client-support"></a>Suporte ao Cliente

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
|Lync Mobile 2013  <br/> |não  <br/> |O VoIP deve ser desabilitado para clientes do Lync Mobile 2013 se usado por usuários com o Roteamento Location-Based habilitado.  <br/> |
|Lync Mobile 2010  <br/> |sim  <br/> ||

> [!NOTE]
> Para desabilitar o VoIP para clientes do Skype for Business, atribua uma política de mobilidade com a configuração Áudio/Vídeo IP, desabilitada para todos os usuários habilitados para o Roteamento Location-Based. Para obter mais detalhes sobre a política de mobilidade, [consulte New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).

## <a name="capabilities-not-supported-by-location-based-routing"></a>Recursos não suportados pelo roteamento Location-Based gerenciamento

Location-Based roteamento não se aplica aos seguintes tipos de interações. Location-Based roteamento não é imposto quando os pontos de extremidade do Skype for Business interagem com pontos de extremidade PSTN usando esses recursos.

- Discagem PSTN para conferências

- Chamadas PSTN de entrada e saída por meio do Grupo de Resposta

- Estacionamento de chamada ou recuperação de chamadas PSTN por meio do Estacionamento de Chamadas

- Chamadas PSTN de entrada para o Serviço de Comunicado

- Chamadas PSTN de entrada recuperadas por meio do Recebimento de Chamadas em Grupo

Para impor Location-Based roteamento para os tipos de interações na lista a seguir, você deve habilitar Location-Based roteamento para conferência:

- Discagem PSTN de conferências

- Escalonamentos de conversas de áudio ponto a ponto para conferências envolvendo pontos de extremidade PSTN

- Transferências consultivas envolvendo pontos de extremidade PSTN

Para habilitar Location-Based roteamento para conferência, consulte [Roteamento baseado](https://technet.microsoft.com/library/e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3.aspx)em local para conferência.


