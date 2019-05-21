---
title: Roteamento baseado em local para conferências no Skype for Business Server
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
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: Planejando o roteamento baseado em local para conferências no Skype for Business Server Enterprise Voice, incluindo transferências de chamadas consultivas.
ms.openlocfilehash: d9ca03920fe361cf4d7692fd80031bef01b03b17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276779"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Roteamento baseado em local para conferências no Skype for Business Server

Planejando o roteamento baseado em local para conferências no Skype for Business Server Enterprise Voice, incluindo transferências de chamadas consultivas.

O roteamento baseado em local torna possível restringir o roteamento de chamadas entre pontos de extremidade VoIP e pontos de extremidade PSTN com base no local das partes na chamada. O roteamento baseado em local para a conferência permite que você aplique regras de roteamento baseadas em local em reuniões (como conferências) para impedir o bypass de chamada PSTN. O aplicativo monitora uma conferência ativa e impõe restrições de roteamento com base na localização com base na localização dos usuários participantes. O roteamento baseado em localização para aplicativo de conferência Adicionalmente permite a imposição de restrições de roteamento baseado em localização para transferências consultivas envolvendo pontos de extremidade PSTN.

O aplicativo de conferência de roteamento baseado em local fornece às conferências do Skype for Business um mecanismo para impedir que o bypass seja interurbana de PSTN. O aplicativo monitora conferências ativas e impõe restrições de roteamento com base no local com base no local dos usuários do Skype for Business participantes.

O aplicativo de conferência de roteamento baseado em local determina se o roteamento baseado em localização deve ser imposto em uma reunião do Skype for Business se os seguintes critérios forem atendidos:

- O organizador da reunião está habilitado para roteamento baseado em local. As restrições de roteamento baseadas em local serão aplicadas somente a conferências organizadas por usuários que estão habilitados para roteamento baseado em local.

- Pelo menos um participante da reunião é um ponto de extremidade PSTN. As restrições de roteamento baseadas em local são aplicáveis somente para conferências que incluem pontos de extremidade PSTN.

- O local da rede onde o gateway PSTN usado para fazer a ligação da conferência com o PSTN está localizado, bem como os locais de rede, de onde os organizadores e os participantes estão se conectando.

O roteamento baseado em local para o aplicativo de conferência impede a participação de usuários do Skype for Business e pontos de extremidade PSTN de diferentes sites de rede para a mesma conferência. Se o organizador de uma reunião estiver habilitado para roteamento baseado em localização, o aplicativo de conferência forçará as seguintes restrições:

- Os pontos de extremidade que podem participar de uma reunião do Skype for Business dependem dos pontos de extremidade que já ingressaram na conferência, e essa restrição é ajustada quando os pontos de extremidade associados entram e os novos pontos de extremidade entram na conferência. Se os organizadores e participantes estiverem participando de uma reunião do Skype for Business no mesmo local de rede, um ponto de extremidade PSTN, outro participante do mesmo site de rede, outro participante de um site de rede diferente ou um participante de um site de rede desconhecido podem ingressar.

- Se os organizadores e os participantes estiverem ingressando na reunião de locais de rede diferentes ou desconhecidos, um ponto de extremidade PSTN não terá autorização para participar da reunião se a chamada PSTN ingressar de um tronco SIP habilitado para Roteamento Baseado na Localização.

- Se os organizadores e participantes estiverem ingressando na reunião no mesmo local de rede e houver participantes que ingressam na mesma reunião a partir da PSTN, um ponto de extremidade do Skype for Business de um site de rede diferente não poderá ingressar na reunião.

Essas restrições de roteamento baseado em localização de conferências são resumidas na tabela a seguir.

| |

