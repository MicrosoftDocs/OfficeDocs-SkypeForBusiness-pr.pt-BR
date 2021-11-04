---
title: Location-Based roteamento para conferência no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: Planejamento de roteamento baseado em local para conferência em Skype for Business Server Enterprise Voice, incluindo transferências de chamadas consultivas.
ms.openlocfilehash: 118ccd13fb85f9566c7b62736514936d4f41f9bd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768509"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Location-Based roteamento para conferência no Skype for Business Server

Planejamento de roteamento baseado em local para conferência em Skype for Business Server Enterprise Voice, incluindo transferências de chamadas consultivas.

Location-Based roteamento possibilita restringir o roteamento de chamadas entre pontos de extremidade VoIP e pontos de extremidade PSTN com base no local das partes na chamada. Location-Based roteamento para conferência permite impor Location-Based regras de roteamento em reuniões (ou seja, conferências) para impedir o desvio de tarifa de PSTN. O aplicativo monitora uma conferência ativa e impõe Location-Based de roteamento com base no local dos usuários participantes. O Location-Based de roteamento para conferência adicionalmente permite a imposição de restrições de roteamento Location-Based para transferências consultivas envolvendo pontos de extremidade PSTN.

O Location-Based de Conferência de Roteamento fornece Skype for Business conferências um mecanismo para a prevenção do desvio de tarifa de PSTN. O aplicativo monitora conferências ativas e impõe Location-Based restrições de roteamento com base no local dos usuários Skype for Business participantes.

O Location-Based de Conferência de Roteamento determina se Location-Based roteamento deve ser imposto em uma reunião Skype for Business se os seguintes critérios são atendidos:

- O organizador da reunião está habilitado para Location-Based Routing. Location-Based restrições de roteamento serão aplicadas somente a conferências organizadas por usuários habilitados para roteamento Location-Based.

- Pelo menos um participante da reunião é um ponto de extremidade PSTN. Location-Based restrições de roteamento são aplicáveis apenas para conferências que incluem pontos de extremidade PSTN.

- O site de rede no qual o gateway PSTN usado para fazer a ponte da conferência com a PSTN está localizado, bem como os sites de rede de onde os organizadores e participantes estão se conectando.

O Location-Based de roteamento para conferência impede a participação de usuários Skype for Business e pontos de extremidade PSTN de diferentes sites de rede para a mesma conferência. Se o organizador de uma reunião estiver habilitado para roteamento Location-Based, o aplicativo de Conferência imporá as seguintes restrições:

- Os pontos de extremidade que podem ingressar em uma reunião de Skype for Business dependem dos pontos de extremidade que já ingressaram na conferência, e essa restrição se ajusta à medida que os pontos de extremidade ingressam e novos pontos de extremidade ingressam na conferência. Se organizadores e participantes ingressarem em uma reunião de Skype for Business do mesmo site de rede, um ponto de extremidade PSTN, outro participante do mesmo site de rede, outro participante de um site de rede diferente ou um participante de um site de rede desconhecido podem ingressar.

- Se organizadores e participantes ingressarem na reunião de sites de rede diferentes ou desconhecidos, um ponto de extremidade PSTN não poderá ingressar na reunião se a chamada PSTN entrar em um tronco SIP habilitado para roteamento Location-Based.

- Se os organizadores e participantes ingressarem na reunião no mesmo site de rede e houver participantes participando da mesma reunião do PSTN, um ponto de extremidade Skype for Business de um site de rede diferente não poderá ingressar na reunião.

Essas restrições de Location-Based roteamento são resumidas na tabela a seguir.

