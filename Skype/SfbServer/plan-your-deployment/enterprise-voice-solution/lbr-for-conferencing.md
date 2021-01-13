---
title: Location-Based roteamento para conferência no Skype for Business Server
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
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: Planejamento de roteamento baseado em local para conferência no Skype for Business Server Enterprise Voice, incluindo transferências de chamadas consultivas.
ms.openlocfilehash: 744f4b313f7ea458013aa0e45cff37ebbf85068a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825571"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Location-Based roteamento para conferência no Skype for Business Server

Planejamento de roteamento baseado em local para conferência no Skype for Business Server Enterprise Voice, incluindo transferências de chamada consultiva.

Location-Based roteamento possibilita restringir o roteamento de chamadas entre pontos de extremidade VoIP e pontos de extremidade PSTN com base no local das partes na chamada. Location-Based roteamento para conferência permite impor regras de Roteamento Location-Based em reuniões (ou seja, conferências) para impedir bypass de chamadas tarifadas PSTN. O aplicativo monitora uma conferência ativa e impõe restrições Location-Based roteamento com base no local dos usuários participantes. O Location-Based roteamento para conferência adicionalmente permite a imposição de restrições de roteamento Location-Based para transferências de consulta envolvendo pontos de extremidade PSTN.

O Location-Based conferência de roteamento fornece às Conferências do Skype for Business um mecanismo para a prevenção de bypass de chamada tarifada PSTN. O aplicativo monitora conferências ativas e impõe restrições Location-Based roteamento com base no local dos usuários do Skype for Business que participam.

O Location-Based de Conferência de Roteamento de Location-Based determina se o Roteamento Location-Based deve ser imposto em uma reunião do Skype for Business se os seguintes critérios são atendidos:

- O organizador da reunião está habilitado para o Roteamento Location-Based Local. Location-Based de roteamento serão aplicadas somente a conferências organizadas por usuários habilitados para o Roteamento Location-Based Usuário.

- Pelo menos um participante da reunião é um ponto de extremidade PSTN. Location-Based roteamento são aplicáveis apenas a conferências que incluem pontos de extremidade PSTN.

- O local de rede onde o gateway PSTN usado para fazer a ponte da conferência para a PSTN está localizado, bem como os sites de rede de onde os organizadores e participantes estão se conectando.

O Location-Based roteamento para conferência impede a participação de usuários do Skype for Business e pontos de extremidade PSTN de diferentes locais de rede para a mesma conferência. Se o organizador de uma reunião estiver habilitado para o Roteamento Location-Based, o aplicativo de Conferência aplicará as seguintes restrições:

- Os pontos de extremidade que podem ingressar em uma reunião do Skype for Business dependem dos pontos de extremidade que já ingressaram na conferência, e essa restrição se ajusta à medida que pontos de extremidade ingressam e novos pontos de extremidade ingressam na conferência. Se os organizadores e participantes ingressarem em uma reunião do Skype for Business a partir do mesmo local de rede, um ponto de extremidade PSTN, outro participante do mesmo local de rede, outro participante de um local de rede diferente ou um participante de um local de rede desconhecido poderão participar.

- Se os organizadores e participantes ingressarem na reunião de locais de rede diferentes ou desconhecidos, um ponto de extremidade PSTN não poderá ingressar na reunião se a chamada PSTN entrar em um tronco SIP habilitado para Roteamento Location-Based.

- Se os organizadores e participantes ingressarem na reunião a partir do mesmo local de rede e houver participantes participando da mesma reunião da PSTN, um ponto de extremidade do Skype for Business de um local de rede diferente não poderá participar da reunião.

Essas restrições de Location-Based roteamento estão resumidas na tabela a seguir.

