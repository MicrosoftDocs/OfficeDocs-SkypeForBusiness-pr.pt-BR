---
title: Roteamento baseado em local para conferência no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: cec7eb1f853752997ca3dcfbe8546b86227fde9b
ms.sourcegitcommit: d664ef6994e242bf18a29dac31286c78c163478a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2020
ms.locfileid: "44710735"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Roteamento baseado em local para conferência no Skype for Business Server

Planejamento de roteamento baseado em local para conferência no Skype for Business Server Enterprise Voice, incluindo transferências de chamadas consultivas.

O roteamento baseado em local permite restringir o roteamento de chamadas entre pontos de extremidade VoIP e pontos de extremidade PSTN com base no local das partes na chamada. O roteamento baseado em local para conferência permite que você aplique regras de roteamento com base no local em reuniões (ou seja, conferências) para impedir o desvio de chamada PSTN. O aplicativo monitora uma conferência ativa e aplica as restrições de roteamento com base no local com base no local de usuários participantes. O roteamento baseado em local para o aplicativo de conferência adicional permite a imposição de restrições de roteamento com base no local para transferências consultivas envolvendo pontos de extremidade PSTN.

O aplicativo de conferência de roteamento baseado em local oferece ao Skype for Business conferências um mecanismo para a prevenção de desvio de chamada PSTN. O aplicativo monitora conferências ativas e impõe restrições de roteamento com base no local com base no local dos usuários participantes do Skype for Business.

O aplicativo de conferência de roteamento baseado em local determina se o roteamento baseado em local deve ser aplicado em uma reunião do Skype for Business se os seguintes critérios forem atendidos:

- O organizador da reunião está habilitado para roteamento baseado em local. As restrições de roteamento com base no local serão aplicadas somente a conferências organizadas por usuários habilitados para roteamento baseado em local.

- Pelo menos um participante de reunião é um ponto de extremidade PSTN. As restrições de roteamento com base no local são aplicáveis apenas para conferências que incluem pontos de extremidade PSTN.

- O local de rede onde o gateway PSTN usado para fazer a ponte da conferência para o PSTN está localizado, bem como os sites de rede onde os organizadores e participantes estão se conectando.

O roteamento baseado em local para o aplicativo de conferência impede a participação de usuários do Skype for Business e pontos de extremidade PSTN de diferentes sites de rede para a mesma conferência. Se o organizador de uma reunião estiver habilitado para roteamento baseado em local, o aplicativo de conferência imporá as seguintes restrições:

- Os pontos de extremidade que podem participar de uma reunião do Skype for Business dependem dos pontos de extremidade que já ingressaram na conferência, e essa restrição é ajustada conforme os pontos de extremidade associados deixam e novos pontos de extremidade ingressam na conferência. Se os organizadores e participantes estiverem participando de uma reunião do Skype for Business do mesmo local de rede, então um ponto de extremidade PSTN, outro participante do mesmo local de rede, outro participante de um site de rede diferente ou um participante de um site de rede desconhecido poderá ingressar.

- Se os organizadores e participantes estiverem participando da reunião de sites de rede diferentes ou desconhecidos, um ponto de extremidade PSTN não terá permissão para ingressar na reunião se a chamada PSTN ingresses de um tronco SIP habilitado para roteamento baseado em local.

- Se os organizadores e participantes estiverem participando da reunião do mesmo local de rede e se houver participantes participando da mesma reunião da PSTN, um ponto de extremidade do Skype for Business de um site de rede diferente não tem permissão para ingressar na reunião.

Essas restrições de roteamento com base no local de conferência são resumidas na tabela a seguir.