|User(s) in a conference at any given point|Usuários permitidos a ingressar na conferência|Usuários não autorizados a ingressar na conferência|
|:-----|:-----|:-----|
|Skype for Business Usuários do cliente VoIP de um único site de rede  <br/> |Skype for Business Usuário cliente VoIP do mesmo site de rede  <br/> Skype for Business Usuário cliente VoIP de um site de rede diferente  <br/> Skype for Business Usuário cliente VoIP de um site de rede desconhecido  <br/> Usuário do Skype for Business VoIP federado  <br/> União do usuário a partir de um ponto de extremidade PSTN  <br/> |Nenhum  <br/> |
|Skype for Business Usuários do cliente VoIP de um site de rede desconhecido  <br/> |Skype for Business Usuário cliente VoIP de qualquer site  <br/> Skype for Business Usuário cliente VoIP de um site desconhecido  <br/> Usuário do Skype for Business VoIP federado  <br/> |União do usuário por meio de um ponto de extremidade PSTN  <br/> |
|Skype for Business Usuários cliente VoIP de diferentes sites de rede  <br/> |Skype for Business Usuário cliente VoIP de qualquer site de rede  <br/> Skype for Business Usuário cliente VoIP de um site de rede desconhecido  <br/> Usuário do Skype for Business VoIP federado  <br/> |União do usuário por meio de um ponto de extremidade PSTN  <br/> |
|Skype for Business Usuários do cliente VoIP de um único site de rede e usuários que ingressaram em um ponto de extremidade PSTN  <br/> |Skype for Business Usuário cliente VoIP do mesmo site de rede  <br/> |Skype for Business Usuário cliente VoIP de um site de rede diferente  <br/> Skype for Business Usuário cliente VoIP de um site de rede desconhecido  <br/> Usuário do Skype for Business VoIP federado  <br/> |

Veja a seguir características adicionais do aplicativo Location-Based Routing for Conferencing:

- Quando um usuário não tem permissão para ingressar em uma conferência com Location-Based restrições de roteamento, a chamada para a conferência será rejeitada e o cliente Skype for Business informará que a chamada não foi concluída ou encerrada.

- Um ponto de extremidade PSTN que ingressar em uma conferência com as imposições de roteamento do Location-Based não será restrito para ingressar na conferência, independentemente de seu estado, se o ponto de extremidade ingressar por meio de um tronco que não está habilitado para roteamento Location-Based.

- Um sistema PBX conectado a um Servidor de Mediação em um tronco SIP que não egressa chamadas para a PSTN terá as mesmas imposições que os usuários Skype for Business localizados no mesmo site de rede em que o tronco SIP é definido. Por exemplo, um ponto de extremidade PSTN poderá ingressar em uma conferência com um usuário PBX e um usuário Skype for Business se estiver localizado no mesmo site de rede; caso contrário, o ponto de extremidade PSTN não terá permissão para ingressar na conferência se o usuário PBX estiver em um site de rede diferente do Skype for Business usuário.

> [!NOTE]
> Com Skype for Business Atualização Cumulativa 4, o comportamento na tabela a seguir deve ser observado:

|User|Outra parte|Action|Resultado|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile está em uma chamada PSTN. Skype for Business Mobile, em seguida, escalona a chamada para uma conferência Atendedor Automático (CAA).  <br/> |A chamada é bloqueada, com uma mensagem de erro apropriada.  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business Cliente ou Usuário Federado  <br/> |O Usuário Cliente ou Federado está em uma chamada VoIP para um usuário de roteamento de Skype for Business móvel Location-Based e uma das partes é escalonada para uma CAA.  <br/> |A chamada de escalonamento é bloqueada, com uma mensagem de erro apropriada.  <br/> |

## <a name="consultative-call-transfers"></a>Transferências de chamada consultiva

Além de impor Location-Based roteamento para reuniões Skype for Business, o aplicativo roteamento para conferência Location-Based impõe restrições de roteamento Location-Based às transferências de chamada consultiva que são egressadas para pontos de extremidade PSTN. Uma transferência de chamada consultiva é uma chamada estabelecida entre duas partes em que uma das partes transfere a chamada para um novo usuário. Por exemplo, um ponto de extremidade PSTN chama o usuário A (Skype for Business chamador). O Usuário A determina que o usuário PSTN deve ser encaminhado para o usuário B (Skype for Business usuário). O Usuário A coloca a chamada com o usuário PSTN em espera e chama o usuário B. O usuário B concorda em falar com o usuário PSTN. O Usuário A transfere a chamada em espera para o usuário B.

**Fluxo de chamada de transferência de chamada consultiva**

![Roteamento baseado em local para diagrama de conferência.](../../media/LocationBasedRoutingForConferencing.jpg)

Quando um usuário habilitado para roteamento de Location-Based inicia uma transferência de chamada consultiva de um ponto de extremidade PSTN (conforme mostrado na figura anterior), isso cria duas chamadas ativas, uma chamada entre o usuário PSTN e o usuário A do Skype for Business e a outra entre o usuário A do Skype for Business e o usuário Skype for Business B. O comportamento a seguir é imposto por t ele Location-Based roteamento para aplicativo de conferência:

