---
title: Planejar chamadas de emergência, endereços de emergência, roteamento de chamadas de emergência, chamadas de emergência dinâmicas
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
- Direct Routing
description: Saiba mais sobre chamadas de emergência, incluindo informações sobre endereços de emergência, roteamento de chamadas de emergência e chamadas de emergência dinâmicas.
ms.openlocfilehash: b97a14310014ea2e8271ee54f3bd6e777afa4d57
ms.sourcegitcommit: 021c86bf579e315f15815dcddf232a0c651cbf6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615831"
---
# <a name="manage-emergency-calling"></a>Gerenciar chamadas de emergência

Este artigo descreve os conceitos que você precisará saber para gerenciar as chamadas de emergência--ele inclui informações sobre endereços de emergência, endereços de emergência dinâmicos e roteamento de chamadas de emergência. Este artigo usa a seguinte terminologia:

- **Endereço de emergência** -um endereço cívico--o endereço físico ou da rua de um local de negócios para a sua organização.

  Por exemplo, o endereço *12345 residencial do Norte, Redmond, WA 98052* é usado para direcionar chamadas de emergência para as autoridades de expedição adequadas e para ajudar a localizar o chamador de emergência.

- **Lugar** -geralmente um número de andar, prédio, asa ou número de escritório. O local está associado a um endereço de emergência para dar um local mais exato dentro de um edifício. Você pode ter um número ilimitado de locais associados a um endereço de emergência. Por exemplo, se a sua organização tiver vários edifícios, talvez você queira incluir informações de local para cada prédio e para cada andar dentro de cada edifício.  

- **Local de emergência** -um local é um endereço cívico--com um lugar opcional. Se a sua empresa tiver mais de um local físico, é provável que você precise de mais de um local de emergência. 

  Quando você cria um endereço de emergência, um ID de local exclusivo é criado automaticamente para esse endereço.  Se você adicionar um local a um endereço de emergência-por exemplo, se você adicionar uma elevação a um endereço de construção--uma ID de local será criada para a combinação do endereço de emergência e local.  Neste exemplo, haverá duas IDs de localização: uma para o endereço cívico; um para o endereço cívico associado e o local associado.

  Quando você atribui um local de emergência a um usuário ou site, essa ID de local exclusivo associada ao usuário ou ao site.

- **Endereço cadastrado** -um endereço de emergência atribuído a cada usuário do plano de chamada; às vezes, ele é chamado de endereço de emergência estático ou endereço do registro.  (Os endereços registrados não se aplicam a usuários de roteamento direto.)

Você cria endereços de emergência para usuários do plano de chamada usando o centro de administração do teams.  

>[!Note]
>Há algumas diferenças em como você gerencia as chamadas de emergência dependendo se você estiver usando planos de chamada do sistema telefônico ou roteamento direto do sistema de telefonia para sua conectividade PSTN. Essas considerações são descritas em todo este artigo.

## <a name="emergency-address-validation"></a>Validação de endereço de emergência

Para atribuir um endereço de emergência a um usuário ou a um identificador de rede, você deve certificar-se de que o endereço de emergência esteja marcado como "validado".  A validação de endereço garante que o endereço seja legítimo e que ele não possa ser modificado após a atribuição. 

Se você definir um endereço de emergência usando o recurso de pesquisa do mapa de endereços no centro de administração do Teams, o endereço será automaticamente marcado como validado. Não é possível modificar um endereço de emergência validado. Portanto, se o formato ou representação do endereço mudar, você deverá criar um novo endereço com o formato atualizado.


## <a name="emergency-address-geo-codes"></a>Códigos de localização de endereço de emergência

Cada endereço de emergência pode ter um código geográfico (Latitude e longitude) associado a ele. Esses códigos geográficos são usados em alguns países para ajudar no roteamento de chamadas de emergência com locais dinâmicos. 

Se você definir um endereço de emergência usando o recurso de pesquisa mapa de endereços no centro de administração do Teams, o código geográfico será automaticamente associado a um endereço de emergência. Você também pode associar códigos geográficos a um endereço se definir o endereço usando o PowerShell. No entanto, a Microsoft recomenda que você crie endereços de emergência para o plano de chamadas usando o recurso de pesquisa de mapa no centro de administração do Teams, o que garante que os endereços sejam formatados, validados e tenham os códigos geográficos adequados.  

