---
title: Roteamento com base no local  para conferência no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 10/13/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: Planejamento de roteamento baseado no local para conferências no Skype para Business Server Enterprise Voice, incluindo com consultoria transferências de chamada.
ms.openlocfilehash: 4cfa76e10ed0107c1dc1fe4c1759a89536529ada
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server-2015"></a>Roteamento com base no local  para conferência no Skype for Business Server 2015
 
Planejamento de roteamento baseado no local para conferências no Skype para Business Server Enterprise Voice, incluindo com consultoria transferências de chamada.
  
Roteamento baseado em local torna possível restringir o roteamento de chamadas entre os pontos de extremidade de VoIP e pontos de extremidade PSTN com base na localização dos participantes na chamada. Roteamento de conferência baseados em local permite impor regras de roteamento baseados em local no contorno de tarifa de reuniões (isto é, conferências) para evitar a PSTN. O aplicativo monitora uma conferência ativa e impõe restrições de roteamento baseados em local baseadas no local de usuários participantes. Além disso, o serviço de roteamento com base no local para o aplicativo de conferência permite a aplicação de restrições de roteamento baseado no local para transferências de consultas envolvendo os pontos de extremidade PSTN.
  
Fornece o aplicativo de conferência de roteamento baseada no local para Skype para conferências de negócios o desvio de um mecanismo para prevenção das tarifas PSTN. O aplicativo monitora conferência ativa e impõe restrições de roteamento baseado no local com base na localização do Skype para usuários corporativos que participam. 
  
O aplicativo de conferência de roteamento baseados em local determina se o roteamento baseado no local está para ser impostas em um Skype para reunião de negócios se os critérios a seguir forem atendidos:
  
- O organizador da reunião está habilitado para roteamento baseado no local. Restrições de roteamento baseados em local serão aplicadas apenas para conferências que são organizadas por usuários habilitados para roteamento baseado no local.
    
- Pelo menos um participante da reunião é um ponto de extremidade PSTN. Restrições de roteamento baseados em local são aplicáveis somente para conferências que incluem os pontos de extremidade PSTN.
    
- O local da rede onde o gateway PSTN usado para fazer a ligação da conferência com o PSTN está localizado, bem como os locais de rede, de onde os organizadores e os participantes estão se conectando. 
    
O serviço de roteamento com base no local para o aplicativo de conferência impede a participação de Skype para usuários empresariais e pontos de extremidade PSTN dos sites de rede diferente para a mesma conferência. Se o organizador de reunião estiver habilitado para roteamento baseado em local, o aplicativo de conferência impõe as seguintes restrições:
  
- Os pontos de extremidade que podem ingressar em uma Skype para reunião de negócios dependem os pontos de extremidade que já ingressou na conferência, e essa restrição ajusta como pontos de extremidade unidas deixe e novos pontos de extremidade ingressar na conferência. Se os organizadores e os participantes estão ingressando um Skype para reunião de negócios do mesmo site de rede, e em seguida, um ponto de extremidade PSTN, outro participante do mesmo local de rede, outro participante de um site de rede diferente ou um participante de um site de rede desconhecido são permitidos para ingressar.
    
- Se os organizadores e os participantes estiverem ingressando na reunião de locais de rede diferentes ou desconhecidos, um ponto de extremidade PSTN não terá autorização para participar da reunião se a chamada PSTN ingressar de um tronco SIP habilitado para Roteamento Baseado na Localização.
    
- Se os organizadores e participantes todos estão participando da reunião do mesmo local de rede e há participantes para ingressar na reunião mesma da PSTN, um Skype para ponto de extremidade de negócios de um site de rede diferente não é permitida para ingressar na reunião.
    
Essas restrições de roteamento baseados em local da conferência estão resumidas na tabela a seguir. 
  