|**Usuário(s) em uma conferência em um determinado ponto**|**Usuário(s) autorizados a ingressar na conferência**|**Usuário(s) não autorizados a ingressar na conferência**|
|:-----|:-----|:-----|
|Usuário (s) do cliente VoIP do Skype for Business em um único site de rede  <br/> |Usuário do cliente VoIP do Skype for Business no mesmo local de rede  <br/> Usuário do cliente VoIP do Skype for Business em um site de rede diferente  <br/> Usuário do cliente VoIP do Skype for Business de um site de rede desconhecido  <br/> Usuário federado do cliente VoIP Skype for Business  <br/> Usuário ingressando a partir de um ponto de extremidade PSTN  <br/> |Nenhum  <br/> |
|Usuário (s) do cliente VoIP do Skype for Business em um site de rede desconhecido  <br/> |Usuário do cliente VoIP do Skype for Business em qualquer site  <br/> Usuário do cliente VoIP do Skype for Business de um site desconhecido  <br/> Usuário federado do cliente VoIP Skype for Business  <br/> |Usuário ingressando por meio de um ponto de extremidade PSTN  <br/> |
|Usuários do cliente VoIP do Skype for Business em diferentes locais de rede  <br/> |Usuário do cliente VoIP do Skype for Business em qualquer site de rede  <br/> Usuário do cliente VoIP do Skype for Business de um site de rede desconhecido  <br/> Usuário federado do cliente VoIP Skype for Business  <br/> |Usuário ingressando por meio de um ponto de extremidade PSTN  <br/> |
|Usuários do cliente VoIP do Skype for Business de um único site de rede e usuários que ingressam em um ponto de extremidade PSTN  <br/> |Usuário do cliente VoIP do Skype for Business no mesmo local de rede  <br/> |Usuário do cliente VoIP do Skype for Business em um site de rede diferente  <br/> Usuário do cliente VoIP do Skype for Business de um site de rede desconhecido  <br/> Usuário federado do cliente VoIP Skype for Business  <br/> |

Veja a seguir as características adicionais do aplicativo roteamento baseado em localização para conferência:

- Quando um usuário não tem permissão para ingressar em uma conferência dadas restrições de roteamento baseado em local, a chamada para a conferência será rejeitada e o cliente Skype for Business reportará que a chamada não foi concluída ou encerrada.

- Um ponto de extremidade PSTN ingressando em uma conferência com enforces de roteamento baseado em local não será restrito a ingressar na conferência independentemente de seu estado se o ponto de extremidade se associar por meio de um tronco que não está habilitado para roteamento baseado em localização.

- Um sistema PBX conectado a um servidor de mediação por meio de um tronco SIP que não faz chamadas para a PSTN terá os mesmos enforces que os usuários do Skype for Business localizados no mesmo local de rede onde o tronco SIP está definido. Por exemplo, um ponto de extremidade PSTN poderá ingressar em uma conferência com um usuário do PBX e um usuário do Skype for Business se eles estiverem localizados no mesmo site de rede; caso contrário, o ponto de extremidade PSTN não terá permissão para ingressar na conferência se o usuário do PBX estiver em um site de rede diferente do usuário do Skype for Business.

> [!NOTE]
> Com a Atualização Cumulativa 4 do Skype for Business, é preciso observar o comportamento apresentado na tabela a seguir:

|**Usuário**|**Outros**|**Ação**|**Resultado**|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |O Skype for Business Mobile está em uma chamada PSTN. O Skype for Business Mobile escalona a chamada para um CAA (Atendedor Automático de Conferência).  <br/> |A chamada é bloqueada com a mensagem de erro apropriada.  <br/> |
|Skype for Business Mobile  <br/> |Cliente ou usuário federado do Skype for Business  <br/> |O cliente ou usuário federado está em uma chamada de VoIP para um usuário de roteamento baseado em localização do Skype for Business Mobile, e o outro é encaminhado para um CAA.  <br/> |A chamada escalonada é bloqueada com a mensagem de erro apropriada.  <br/> |

## <a name="consultative-call-transfers"></a>Transferências de chamada consultiva

Além de aplicar o roteamento baseado em localização às reuniões do Skype for Business, o roteamento baseado em local para o aplicativo de conferência impõe restrições de roteamento baseado em localização em transferências de chamadas consuldas que entram em pontos de extremidade PSTN. Uma transferência de chamada consultiva é estabelecida entre duas partes em que uma delas transfere a chamada para um novo usuário. Por exemplo, um ponto de extremidade PSTN chama o usuário A (chamada do Skype for Business). O usuário A determina que o usuário PSTN deve ser encaminhado para o usuário B (usuário do Skype for Business). O usuário A coloca a chamada com o usuário PSTN em espera e liga para o usuário B. O usuário B concorda em falar com o usuário PSTN. O usuário A transfere a chamada espera para o usuário B.

**Fluxo da Transferência de Chamada Consultiva**

![Roteamento baseado em local para o diagrama de conferência](../../media/LocationBasedRoutingForConferencing.jpg)

Quando um usuário habilitado para roteamento baseado em local inicia uma transferência de chamadas consultivas de um ponto de extremidade PSTN (conforme mostrado na figura anterior), isso cria duas chamadas ativas, uma chamada entre o usuário PSTN e o usuário do Skype for Business, e a outra entre o Skype para Usuário empresarial A e usuário do Skype for Business B. o seguinte comportamento é imposto pelo roteamento baseado em local para o aplicativo de conferência:

- Se o roteamento de tronco SIP a chamada PSTN estiver autorizado a redirecionar a chamada PSTN para o site de rede onde o usuário do Skype for Business B (ou seja, destino da transferência) estiver localizado, a transferência de chamada será permitida; caso contrário, a transferência de chamadas consultivas será bloqueada. Essa autorização é realizada com base na localização da parte transferida que está no mesmo local de rede que o tronco SIP que está roteando a chamada ativa para o ponto de extremidade PSTN.

- Se o tronco SIP que faz a chamada PSTN não estiver autorizado a encaminhar chamadas para o site de rede onde a parte transferida (Skype for Business usuário B) estiver localizada ou a parte transferida transferida estiver localizada em um site de rede desconhecido, a transferência de chamadas consultivas para o ponto de extremidade PSTN (ou seja, destino de transferência de chamada) será bloqueado.

A tabela a seguir descreve como as restrições de roteamento baseado em localização são aplicadas pelo roteamento baseado em local para o aplicativo de conferência para transferências de chamadas consultivas. Embora os pontos de extremidade PBX não estejam associados diretamente a um local de rede, o tronco SIP ao qual o PBX está conectado pode ser atribuído a um local de rede. Portanto, o ponto de extremidade PBX pode ser indiretamente associado a um local de rede.


|**Local de rede da parte transferida da chamada**|**Local de rede de destino da transferência de chamada**|**Comportamento**|
|:-----|:-----|:-----|
|Ponto de extremidade PSTN  <br/> |Usuário do Skype for Business no mesmo local de rede (por exemplo, site 1)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PSTN  <br/> |Usuário do Skype for Business em diferentes sites de rede (por exemplo, site 2)  <br/> |A transferência consultiva não será permitida  <br/> |
|Ponto de extremidade PSTN  <br/> |Usuário do Skype for Business em um site de rede desconhecido  <br/> |A transferência consultiva não será permitida  <br/> |
|Ponto de extremidade PSTN  <br/> |Usuário federado do Skype for Business  <br/> |A transferência consultiva não será permitida  <br/> |
|Ponto de extremidade PSTN  <br/> |Ponto de extremidade do PBX no mesmo local (isto é, local 1)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PSTN  <br/> |Ponto de extremidade PBX em locais diferentes (isto é, local 2)  <br/> |A transferência consultiva não será permitida  <br/> |
|Ponto de extremidade do PBX no mesmo local (isto é, local 1)  <br/> |Ponto de extremidade PSTN  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade do PBX em locais diferentes (i.e. local 2)  <br/> |Ponto de extremidade PSTN  <br/> |A transferência consultiva não será permitida  <br/> |
|Ponto de extremidade PBX em qualquer local  <br/> |Usuário do Skype for Business no mesmo local de rede (por exemplo, site 1)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PBX em qualquer local  <br/> |Usuário do Skype for Business em diferentes sites de rede (por exemplo, site 2)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PBX em qualquer local  <br/> |Usuário do Skype for Business em um site de rede desconhecido  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PBX em qualquer local  <br/> |Usuário federado do Skype for Business  <br/> |A transferência consultiva será permitida  <br/> |

## <a name="requirements"></a>Requisitos

O roteamento baseado em local para o aplicativo de conferência requer que o Skype for Business Server ou a atualização cumulativa 2 do Lync Server 2013 seja implantada em todos os pools de front-end e servidores Standard Edition na sua topologia. Se essas versões do servidor não estiverem instaladas em alguns servidores na sua topologia, as restrições de roteamento baseadas em local não poderão ser totalmente impostas em reuniões e transferências de chamadas consultivas.

A tabela a seguir identifica a combinação de funções de servidor e versões que dão suporte ao roteamento baseado em localização.


|**Versão do Pool de Front-End**|**Versão do Servidor de Mediação**|**Compatível**|
|:-----|:-----|:-----|
|Atualização cumulativa 2 do Skype for Business Server ou do Lync Server 2013  <br/> |Atualização cumulativa 2 do Skype for Business Server ou do Lync Server 2013  <br/> |Sim  <br/> |
|Atualização Cumulativa 2 do Lync Server 2013  <br/> |Atualização Cumulativa 1 do Lync Server 2013  <br/> |Não  <br/> |
|Atualização Cumulativa 2 do Lync Server 2013  <br/> |Lync Server 2010  <br/> |Não  <br/> |
|Atualização Cumulativa 2 do Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |Não  <br/> |
|Atualização Cumulativa 1 do Lync Server 2013  <br/> |Qualquer um  <br/> |Não  <br/> |
|Lync Server 2010  <br/> |Qualquer um  <br/> |Não  <br/> |
|Office Communications Server 2007 R2  <br/> |Qualquer um  <br/> |Não  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Configuração do roteamento baseado em locais para conferência