- Se o tronco SIP que roteia a chamada PSTN estiver autorizado a rotear a chamada PSTN para o Skype for Business site de rede onde o usuário B (ou seja, destino de transferência) está localizado, a transferência de chamada será permitida; caso contrário, a transferência de chamada consultiva será bloqueada. Essa autorização é executada com base no local da parte transferida que está no mesmo site de rede do tronco SIP que está roteando a chamada ativa para o ponto de extremidade PSTN.

- Se o tronco SIP que roteia a chamada PSTN de entrada não estiver autorizado a rotear chamadas para o site de rede onde a parte transferida (usuário B do Skype for Business) está localizada ou se a parte transferida estiver localizada em um site de rede desconhecido, a transferência de chamada consultiva para o ponto de extremidade PSTN (ou seja, destino de transferência de chamada) será bloqueada.

A tabela a seguir descreve como Location-Based restrições de roteamento são aplicadas pelo aplicativo de roteamento Location-Based para conferência para transferências de chamadas consultativas. Embora os pontos de extremidade PBX não sejam diretamente associados a um site de rede, o tronco SIP ao que o PBX está conectado pode ser atribuído a um site de rede. Portanto, o ponto de extremidade PBX pode ser indiretamente associado a um site de rede.


|Site de rede da parte transferida de chamada|Site de rede de destino de transferência de chamada|Comportamento|
|:-----|:-----|:-----|
|Ponto de extremidade PSTN  <br/> |Skype for Business usuário no mesmo site de rede (ou seja, site 1)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PSTN  <br/> |Skype for Business usuário em sites de rede diferentes (ou seja, site 2)  <br/> |A transferência consultiva não será permitido  <br/> |
|Ponto de extremidade PSTN  <br/> |Skype for Business usuário em um site de rede desconhecido  <br/> |A transferência consultiva não será permitido  <br/> |
|Ponto de extremidade PSTN  <br/> |Usuário Skype for Business federado  <br/> |A transferência consultiva não será permitido  <br/> |
|Ponto de extremidade PSTN  <br/> |Ponto de extremidade PBX no mesmo site (ou seja, site 1)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PSTN  <br/> |Ponto de extremidade PBX em sites diferentes (ou seja, site 2)  <br/> |A transferência consultiva não será permitido  <br/> |
|Ponto de extremidade PBX no mesmo site (ou seja, site 1)  <br/> |Ponto de extremidade PSTN  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PBX em um site diferente (ou seja, site 2)  <br/> |Ponto de extremidade PSTN  <br/> |A transferência consultiva não será permitido  <br/> |
|Ponto de extremidade PBX em qualquer site  <br/> |Skype for Business usuário no mesmo site de rede (ou seja, site 1)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PBX em qualquer site  <br/> |Skype for Business usuário em sites de rede diferentes (ou seja, site 2)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PBX em qualquer site  <br/> |Skype for Business usuário em um site de rede desconhecido  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PBX em qualquer site  <br/> |Usuário Skype for Business federado  <br/> |A transferência consultiva será permitida  <br/> |

## <a name="requirements"></a>Requisitos

O aplicativo roteamento de Location-Based para conferência exige que o Skype for Business Server ou a Atualização Cumulativa 2 do Lync Server 2013 seja implantado em todos os pools Front-End e servidores Edição Standard em sua topologia. Se essas versões do servidor não estão instaladas em alguns servidores em sua topologia Location-Based, as restrições de roteamento não poderão ser totalmente impostas em reuniões e transferências de chamadas consultivas.

A tabela a seguir identifica a combinação de funções de servidor e versões que suportam Location-Based Routing.


|Front-End pool|Versão do Servidor de Mediação|Com suporte|
|:-----|:-----|:-----|
|Skype for Business Server ou Lync Server 2013 Cumulative Update 2  <br/> |Skype for Business Server ou Lync Server 2013 Cumulative Update 2  <br/> |Sim  <br/> |
|Atualização Cumulativa 2 do Lync Server 2013  <br/> |Atualização Cumulativa 1 do Lync Server 2013  <br/> |Não  <br/> |
|Atualização Cumulativa 2 do Lync Server 2013  <br/> |Lync Server 2010  <br/> |Não  <br/> |
|Atualização Cumulativa 2 do Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |Não  <br/> |
|Atualização Cumulativa 1 do Lync Server 2013  <br/> |Qualquer  <br/> |Não  <br/> |
|Lync Server 2010  <br/> |Qualquer  <br/> |Não  <br/> |
|Office Communications Server 2007 R2  <br/> |Qualquer  <br/> |Não  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Configuração de Location-Based roteamento para conferência