|Usuário (s) em uma conferência em um determinado ponto|Usuário (s) com permissão para ingressar na conferência|Usuário (s) não autorizados a ingressar na conferência|
|:-----|:-----|:-----|
|Usuário (s) de cliente VoIP do Skype for Business em um único site de rede  <br/> |Usuário de cliente VoIP do Skype for Business do mesmo local de rede  <br/> Usuário de cliente VoIP do Skype for Business de um site de rede diferente  <br/> Usuário de cliente VoIP do Skype for Business de um site de rede desconhecido  <br/> Usuário de cliente VoIP federado do Skype for Business  <br/> Usuário ingressando a partir de um ponto de extremidade PSTN  <br/> |Nenhuma  <br/> |
|Usuário (s) de cliente VoIP do Skype for Business de um site de rede desconhecido  <br/> |Usuário de cliente VoIP do Skype for Business de qualquer site  <br/> Usuário de cliente VoIP do Skype for Business de um site desconhecido  <br/> Usuário de cliente VoIP federado do Skype for Business  <br/> |Ingresso de usuário por meio de um ponto de extremidade PSTN  <br/> |
|Usuários de cliente VoIP do Skype for Business de diferentes locais de rede  <br/> |Usuário de cliente VoIP do Skype for Business de qualquer site de rede  <br/> Usuário de cliente VoIP do Skype for Business de um site de rede desconhecido  <br/> Usuário de cliente VoIP federado do Skype for Business  <br/> |Ingresso de usuário por meio de um ponto de extremidade PSTN  <br/> |
|Usuário (s) de cliente VoIP do Skype for Business de um único site de rede e usuários ingressando de um ponto de extremidade PSTN  <br/> |Usuário de cliente VoIP do Skype for Business do mesmo local de rede  <br/> |Usuário de cliente VoIP do Skype for Business de um site de rede diferente  <br/> Usuário de cliente VoIP do Skype for Business de um site de rede desconhecido  <br/> Usuário de cliente VoIP federado do Skype for Business  <br/> |

Veja a seguir as características adicionais do aplicativo de roteamento baseado em local para conferência:

- Quando um usuário não tem permissão para ingressar em uma conferência determinada por restrições de roteamento baseado em local, a chamada para a conferência será rejeitada e o cliente Skype for Business relatará que a chamada não foi concluída ou terminou.

- Um ponto de extremidade PSTN ingressando em uma conferência com enforces de roteamento baseado em local não será restrito a ingressar na conferência independentemente de seu estado se o ponto de extremidade ingressar por meio de um tronco que não está habilitado para roteamento baseado em local.

- Um sistema PBX conectado a um servidor de mediação por meio de um tronco SIP que não faz chamadas de saída para o PSTN terá os mesmos impostos que os usuários do Skype for Business localizados no mesmo local de rede onde o tronco SIP está definido. Por exemplo, um ponto de extremidade PSTN poderá ingressar em uma conferência com um usuário PBX e um usuário do Skype for Business se eles estiverem localizados no mesmo local de rede; caso contrário, o ponto de extremidade PSTN não terá permissão para ingressar na conferência se o usuário do PBX estiver em um local de rede diferente do usuário do Skype for Business.

> [!NOTE]
> Com a atualização cumulativa 4 do Skype for Business, o comportamento na seguinte tabela deve ser observado:

|Usuário|Outra parte|Action|Resultado|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |O Skype for Business Mobile está em uma chamada PSTN. O Skype for Business Mobile então Escalona a chamada para um atendedor automático de conferência (CAA).  <br/> |A chamada é bloqueada, com uma mensagem de erro apropriada.  <br/> |
|Skype for Business Mobile  <br/> |Cliente do Skype for Business ou federado  <br/> |O cliente ou usuário federado está em uma chamada VoIP para um usuário de roteamento baseado em local móvel do Skype for Business e qualquer uma das partes é escalonada para um CAA.  <br/> |A chamada de escalonamento é bloqueada, com uma mensagem de erro apropriada.  <br/> |

## <a name="consultative-call-transfers"></a>Transferências de chamadas consultivas

Além de aplicar o roteamento baseado em local às reuniões do Skype for Business, o roteamento baseado em local para o aplicativo de conferência impõe restrições de roteamento com base no local em transferências de chamadas consuldas que são de saída para pontos de extremidade PSTN. Uma transferência de chamada consultiva é estabelecida entre duas partes em que uma das partes transfere a chamada para um novo usuário. Por exemplo, um ponto de extremidade PSTN chama o usuário A (chamado do Skype for Business). O usuário A determina que o usuário PSTN deve ser encaminhado para o usuário B (Skype for Business usuário). O usuário A coloca a chamada com o usuário PSTN em espera e chama o usuário B. o usuário B concorda em falar com o usuário PSTN. O usuário A transfere a chamada em espera para o usuário B.

**Fluxo de chamadas de transferência de chamadas consultivas**

![Roteamento baseado em local para o diagrama de conferência](../../media/LocationBasedRoutingForConferencing.jpg)

Quando um usuário habilitado para roteamento baseado em local inicia uma transferência de chamada consultiva de um ponto de extremidade PSTN (conforme mostrado na figura anterior), isso cria duas chamadas ativas, uma chamada entre o usuário PSTN e o usuário A do Skype for Business e a outra entre o usuário do Skype for Business e o usuário B do Skype for Business B. o comportamento a seguir é imposto pelo roteamento baseado em local para o aplicativo de conferência :