O roteamento baseado em local para o aplicativo de conferência depende da configuração do roteamento baseado no local. Estas são as principais configurações:

- O local dos participantes que ingressam em uma reunião é determinado com base em seus locais de rede. Um site de rede e suas sub-redes de rede associadas devem ser definidos no Skype for Business Server para a aplicação de roteamento baseado em localização.

- Para impor o roteamento baseado em localização de reuniões, os participantes do Skype for Business devem estar habilitados para roteamento baseado em local.

- Para impor o roteamento baseado em localização de pontos de extremidade PSTN ingressando em reuniões, o tronco SIP usado para conexão dos pontos de extremidade PSTN devem ser configurados para roteamento baseado em local.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Habilitando o roteamento baseado em localização para conferência

O roteamento baseado em local para aplicativo de conferência é desabilitado por padrão. Antes de habilitá-lo, determine a prioridade certa para atribuir a ele. Para determinar essa prioridade, execute o seguinte cmdlet no Shell de gerenciamento do Skype for Business Server:

Get-CsServerApplication-serviço de identidade: registrador:<Pool FQDN>nesse cmdlet \<, o\> FQDN do pool é o pool no qual o roteamento baseado em localização para o aplicativo de conferência deve ser habilitado.

Esse cmdlet retornará a lista dos aplicativos hospedados pelo Skype for Business Server e o valor de prioridade para cada um deles. O roteamento baseado em local para o aplicativo de conferência precisa ser atribuído um valor de prioridade maior do que o aplicativo "UdcAgent" e menor do que os aplicativos "defaultrouting", "ExumRouting" e "OutboundRouting". Recomendamos que você atribua o roteamento baseado em localização para aplicativo de conferência um valor de prioridade que seja um ponto superior ao valor de prioridade do aplicativo "UdcAgent".

Por exemplo, se o aplicativo "UdcAgent" tem um valor de prioridade "2", o aplicativo "defaultrouting" tem um valor de prioridade de "8", o aplicativo "ExumRouting" tem um valor de prioridade de "9" e o aplicativo "OutboundRouting" tem um valor de prioridade de "10" e, em seguida, Você deve atribuir o roteamento baseado em local para aplicativo de conferência um valor prioritário de "3". Isso colocaria a prioridade dos aplicativos na seguinte ordem: outros aplicativos (prioridades: de 0 a 1), "UdcAgent" (prioridade: 2), aplicativo de conferência de roteamento baseado em local (prioridade: 3), outros aplicativos (prioridades: 4 a 8), " Defaultrouting "(prioridade: 9)," ExumRouting "(prioridade: 10) e" OutboundRouting "(prioridade: 11).

Depois de encontrar o valor de prioridade correto para o aplicativo de roteamento de conferência baseado em local, digite o cmdlet a seguir para cada pool Front-end ou servidor Standard Edition que os usuários habilitarem para roteamento baseado em localização:

Novo-CsServerApplication-serviço de identidade: registrador:`<Pool FQDN`_GT_/LBRouting \<-prioridade\> de aplicação habilitada $true-URI $true-URI<http://www.microsoft.com/LCS/LBRouting> 

Por exemplo:

New-CsServerApplication-Identity Service:Registrar:LS2013CU2LBRPool. contoso. com/LBRouting-Priority 3-Enabled $true-Critical $true-URIhttp://www.microsoft.com/LCS/LBRouting 

Depois de usar esse cmdlet, reinicie todos os servidores front-end no pool ou os servidores Standard Edition nos quais o roteamento baseado em localização do aplicativo de conferência foi habilitado.

> [!IMPORTANT]
> Os roteamentos baseados em local para conferências ou transferências de consultoria não serão impostos até que todos os servidores de front-end nos pools aplicáveis ou servidores padrão da edição sejam reiniciados. Se você definiu **-crítico** para **$true** nos cmdlets anteriores, os serviços do Skype for Business Server serão reiniciados imediatamente. Se você não quiser que esses serviços reiniciem imediatamente, defina **-** os **como $false** por enquanto e, em seguida, use **set-CsServerApplication** para alterar **-Critical** para **$true** mais tarde, após a reinicialização dos serviços.

Depois que o roteamento baseado em localização do aplicativo de conferência tiver sido habilitado com êxito e todos os servidores aplicáveis forem reiniciados, todas as conferências organizadas por usuários do Skype for Business habilitados para roteamento baseado em local serão monitoradas para evitar Desvio de chamada PSTN