>[!Important]
>Para atribuir um local de emergência a um identificador de rede para chamadas de emergência dinâmicas, o endereço de emergência deve conter um código geográfica apropriado.


## <a name="considerations-for-calling-plans"></a>Considerações para planos de chamada

Para descobrir se os planos de chamada estão disponíveis na sua área, consulte [disponibilidade de país e região para planos de chamada](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).


### <a name="emergency-call-enablement"></a>Habilitação de chamadas de emergência

Cada usuário do plano de chamada é automaticamente habilitado para chamadas de emergência e precisa ter um endereço de emergência registrado associado ao número de telefone atribuído a ele. 

Quando o local deve estar associado ao número de telefone, depende do país/região:

- Nos Estados Unidos e no Canadá, por exemplo, uma localização de emergência é necessária quando um número é atribuído a um usuário.

- Para outros países, como na Europa, Oriente Médio e África (EMEA), é preciso um local de emergência quando você recebe o número de telefone do Office 365 ou quando ele é transferido de outro provedor de serviços ou operadora.

### <a name="dynamic-emergency-calling"></a>Chamadas de emergência dinâmicas

Chamadas de emergência dinâmicas para planos de chamada da Microsoft fornecem a funcionalidade de configurar e rotear chamadas de emergência com base na localização atual do cliente da equipe. A capacidade de direcionar o roteamento automático para o ponto de resposta de segurança pública adequado (PSAP) ou notificar a equipe de suporte técnico varia de acordo com o país de uso do usuário do teams.  

No momento, somente os usuários do plano de chamada nos Estados Unidos podem aproveitar locais dinâmicos para direcionar as chamadas de emergência da seguinte maneira:

- Se um cliente do teams para um plano de chamadas dos Estados Unidos usuários adquirem dinamicamente um endereço de emergência nos Estados Unidos, esse endereço será usado para roteamento de emergência em vez do endereço cadastrado, e a chamada será automaticamente roteada para o PSAP na área de serviço do endereço.

- Se um cliente do teams para um usuário do plano de chamadas do Brasil não adquirir dinamicamente um endereço de emergência nos Estados Unidos, o endereço de emergência registrado será usado para ajudar a tela e a encaminhar a chamada. No entanto, a chamada será filtrada para determinar se um endereço atualizado é necessário antes de conectar o chamador ao PSAP apropriado.

Nos Estados Unidos, você deve configurar o endereço cívico que faz parte dos locais de emergência atribuídos a identificadores de rede, e inclui os códigos geográficos associados. Para obter mais informações, consulte [planejar e configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md).


### <a name="emergency-call-routing"></a>Encaminhamento de chamadas de emergência

Quando um plano de chamada de equipe faz a discagem de um número de emergência, a chamada é roteada para o PSAP depende do seguinte:

- Se o endereço de emergência é determinado dinamicamente pelo cliente do teams.

- Se o endereço de emergência é o endereço cadastrado associado ao número de telefone do usuário.

- A rede de chamadas de emergência do país.

  **Nos Estados Unidos:**

  - Se um cliente do teams estiver localizado em um local de emergência dinâmico definido pelo locatário, as chamadas de emergência desse cliente serão roteadas automaticamente para o PSAP que está servindo essa localização geográfica. 

  - Se um cliente do Teams não estiver localizado em um local de emergência dinâmico definido pelo locatário, as chamadas de emergência desse cliente serão filtradas por um centro de chamadas nacionais para determinar a localização do chamador antes de transferir a chamada para o PSAP que está servindo dessa localização geográfica.

  - Se um chamador de emergência não conseguir atualizar o local de emergência para o centro de triagem, a chamada será transferida para o PSAP que está servindo o endereço cadastrado do chamador.

  **No Canadá, na Irlanda e no Reino Unido, as**chamadas de emergência são primeiramente reconectadas para determinar a localização atual do usuário antes de conectar a chamada ao centro de expedição apropriado. 

  **Na França, na Alemanha e na Espanha**, as chamadas de emergência são roteadas diretamente para o PSAP que está servindo o endereço de emergência associado ao número, independentemente da localização do chamador.

  **Nos Países Baixos**, as chamadas de emergência são roteadas diretamente para o PSAP para o código de área local do número, independentemente da localização do chamador.

  **Na Austrália**, os endereços de emergência são configurados e roteados pelo parceiro da operadora.

  **No Japão**, não há suporte para chamadas de emergência.