- Se o tronco SIP encaminhar a chamada PSTN estiver autorizado a redirecionar a chamada PSTN para o site de rede onde o Skype for Business User B (ou seja, destino da transferência) estiver localizado, a transferência de chamada será permitida; caso contrário, a transferência de chamadas consuldas será bloqueada. Essa autorização é executada com base no local da parte transferida que está no mesmo local de rede que o tronco SIP que está encaminhando a chamada ativa para o ponto de extremidade PSTN.

- Se o tronco SIP encaminhar a chamada PSTN de entrada não estiver autorizado a encaminhar chamadas para o local de rede onde a parte transferida (Skype for Business User B) estiver localizada ou a parte transferida estiver localizada em um site de rede desconhecido, a transferência de chamada consultiva para o ponto de extremidade PSTN (ou seja, destino da transferência de chamada) será bloqueada.

A tabela a seguir descreve como as restrições de roteamento baseadas em local são aplicadas pelo roteamento baseado em local para o aplicativo de conferência para transferências de chamadas consultivas. Embora os pontos de extremidade PBX não estejam diretamente associados a um site de rede, o tronco SIP ao qual o PBX está conectado pode ser atribuído a um local de rede. Portanto, o ponto de extremidade de PBX pode ser indiretamente associado a um site de rede.


|Site de rede da parte transferida por chamada|Local de rede do destino da transferência de chamadas|Comportamento|
|:-----|:-----|:-----|
|Ponto de extremidade PSTN  <br/> |O usuário do Skype for Business no mesmo local de rede (ou seja, site 1)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PSTN  <br/> |Usuário do Skype for Business em sites de rede diferentes (ou seja, site 2)  <br/> |A transferência consultiva não será permitida  <br/> |
|Ponto de extremidade PSTN  <br/> |Usuário do Skype for Business em um site de rede desconhecido  <br/> |A transferência consultiva não será permitida  <br/> |
|Ponto de extremidade PSTN  <br/> |Usuário federado do Skype for Business  <br/> |A transferência consultiva não será permitida  <br/> |
|Ponto de extremidade PSTN  <br/> |Ponto de extremidade de PBX no mesmo site (ou seja, site 1)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PSTN  <br/> |Ponto de extremidade de PBX em sites diferentes (ou seja, site 2)  <br/> |A transferência consultiva não será permitida  <br/> |
|Ponto de extremidade de PBX no mesmo site (ou seja, site 1)  <br/> |Ponto de extremidade PSTN  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade de PBX em um site diferente (ou seja, site 2)  <br/> |Ponto de extremidade PSTN  <br/> |A transferência consultiva não será permitida  <br/> |
|Ponto de extremidade de PBX em qualquer site  <br/> |O usuário do Skype for Business no mesmo local de rede (ou seja, site 1)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade de PBX em qualquer site  <br/> |Usuário do Skype for Business em sites de rede diferentes (ou seja, site 2)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade de PBX em qualquer site  <br/> |Usuário do Skype for Business em um site de rede desconhecido  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade de PBX em qualquer site  <br/> |Usuário federado do Skype for Business  <br/> |A transferência consultiva será permitida  <br/> |

## <a name="requirements"></a>Requirements

O roteamento baseado em local para o aplicativo de conferência requer que o Skype for Business Server ou a atualização cumulativa 2 do Lync Server 2013 seja implantado em todos os pools de front-end e servidores Standard Edition em sua topologia. Se essas versões do servidor não estiverem instaladas em alguns servidores em sua topologia, as restrições de roteamento baseadas em local não poderão ser totalmente impostas em reuniões e transferências de chamadas consultivas.

A tabela a seguir identifica a combinação de funções de servidor e versões que dão suporte ao roteamento baseado em local.


|Versão do pool de front-end|Versão do servidor de mediação|Com suporte|
|:-----|:-----|:-----|
|Atualização cumulativa 2 do Skype for Business Server ou do Lync Server 2013  <br/> |Atualização cumulativa 2 do Skype for Business Server ou do Lync Server 2013  <br/> |Sim  <br/> |
|Atualização cumulativa 2 do Lync Server 2013  <br/> |Atualização cumulativa 1 do Lync Server 2013  <br/> |Não  <br/> |
|Atualização cumulativa 2 do Lync Server 2013  <br/> |Lync Server 2010  <br/> |Não  <br/> |
|Atualização cumulativa 2 do Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |Não  <br/> |
|Atualização cumulativa 1 do Lync Server 2013  <br/> |Qualquer tamanho  <br/> |Não  <br/> |
|Lync Server 2010  <br/> |Qualquer tamanho  <br/> |Não  <br/> |
|Office Communications Server 2007 R2  <br/> |Qualquer tamanho  <br/> |Não  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Configuração do roteamento baseado em local para conferência