| |
|**Um ou mais usuários em uma conferência em qualquer ponto**|**Um ou mais usuários permitido para ingressar na conferência**|**Um ou mais usuários não são permitido para ingressar na conferência**|
|:-----|:-----|:-----|
|Skype para negócios VoIP (s) de cliente de um site de rede único  <br/> |Skype para usuário de cliente VoIP de negócios do mesmo local de rede  <br/> Skype para usuário de cliente VoIP de negócios de um site de rede diferente  <br/> Skype para usuário de cliente VoIP de negócios de um site de rede desconhecido  <br/> Skype federado para o usuário do cliente de VoIP de negócios  <br/> Usuário ingressando a partir de um ponto de extremidade PSTN  <br/> |Nenhum  <br/> |
|Skype para negócios VoIP (s) de cliente de um site de rede desconhecido  <br/> |Skype para usuário de cliente VoIP de negócios em qualquer site  <br/> Skype para usuário de cliente VoIP de negócios de um site desconhecido  <br/> Skype federado para o usuário do cliente de VoIP de negócios  <br/> |Usuário ingressando por meio de um ponto de extremidade PSTN  <br/> |
|Skype para usuários do cliente VoIP de negócios dos sites de rede diferente  <br/> |Skype para usuário de cliente VoIP de negócios de qualquer site de rede  <br/> Skype para usuário de cliente VoIP de negócios de um site de rede desconhecido  <br/> Skype federado para o usuário do cliente de VoIP de negócios  <br/> |Usuário ingressando por meio de um ponto de extremidade PSTN  <br/> |
|Skype para usuários que ingressando a partir de um ponto de extremidade PSTN e VoIP de negócios (s) de cliente de um site de rede único  <br/> |Skype para usuário de cliente VoIP de negócios do mesmo local de rede  <br/> |Skype para usuário de cliente VoIP de negócios de um site de rede diferente  <br/> Skype para usuário de cliente VoIP de negócios de um site de rede desconhecido  <br/> Skype federado para o usuário do cliente de VoIP de negócios  <br/> |
   
Estas são as características adicionais de roteamento com base no local para o aplicativo de conferência:
  
- Quando um usuário não tem permissão para ingressar em uma conferência dada restrições de roteamento baseados em local, a chamada para a conferência será rejeitada e o Skype para o cliente de negócios será o relatório que a chamada não foi concluída ou foi finalizada.
    
- Uma PSTN endpoint ingressar em que uma conferência com aplicações de roteamento baseado no local não serão restrita para ingressar na conferência independentemente de seu estado, se o ponto de extremidade ingressa através de um tronco que não está habilitado para roteamento baseado no local.
    
- Um sistema PBX conectado a um servidor de mediação por um tronco SIP que não saída chamadas para o PSTN terá a mesma aplicações como Skype para usuários comerciais localizados no mesmo site de rede onde o tronco SIP está definido. Por exemplo, um ponto de extremidade PSTN poderão ingressar em uma conferência com um usuário de PBX e um Skype para o usuário de negócios se estiverem localizados no mesmo site de rede; Caso contrário, o ponto de extremidade PSTN não poderão ingressar na conferência, se o usuário de PBX estiver em um site de rede diferente que o Skype para o usuário de negócios.
    
> [!NOTE]
> Com a Atualização Cumulativa 4 do Skype for Business, é preciso observar o comportamento apresentado na tabela a seguir: 
  
|**Usuário**|**Outra parte**|**Ação**|**Resultado**|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |O Skype for Business Mobile está em uma chamada PSTN. O Skype for Business Mobile escalona a chamada para um CAA (Atendedor Automático de Conferência).  <br/> |A chamada é bloqueada com a mensagem de erro apropriada.  <br/> |
|Skype for Business Mobile  <br/> |Cliente ou usuário federado do Skype for Business  <br/> |O cliente ou um usuário federado é em uma chamada VoIP para um Skype para usuário Business Mobile Location-Based roteamento e qualquer uma das partes for escalonada para uma CAA.  <br/> |A chamada escalonada é bloqueada com a mensagem de erro apropriada.  <br/> |
   
## <a name="consultative-call-transfers"></a>Transferências de chamada consultiva

Além das aplicando roteamento baseado no local para Skype para reuniões de negócios, o serviço de roteamento com base no local para o aplicativo de conferência impõe restrições de roteamento baseados em local nas transferências de chamada com consultoria que saída aos pontos de extremidade PSTN. Uma transferência de chamada consultiva é estabelecida entre duas partes em que uma delas transfere a chamada para um novo usuário. Por exemplo, um ponto de extremidade PSTN chama o usuário (Skype para o receptor de negócios). O usuário A determina que o usuário PSTN deve ser encaminhado para o usuário B (Skype para usuário comercial). O usuário A coloca a chamada com o usuário PSTN em espera e liga para o usuário B. O usuário B concorda em falar com o usuário PSTN. O usuário A transfere a chamada espera para o usuário B.
  
**Fluxo de chamadas de transferência com consultoria chamada**

![Diagrama de roteamento baseado em local para conferência](../../media/LocationBasedRoutingForConferencing.jpg)
  
Quando um usuário habilitado para roteamento baseado em local inicia uma transferência com consultoria chamada de um ponto de extremidade PSTN (conforme mostrado na figura anterior), isso cria duas chamadas ativas, uma chamada entre o usuário PSTN e Skype para o usuário de negócios A e o outro entre Skype para Skype para comercial do usuário B. o seguinte comportamento e usuário corporativos é imposto pelo roteamento baseado no local para o aplicativo de conferência:
  