|Usuários em uma conferência em um determinado ponto|Usuários com permissão para ingressar na conferência|Usuários não autorizados a ingressar na conferência|
|:-----|:-----|:-----|
|Skype for Business VoIP client user(s) from a single network site  <br/> |Usuário cliente VoIP do Skype for Business do mesmo local de rede  <br/> Usuário cliente VoIP do Skype for Business de um local de rede diferente  <br/> Usuário cliente VoIP do Skype for Business de um local de rede desconhecido  <br/> Usuário federado do cliente VoIP do Skype for Business  <br/> Usuário participando de um ponto de extremidade PSTN  <br/> |Nenhum  <br/> |
|Usuários de cliente VoIP do Skype for Business de um local de rede desconhecido  <br/> |Usuário cliente VoIP do Skype for Business de qualquer site  <br/> Usuário cliente VoIP do Skype for Business de um site desconhecido  <br/> Usuário federado do cliente VoIP do Skype for Business  <br/> |Usuário participando por meio de um ponto de extremidade PSTN  <br/> |
|Usuários cliente VoIP do Skype for Business de diferentes locais de rede  <br/> |Usuário cliente VoIP do Skype for Business de qualquer local de rede  <br/> Usuário cliente VoIP do Skype for Business de um local de rede desconhecido  <br/> Usuário federado do cliente VoIP do Skype for Business  <br/> |Usuário participando por meio de um ponto de extremidade PSTN  <br/> |
|Usuários de cliente VoIP do Skype for Business de um único local de rede e usuários in joining de um ponto de extremidade PSTN  <br/> |Usuário cliente VoIP do Skype for Business do mesmo local de rede  <br/> |Usuário cliente VoIP do Skype for Business de um local de rede diferente  <br/> Usuário cliente VoIP do Skype for Business de um local de rede desconhecido  <br/> Usuário federado do cliente VoIP do Skype for Business  <br/> |

A seguir estão as características adicionais do aplicativo Location-Based roteamento para conferência:

- Quando um usuário não tem permissão para ingressar em uma conferência determinadas restrições de Roteamento Location-Based, a chamada para a conferência será rejeitada e o cliente Skype for Business relatará que a chamada não foi concluída ou terminou.

- Um ponto de extremidade PSTN que ingressar em uma conferência com imposições de Roteamento do Location-Based não será restrito a ingressar na conferência independentemente de seu estado se o ponto de extremidade ingressar por meio de um tronco que não está habilitado para o Roteamento Location-Based.

- Um sistema PBX conectado a um Servidor de Mediação sobre um tronco SIP que não egressa chamadas para a PSTN terá as mesmas imposições que os usuários do Skype for Business localizados no mesmo local de rede onde o tronco SIP está definido. Por exemplo, um ponto de extremidade PSTN poderá ingressar em uma conferência com um usuário de PBX e um usuário do Skype for Business se ele estiver localizado no mesmo local de rede; Caso contrário, o ponto de extremidade PSTN não poderá ingressar na conferência se o usuário pbx estiver em um local de rede diferente do usuário do Skype for Business.

> [!NOTE]
> Com a Atualização Cumulativa 4 do Skype for Business, o comportamento na tabela a seguir deve ser observado:

|Usuário|Outra parte|Action|Resultado|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |O Skype for Business Mobile está em uma chamada PSTN. Em seguida, o Skype for Business Mobile escalona a chamada para um CaA (Atendimento Automático de Conferência).  <br/> |A chamada é bloqueada, com uma mensagem de erro apropriada.  <br/> |
|Skype for Business Mobile  <br/> |Cliente do Skype for Business ou Usuário Federado  <br/> |O Cliente ou Usuário Federado está em uma chamada VoIP para um usuário de Roteamento de Location-Based Do Skype for Business Mobile e uma das partes escalona para um CAA.  <br/> |A chamada de escalonamento é bloqueada, com uma mensagem de erro apropriada.  <br/> |

## <a name="consultative-call-transfers"></a>Transferências de chamada consultiva

Além de impor o roteamento Location-Based para reuniões do Skype for Business, o aplicativo roteamento Location-Based para conferência impõe restrições de roteamento Location-Based em transferências de chamadas consultivas que egressam para pontos de extremidade PSTN. Uma transferência de chamada consultiva é uma chamada estabelecida entre duas partes em que uma das partes transfere a chamada para um novo usuário. Por exemplo, um ponto de extremidade PSTN chama o usuário A (destinatário da chamada do Skype for Business). O Usuário A determina que o usuário PSTN deve ser encaminhado para o usuário B (usuário do Skype for Business). O Usuário A coloca a chamada com o usuário PSTN em espera e chama o usuário B. O Usuário B concorda em falar com o usuário PSTN. O Usuário A transfere a chamada em espera para o usuário B.

**Fluxo de chamada de transferência de chamada consultiva**

![Roteamento baseado em local para diagrama de conferência](../../media/LocationBasedRoutingForConferencing.jpg)

Quando um usuário habilitado para o Roteamento do Location-Based inicia uma transferência de chamada consultiva de um ponto de extremidade PSTN (conforme mostrado na figura anterior), isso cria duas chamadas ativas, uma chamada entre o usuário PSTN e o usuário A do Skype for Business e a outra entre o usuário A do Skype for Business e o usuário do Skype for Business B. O comportamento a seguir é imposto pelo aplicativo de Roteamento Location-Based para Conferência:

- Se o tronco SIP que roteia a chamada PSTN estiver autorizado a rotear a chamada PSTN para o local de rede onde o usuário B do Skype for Business (ou seja, destino da transferência) está localizado, a transferência de chamada será permitida; caso contrário, a transferência de chamada consultiva será bloqueada. Essa autorização é realizada com base no local da parte transferida que está no mesmo local de rede que o tronco SIP que está roteando a chamada ativa para o ponto de extremidade PSTN.

- Se o tronco SIP que roteia a chamada PSTN de entrada não estiver autorizado a rotear chamadas para o local de rede onde a parte transferida (usuário do Skype for Business B) está localizada ou a parte transferida está localizada em um local de rede desconhecido, a transferência de chamada consultiva para o ponto de extremidade PSTN (ou seja, destino de transferência de chamada) será bloqueada.

A tabela a seguir descreve como Location-Based roteamento são aplicadas pelo aplicativo Location-Based roteamento para conferência para transferências de chamada consultiva. Embora os pontos de extremidade PBX não sejam associados diretamente a um local de rede, o tronco SIP ao que o PBX está conectado pode ser atribuído a um local de rede. Portanto, o ponto de extremidade PBX pode ser indiretamente associado a um local de rede.


|Local de rede da parte transferida da chamada|Local de rede de destino de transferência de chamada|Comportamento|
|:-----|:-----|:-----|
|Ponto de extremidade PSTN  <br/> |Usuário do Skype for Business no mesmo local de rede (ou seja, local 1)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PSTN  <br/> |Usuário do Skype for Business em diferentes locais de rede (ou seja, local 2)  <br/> |A transferência consultiva não será permitido  <br/> |
|Ponto de extremidade PSTN  <br/> |Usuário do Skype for Business em um local de rede desconhecido  <br/> |A transferência consultiva não será permitido  <br/> |
|Ponto de extremidade PSTN  <br/> |Usuário federado do Skype for Business  <br/> |A transferência consultiva não será permitido  <br/> |
|Ponto de extremidade PSTN  <br/> |Ponto de extremidade PBX no mesmo site (ou seja, site 1)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PSTN  <br/> |Ponto de extremidade PBX em sites diferentes (ou seja, site 2)  <br/> |A transferência consultiva não será permitido  <br/> |
|Ponto de extremidade PBX no mesmo site (ou seja, site 1)  <br/> |Ponto de extremidade PSTN  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PBX em um site diferente (ou seja, site 2)  <br/> |Ponto de extremidade PSTN  <br/> |A transferência consultiva não será permitido  <br/> |
|Ponto de extremidade PBX em qualquer site  <br/> |Usuário do Skype for Business no mesmo local de rede (ou seja, local 1)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PBX em qualquer site  <br/> |Usuário do Skype for Business em diferentes locais de rede (ou seja, local 2)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PBX em qualquer site  <br/> |Usuário do Skype for Business em um local de rede desconhecido  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PBX em qualquer site  <br/> |Usuário federado do Skype for Business  <br/> |A transferência consultiva será permitida  <br/> |

## <a name="requirements"></a>Requirements

O aplicativo de Roteamento Location-Based para Conferência exige que o Skype for Business Server ou a Atualização Cumulativa 2 do Lync Server 2013 seja implantado em todos os pools do Front-End e Servidores Standard Edition em sua topologia. Se essas versões de servidor não são instaladas em alguns servidores em sua topologia, as restrições de roteamento Location-Based não podem ser totalmente impostas em reuniões e transferências de chamadas de consulta.

A tabela a seguir identifica a combinação de funções de servidor e versões que suportam o Location-Based Routing.


|Front-End do pool|Versão do Servidor de Mediação|Com suporte|
|:-----|:-----|:-----|
|Skype for Business Server ou Atualização Cumulativa 2 do Lync Server 2013  <br/> |Skype for Business Server ou Atualização Cumulativa 2 do Lync Server 2013  <br/> |Sim  <br/> |
|Atualização Cumulativa 2 do Lync Server 2013  <br/> |Atualização cumulativa 1 do Lync Server 2013  <br/> |Não  <br/> |
|Atualização Cumulativa 2 do Lync Server 2013  <br/> |Lync Server 2010  <br/> |Não  <br/> |
|Atualização Cumulativa 2 do Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |Não  <br/> |
|Atualização cumulativa 1 do Lync Server 2013  <br/> |Qualquer  <br/> |Não  <br/> |
|Lync Server 2010  <br/> |Qualquer  <br/> |Não  <br/> |
|Office Communications Server 2007 R2  <br/> |Qualquer  <br/> |Não  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Configuração de Location-Based roteamento para conferência