O Location-Based de roteamento para conferência depende da configuração do Location-Based Routing. As principais configurações são as seguintes:

- O local de participação de participantes em uma reunião é determinado com base em seu site de rede. Um site de rede e suas sub-redes de rede associadas devem ser definidos Skype for Business Server para impor Location-Based Routing.

- Para impor Location-Based roteamento de reuniões, Skype for Business participantes devem estar habilitados para Location-Based Routing.

- Para impor Location-Based roteamento de pontos de extremidade PSTN que ingressarem em reuniões, o tronco SIP usado para conectar os pontos de extremidade PSTN deve ser configurado para roteamento Location-Based.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Habilitando o Location-Based roteamento para conferência

O Location-Based de roteamento para conferência está desabilitado por padrão. Antes de habilitar esse aplicativo, você precisa determinar a prioridade correta a ser atribuído ao aplicativo. Para determinar essa prioridade, execute o seguinte cmdlet Skype for Business Server Shell de Gerenciamento:

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

Neste cmdlet, é o pool no qual o Location-Based de roteamento para \<Pool FQDN\> conferência deve ser habilitado.

Este cmdlet retornará a lista dos aplicativos hospedados pelo Skype for Business Server e o valor de prioridade para cada um deles. O Location-Based de roteamento para conferência precisa ter um valor de prioridade maior do que o aplicativo "UdcAgent" e menor que os aplicativos "DefaultRouting", "ExumRouting" e "OutboundRouting". Recomendamos que você atribua ao aplicativo Location-Based roteamento para conferência um valor de prioridade um ponto maior do que o valor de prioridade do aplicativo "UdcAgent".

Por exemplo, se o aplicativo "UdcAgent" tiver um valor de prioridade de "2", o aplicativo "DefaultRouting" tiver um valor de prioridade de "8", o aplicativo "ExumRouting" tiver um valor de prioridade "9" e o aplicativo "OutboundRouting" tiver um valor de prioridade "10", então você deve atribuir ao aplicativo de Roteamento de Location-Based um valor de prioridade de "3". Isso colocaria a prioridade dos aplicativos na seguinte ordem: Outros aplicativos (Prioridades: 0 a 1), "UdcAgent" (Prioridade: 2), Location-Based aplicativo de Conferência de Roteamento (Prioridade: 3), outros aplicativos (Prioridades: 4 a 8), "DefaultRouting" (Prioridade: 9), "ExumRouting" (Prioridade: 10) e "OutboundRouting" (Prioridade: 11).

Depois de encontrar o valor de prioridade correto para o aplicativo roteamento para conferência Location-Based, digite o seguinte cmdlet para cada pool Front-End ou servidor Edição Standard que habilita os usuários habilitados para roteamento Location-Based:

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri <http://www.microsoft.com/LCS/LBRouting>
```

Por exemplo:

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Depois de usar esse cmdlet, reinicie todos os servidores Front-End no pool ou os servidores Edição Standard onde o aplicativo de roteamento de Location-Based conferência foi habilitado.

> [!IMPORTANT]
> Location-Based As imposições de roteamento para conferências ou transferências consultivas não serão impostas até que todos os Servidores Front-End nos pools aplicáveis ou os servidores Edição Standard sejam reiniciados. Se você definir **-Critical** **como $true** nos cmdlets anteriores, seus serviços Skype for Business Server serão reiniciados imediatamente. Se você não quiser que esses serviços reinicie imediatamente, de definir **-Critical** como **$false** por enquanto e, em seguida, use **Set-CsServerApplication** para alterar **-Critical** **para** $true mais tarde, depois que os serviços foram reiniciados.

Depois que o aplicativo roteamento para conferência do Location-Based tiver sido habilitado com êxito e todos os servidores aplicáveis tenham sido reiniciados, todas as conferências organizadas por usuários do Skype for Business habilitados para o roteamento do Location-Based serão monitoradas para evitar o desvio de tarifa PSTN