- Se o tronco SIP roteamento PSTN chamar está autorizado a roteará a chamada PSTN para o site de rede onde Skype para o usuário B de negócios (ou seja, o destino de transferência) está localizado e, em seguida, a transferência de chamada será permitida; Caso contrário, a transferência com consultoria chamada será bloqueada. Essa autorização é executada com base no local da parte transferidos sendo no mesmo site do tronco SIP que está roteando a chamada ativa para o ponto de extremidade PSTN. 
    
- Se o tronco SIP roteando a chamada PSTN de entrada não estará autorizado para rotear chamadas para o site de rede em que o participante transferido (Skype para o usuário de negócios B) está localizado ou o participante transferido está localizado em um site de rede desconhecido, em seguida, a chamada com consultoria transferir para o ponto de extremidade PSTN (isto é, alvo de transferência de chamadas) será bloqueado.
    
A tabela a seguir descreve como baseados em local roteamento restrições são aplicadas pelo roteamento baseados em local do aplicativo de conferência para as transferências de chamada com consultoria. Embora os pontos de extremidade PBX não estejam associados diretamente a um local de rede, o tronco SIP ao qual o PBX está conectado pode ser atribuído a um local de rede. Portanto, o ponto de extremidade PBX pode ser indiretamente associado a um local de rede.
  

|**Site de rede da parte chamada transferida**|**Site de rede de destino de transferência de chamada**|**Comportamento**|
|:-----|:-----|:-----|
|Ponto de extremidade PSTN  <br/> |Skype para usuário de negócios no mesmo site de rede (ou seja, o site 1)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PSTN  <br/> |Skype para usuário corporativos em sites de rede diferente (ou seja, o site 2)  <br/> |A transferência consultiva não será permitida  <br/> |
|Ponto de extremidade PSTN  <br/> |Skype para usuário de negócios em um site de rede desconhecido  <br/> |A transferência consultiva não será permitida  <br/> |
|Ponto de extremidade PSTN  <br/> |Skype federado para o usuário de negócios  <br/> |A transferência consultiva não será permitida  <br/> |
|Ponto de extremidade PSTN  <br/> |Ponto de extremidade do PBX no mesmo local (isto é, local 1)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PSTN  <br/> |Ponto de extremidade PBX em locais diferentes (isto é, local 2)  <br/> |A transferência consultiva não será permitida  <br/> |
|Ponto de extremidade do PBX no mesmo local (isto é, local 1)  <br/> |Ponto de extremidade PSTN  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade do PBX em locais diferentes (i.e. local 2)  <br/> |Ponto de extremidade PSTN  <br/> |A transferência consultiva não será permitida  <br/> |
|Ponto de extremidade PBX em qualquer local  <br/> |Skype para usuário de negócios no mesmo site de rede (ou seja, o site 1)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PBX em qualquer local  <br/> |Skype para usuário corporativos em sites de rede diferente (ou seja, o site 2)  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PBX em qualquer local  <br/> |Skype para usuário de negócios em um site de rede desconhecido  <br/> |A transferência consultiva será permitida  <br/> |
|Ponto de extremidade PBX em qualquer local  <br/> |Skype federado para o usuário de negócios  <br/> |A transferência consultiva será permitida  <br/> |
   
## <a name="requirements"></a>Requisitos

O serviço de roteamento com base no local para o aplicativo de conferência exige que significa Skype para Business Server ou o Lync Server 2013 2 de atualização cumulativa é implantado em todos os pools de front-end e servidores Standard Edition em sua topologia. Se essas versões de servidor não estiverem instaladas em alguns servidores em sua topologia, restrições de roteamento baseado no local não podem ser totalmente imposta nas reuniões e com consultoria transferências de chamada.
  
A tabela a seguir identifica a combinação das funções de servidor e de versões que suportam o roteamento baseado no local.
  

|**Versão do Pool de front-end**|**Versão do servidor de mediação**|**Compatível**|
|:-----|:-----|:-----|
|Skype para Business Server ou o Lync Server 2013 atualização cumulativa 2  <br/> |Skype para Business Server ou o Lync Server 2013 atualização cumulativa 2  <br/> |Sim  <br/> |
|Atualização Cumulativa 2 do Lync Server 2013  <br/> |Atualização Cumulativa 1 do Lync Server 2013  <br/> |Não  <br/> |
|Atualização Cumulativa 2 do Lync Server 2013  <br/> |Lync Server 2010  <br/> |Não  <br/> |
|Atualização Cumulativa 2 do Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |Não  <br/> |
|Atualização Cumulativa 1 do Lync Server 2013  <br/> |Qualquer  <br/> |Não  <br/> |
|Lync Server 2010  <br/> |Qualquer  <br/> |Não  <br/> |
|Office Communications Server 2007 R2  <br/> |Qualquer  <br/> |Não  <br/> |
   