Para obter mais informações, consulte:

- [Planos de chamadas](calling-plan-landing-page.md)

- [Diferentes tipos de números de telefone utilizados para Planos de Chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [Termos e condições da chamada de emergência](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a>Considerações para roteamento direto

Se os planos de chamada não estiverem disponíveis na sua área ou se você quiser manter sua operadora existente, considere [Roteamento direto](direct-routing-landing-page.md). Para obter mais informações, consulte [Configurar o roteamento direto](direct-routing-configure.md) e [gerenciar as políticas de roteamento de chamadas de emergência](manage-emergency-call-routing-policies.md).

### <a name="emergency-call-enablement-and-configuration"></a>Ativação e configuração de chamadas de emergência

Você deve definir políticas de chamadas de emergência para usuários de roteamento direto usando o TeamsEmergencyCallRoutingPolicy para definir números de emergência e seus destinos de roteamento associados. (Observe que locais de emergência registrados não são compatíveis com usuários de roteamento direto.)

Você pode atribuir um TeamsEmergencyCallRoutingPolicy a uma conta de usuário de roteamento direto do Teams, a um site de rede ou a ambos. Quando um cliente de equipes iniciar ou alterar uma conexão de rede, o Teams executará uma pesquisa do site de rede onde o cliente está localizado da seguinte maneira:

- Se um TeamsEmergencyCallRoutingPolicy estiver associado ao site, a política do site será usada para configurar as chamadas de emergência.

- Se não houver nenhum TeamsEmergencyCallRoutingPolicy associado ao site, ou se o cliente estiver conectado a um site não definido, o TeamsEmergencyCallRoutingPolicy associado à conta de usuário será usado para configurar a chamada de emergência. 

- Se o cliente do Teams não conseguir obter um TeamsEmergencyCallRoutingPolicy, o usuário não está habilitado para chamadas de emergência.

### <a name="dynamic-emergency-calling"></a>Chamadas de emergência dinâmicas

Os clientes do teams para usuários de roteamento direto podem adquirir um endereço de emergência dinâmico, que pode ser usado para direcionar chamadas dinamicamente com base na localização do chamador. Para obter mais informações, consulte [Configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing"></a>Encaminhamento de chamadas de emergência

O TeamsEmergencyCallRoutingPolicy faz referência a um uso de PSTN online, que deve ter a configuração de roteamento direto apropriada para direcionar adequadamente as chamadas de emergência para o (s) gateways PSTN apropriados (s). Em particular, você deve garantir que há um OnlineVoiceRoute para a cadeia de caracteres de discagem de emergência. Para obter mais informações, consulte [Configurar o roteamento direto](direct-routing-configure.md#configure-voice-routing). 

(Observação: no Skype for Business Server, o número de emergência era prefixado com "+", que exigia que uma rota de voz fosse definida para corresponder "+ 911" por exemplo. Os clientes do Teams não precedem o "+" com números de emergência.)

A capacidade de rotear dinamicamente as chamadas de emergência para usuários de roteamento direto varia de acordo com a rede de chamadas de emergência dentro de um determinado país. Há duas soluções disponíveis:

- Provedores de serviços de roteamento de emergência (somente nos EUA) 
- Aplicativos de gateway do número de identificação de localização de emergência (ELIN)

#### <a name="emergency-routing-service-providers"></a>Provedores de serviços de roteamento de emergência

Nos Estados Unidos, há vários provedores de serviços de roteamento de emergência certificados (ERSPs) que podem rotear automaticamente as chamadas de emergência com base na localização do chamador.

- Se um provedor de serviços de roteamento de emergência estiver integrado a uma implantação de roteamento direto, as chamadas de emergência com um local adquirido dinamicamente serão automaticamente roteadas para o ponto de resposta de segurança pública (PSAP) que está servindo essa localização.

-  As chamadas de emergência sem um local adquirido dinamicamente são organizadas em primeiro lugar para determinar a localização atual do usuário antes de conectar a chamada ao centro de expedição apropriado com base no local atualizado.

Para obter mais informações, consulte [controladores de borda de sessão certificados para roteamento direto](direct-routing-border-controllers.md).


#### <a name="emergency-location-identification-number-elin-applications"></a>Aplicativos número de identificação de localização de emergência (ELIN)

Os controladores de borda de sessão (SBCs) podem incluir aplicativos de número de identificação de localização (ELIN) de emergência. Se um aplicativo ELIN do SBC estiver integrado a uma implantação de roteamento direto, você deve configurar os endereços de emergência e os números de telefone associados no aplicativo ELIN e, em seguida, carregar os registros ELIN para o banco de dados de chamadas de emergência na respectiva PSTN .  Locais de emergência do teams com um identificador ELIN devem coincidir com os no aplicativo ELIN.

Quando uma chamada de emergência com um local adquirido dinamicamente é roteada para o SBC apropriado, o aplicativo ELIN:

- Analisa o local de emergência do chamador.
- Corresponde à localização de um registro ELIN.
- Substitui o número do chamador de emergência pelo número de telefone ELIN.
- Roteia a chamada para o PSAP que está servindo essa localização e, em seguida, os despachos obtêm o local do registro ELIN carregado.

Durante uma chamada de volta para o número de emergência, o aplicativo ELIN fará a substituição do número chamado chamado para a do chamador de emergência original. 

Para obter mais informações, consulte [controladores de borda de sessão certificados para roteamento direto](direct-routing-border-controllers.md).


## <a name="security-desk-notification"></a>Notificação de segurança técnica

A notificação do Security Desk está disponível com planos de chamadas da Microsoft e direcionamento direto do sistema de telefonia.

Use o TeamsEmergencyCallingPolicy para configurar quem deve ser notificado durante uma chamada de emergência e como eles são notificados: somente chat, em conferência e mudo ou em conferência e mudo, mas com a capacidade de ativar mudo.  Você também pode especificar um número PSTN externo de um usuário ou grupo para chamar e ingressar na chamada de emergência. 

Um TeamsEmergencyCallingPolicy pode ser concedido a uma conta de usuário do Team, atribuída a um site de rede ou a ambos.  Quando um cliente de equipes iniciar ou alterar uma conexão de rede, o Teams executará uma pesquisa do site de rede onde o cliente está localizado:

- Se um TeamsEmergencyCallingPolicy estiver associado a um site de rede, a política do site será usada para configurar a notificação do Security Desk.

- Se não houver nenhum TeamsEmergencyCallingPolicy associado ao site, ou se o cliente estiver conectado em um site indefinido, o TeamsEmergencyCallingPolicy associado à conta de usuário será usado para configurar a notificação de segurança do escritório.  

- Se o cliente do Teams não conseguir obter um TeamsEmergencyCallingPolicy, o usuário não está habilitado para a notificação de segurança técnica.

Durante uma chamada de emergência, uma mesa de segurança é reconversada na chamada, e a experiência do usuário de segurança é controlada com base no TeamsEmergencyCallingPolicy. Um chat em grupo é iniciado com cada membro do Security Desk, e o local do chamador de emergência é compartilhado por meio de uma notificação de mensagem importante.  Se uma opção de conferência estiver configurada como parte da política, cada usuário do Security Desk será chamado também como parte da conferência.

    
## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar políticas de chamadas de emergência](manage-emergency-calling-policies.md)
- [Gerenciar políticas de roteamento de chamadas de emergência](manage-emergency-call-routing-policies.md)
- [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)
- [Atribuir ou alterar um local de emergência para o usuário](assign-change-emergency-location-user.md)
- [Planejar e configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md)