O Location-Based roteamento para conferência depende da configuração de roteamento Location-Based dados. As principais configurações são as seguintes:

- A localização dos participantes que participam de uma reunião é determinada com base em seu local de rede. Um local de rede e suas sub-redes associadas devem ser definidos no Skype for Business Server para impor o roteamento Location-Based rede.

- Para impor Location-Based roteamento de reuniões, os participantes do Skype for Business devem estar habilitados para o Roteamento Location-Based Usuário.

- Para impor Location-Based roteamento de pontos de extremidade PSTN que in unem reuniões, o tronco SIP usado para conectar os pontos de extremidade PSTN deve ser configurado para o Roteamento Location-Based.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Habilitando o roteamento Location-Based para conferência

O Location-Based roteamento para aplicativo de conferência está desabilitado por padrão. Antes de habilitar esse aplicativo, você precisa determinar a prioridade certa a ser atribuído ao aplicativo. Para determinar essa prioridade, execute o seguinte cmdlet no Shell de Gerenciamento do Skype for Business Server:

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

Neste cmdlet, é o pool no qual o aplicativo Location-Based roteamento para conferência deve \<Pool FQDN\> ser habilitado.

Este cmdlet retornará a lista de aplicativos hospedados pelo Skype for Business Server e o valor de prioridade para cada um deles. O aplicativo Location-Based roteamento para conferência precisa ter um valor de prioridade maior do que o aplicativo "UdcAgent" e menor do que os aplicativos "DefaultRouting", "ExumRouting" e "OutboundRouting". Recomendamos que você atribua ao aplicativo Location-Based roteamento para conferência um valor de prioridade um ponto maior do que o valor de prioridade do aplicativo "UdcAgent".

Por exemplo, se o aplicativo "UdcAgent" tiver um valor de prioridade "2", o aplicativo "DefaultRouting" tiver um valor de prioridade "8", o aplicativo "ExumRouting" tiver um valor de prioridade "9" e o aplicativo "OutboundRouting" tiver um valor de prioridade "10", você deverá atribuir ao aplicativo Location-Based Routing for Conferencing um valor de prioridade "3". Isso colocaria a prioridade dos aplicativos na seguinte ordem: Outros aplicativos (Prioridades: 0 a 1), "UdcAgent" (Prioridade: 2), aplicativo de Conferência de Roteamento do Location-Based (Prioridade: 3), outros aplicativos (Prioridades: 4 a 8), "DefaultRouting" (Prioridade: 9), "ExumRouting" (Prioridade: 10) e "OutboundRouting" (Prioridade: 11).

Depois de encontrar o valor de prioridade correto para o aplicativo de Roteamento Location-Based para Conferência, digite o seguinte cmdlet para cada pool do Front-End ou Servidor Standard Edition que ative os usuários habilitados para o Roteamento Location-Based:

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri <http://www.microsoft.com/LCS/LBRouting>
```

Por exemplo:

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Depois de usar esse cmdlet, reinicie todos os servidores front-end no pool ou nos Servidores Standard Edition onde o aplicativo Location-Based roteamento para conferência foi habilitado.

> [!IMPORTANT]
> Location-Based as imposições de roteamento para conferências ou transferências de consulta não serão aplicadas até que todos os Servidores front-end nos pools aplicáveis ou os Servidores Standard Edition sejam reiniciados. Se você definir **-Critical** **$true** nos cmdlets anteriores, seus serviços do Skype for Business Server serão reiniciados imediatamente. Se você não quiser que esses serviços reinicie imediatamente, de definir **-Critical** como **$false** por enquanto e, em seguida, use **Set-CsServerApplication** para alterar **-Critical** para **$true** posterior, depois que os serviços foram reiniciados.

Depois que o aplicativo de Roteamento Location-Based para Conferência tiver sido habilitado com êxito e todos os servidores aplicáveis foram reiniciados, todas as conferências organizadas por usuários do Skype for Business habilitadas para o Roteamento Location-Based serão monitoradas para evitar bypass de chamada tarifada PSTN