## <a name="configuration-of-location-based-routing-for-conferencing"></a>Configuração de roteamento baseado na localização de conferência

O serviço de roteamento com base no local para o aplicativo de conferência depende da configuração do roteamento baseado no local. Estas são as principais configurações: 
  
- O local dos participantes que ingressam em uma reunião é determinado com base em seus locais de rede. Um site de rede e seus subredes associadas devem ser definidas Skype para Business Server para impor o roteamento baseado no local.
    
- Para impor o roteamento com base no local de reuniões, Skype para participantes de negócios deve ser habilitado para roteamento baseado no local.
    
- Para impor o roteamento com base no local de pontos de extremidade PSTN participar de reuniões, o tronco SIP usado para conectar os pontos de extremidade PSTN deve ser configurado para roteamento baseado no local.
    
## <a name="enabling-the-location-based-routing-for-conferencing"></a>Habilitando o roteamento baseado no local para conferência

O serviço de roteamento com base no local para o aplicativo de conferência está desabilitado por padrão. Antes de habilitá-lo, determine a prioridade certa para atribuir a ele. Para determinar essa prioridade, execute o seguinte cmdlet em Skype do Shell de gerenciamento do servidor de negócios:
  
Get-CsServerApplication-Identity Service: Registrar:<Pool FQDN>nesse cmdlet, \<FQDN do Pool\> é o pool no qual o serviço de roteamento com base no local para o aplicativo de conferência deve ser habilitado.
  
Esse cmdlet retornará a lista dos aplicativos hospedados pelo Skype para Business Server e o valor de prioridade para cada um deles. O serviço de roteamento com base no local para o aplicativo de conferência deve ser atribuído a um valor de prioridade maior do que o aplicativo "UdcAgent" e menor do que os aplicativos "DefaultRouting", "ExumRouting" e "OutboundRouting". É recomendável que você atribua o roteamento baseado no local para o aplicativo de conferência um valor de prioridade que é um ponto de maior que o valor de prioridade do aplicativo "UdcAgent".
  
Por exemplo, se o aplicativo "UdcAgent" tiver um valor de prioridade de "2", o aplicativo de "DefaultRouting" possui um valor de prioridade de "8", o aplicativo "ExumRouting" possui um valor de prioridade de "9" e o aplicativo "OutboundRouting" possui um valor de prioridade de "10", em seguida Você deve atribuir um valor de prioridade de "3" para o serviço de roteamento com base no local para o aplicativo de conferência. Isso seria colocar a prioridade dos aplicativos na seguinte ordem: outros aplicativos (prioridades: 0 e 1), "UdcAgent" (prioridade: 2), o aplicativo de conferência de roteamento baseados em local (prioridade: 3), outros aplicativos (prioridades: 4 a 8), " DefaultRouting"(prioridade: 9),"ExumRouting"(prioridade: 10) e"OutboundRouting"(prioridade: 11).
  
Após localizar o valor de prioridade correto para o serviço de roteamento com base no local para o aplicativo de conferência, digite o seguinte cmdlet para cada pool de front-end ou servidor Standard Edition que hospeda usuários habilitados para o roteamento baseado no local:
  
New-CsServerApplication-Identity Service: Registrar:<Pool FQDN>/LBRouting-prioridade <Application Priority> -habilitado $true-crítico $true - Uri http://www.microsoft.com/LCS/LBRoutingFor exemplo:
  
New-CsServerApplication-Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting-prioridade 3 - $true Enabled-crítico $true - Uri http://www.microsoft.com/LCS/LBRoutingAfter usando este cmdlet, reiniciar todos os servidores de Front-End no pool ou os servidores Standard Edition onde o Roteamento baseado no local para o aplicativo de conferência tiver sido habilitado.
  
> [!IMPORTANT]
> Aplicações de roteamento baseados em local para conferências ou transferências de consultas não são impostas até que todos os servidores Front-End nos pools aplicáveis ou os servidores Standard Edition são reiniciados. Se você definir **-crítico** para **$true** os cmdlets anteriores, seu Skype para serviços de Business Server será reiniciado imediatamente. Se você não quiser que esses serviços para reiniciar imediatamente, defina **-crítico** para **$false** para agora e, em seguida, utilize **Set-CsServerApplication** , para alterar **-crítico** para **$true** mais tarde, depois que os serviços foram reiniciados.
  
Depois que o serviço de roteamento com base no local para o aplicativo de conferência tiver sido habilitado com sucesso e todos os servidores aplicáveis tem sido reiniciados, todas as conferências organizadas por Skype para usuários comerciais habilitados para roteamento baseado em local serão monitoradas para impedir O desvio de tarifas PSTN
  