O roteamento baseado em local para o aplicativo de conferência depende da configuração do roteamento baseado em local. As principais configurações são as seguintes:

- O local dos participantes que ingressam em uma reunião é determinado com base no seu site de rede. Um site de rede e suas sub-redes de rede associadas devem ser definidos no Skype for Business Server para reforçar o roteamento baseado em local.

- Para impor o roteamento baseado em local de reuniões, os participantes do Skype for Business devem estar habilitados para roteamento baseado em local.

- Para impor o roteamento baseado em local de pontos de extremidade PSTN que participam de reuniões, o tronco SIP usado para conectar os pontos de extremidade PSTN deve ser configurado para roteamento baseado em local.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Habilitando o roteamento baseado em local para conferência

O roteamento baseado em local para o aplicativo de conferência está desabilitado por padrão. Antes de habilitar esse aplicativo, você precisa determinar a prioridade correta a ser atribuída ao aplicativo. Para determinar essa prioridade, execute o seguinte cmdlet no Shell de gerenciamento do Skype for Business Server:

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

Neste cmdlet, \<Pool FQDN\> é o pool no qual o roteamento baseado em local para o aplicativo de conferência deve ser habilitado.

Este cmdlet retornará a lista de aplicativos hospedados pelo Skype for Business Server e o valor de prioridade para cada um deles. O roteamento baseado em local para o aplicativo de conferência precisa receber um valor de prioridade maior do que o aplicativo "UdcAgent" e menor do que os aplicativos "defaultrouting", "ExumRouting" e "OutboundRouting". Recomendamos que você atribua o roteamento baseado em local para o aplicativo de conferência um valor de prioridade que seja um ponto maior do que o valor de prioridade do aplicativo "UdcAgent".

Por exemplo, se o aplicativo "UdcAgent" tiver um valor de prioridade "2", o aplicativo "defaultrouting" tem um valor de prioridade "8", o aplicativo "ExumRouting" tem um valor de prioridade "9" e o aplicativo "OutboundRouting" tem um valor de prioridade "10", então você deve atribuir o roteamento baseado em local para o aplicativo de conferência um valor de prioridade "3" Isso colocaria a prioridade dos aplicativos na seguinte ordem: outros aplicativos (prioridades: 0 a 1), "UdcAgent" (prioridade: 2), aplicativo de conferência de roteamento baseado em local (prioridade: 3), outros aplicativos (prioridades: 4 a 8), "roteamento default" (prioridade: 9), "ExumRouting" (prioridade: 10) e "OutboundRouting" (prioridade: 11).

Depois de encontrar o valor de prioridade correto para o aplicativo roteamento baseado em local para conferência, digite o seguinte cmdlet para cada pool de front-end ou servidor Standard Edition que tenha usuários habilitados para roteamento baseado em local:

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri <http://www.microsoft.com/LCS/LBRouting>
```

Por exemplo:

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Após usar esse cmdlet, reinicie todos os servidores front-end no pool ou os servidores Standard Edition onde o roteamento baseado em local para o aplicativo de conferência foi habilitado.

> [!IMPORTANT]
> Os enforces de roteamento baseado em local para conferências ou transferências de consultoria não serão impostos até que todos os servidores front-end nos pools aplicáveis ou servidores Standard Edition sejam reiniciados. Se você definir **-crítico** como **$true** nos cmdlets anteriores, seus serviços do Skype for Business Server serão reiniciados imediatamente. Se você não quiser que esses serviços reiniciem imediatamente, defina **-** os como **$false** por enquanto e, em seguida, use **set-CsServerApplication** para alterá **-** lo para **$true** mais tarde, após os serviços terem sido reiniciados.

Depois que o roteamento baseado em local para o aplicativo de conferência tiver sido habilitado com êxito e todos os servidores aplicáveis tiverem sido reiniciados, todas as conferências organizadas por usuários do Skype for Business habilitados para roteamento baseado em local serão monitoradas para evitar o bypass de chamadas PSTN


