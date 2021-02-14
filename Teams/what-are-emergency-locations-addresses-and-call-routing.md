---
title: Planejar e gerenciar as chamada de emergência
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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
- seo-marvel-mar2020
description: Saiba mais sobre chamadas de emergência, incluindo informações sobre endereços de emergência, roteamento de chamadas de emergência e chamadas de emergência dinâmicas.
ms.openlocfilehash: 4f2ef86d05537a147a459fd6bc121f0680b534bd
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031597"
---
# <a name="manage-emergency-calling"></a>Gerenciar chamada de emergência

Este artigo descreve os conceitos que você precisará conhecer para gerenciar chamadas de emergência, incluindo informações sobre endereços de emergência, endereços de emergência dinâmicos e roteamento &mdash; de chamadas de emergência. Este artigo usa a seguinte terminologia:

- **Endereço de** emergência – Endereço cívico o endereço físico ou de &mdash; rua de um local de negócios para sua organização.

  Por exemplo, o endereço  *12345 North Main Street, Redmond, WA 98052* é usado para encaminhar chamadas de emergência para as autoridades de expedição apropriadas e auxiliar na localização do chamador de emergência.

- **Local** - Normalmente um número de escritório, prédio, prédio ou ala. O local está associado a um endereço de emergência para dar um local mais exato dentro de um prédio. Você pode ter um número ilimitado de locais associados a um endereço de emergência. Por exemplo, se sua organização tiver vários edifícios, talvez você queira incluir informações de local para cada prédio e para cada andar dentro de cada prédio.  

- **Local de emergência** : um local é um endereço cívico &mdash; com um local opcional. Se sua empresa tiver mais de um local físico, é provável que você precise de mais de um local de emergência. 

  Quando você cria um endereço de emergência, uma ID de local exclusiva é criada automaticamente para esse endereço.  Se você adicionar um local a um endereço de emergência, por exemplo, se você adicionar um andar a um endereço de construção, uma ID de local será criada para a combinação do endereço e do &mdash; &mdash; local de emergência.  Neste exemplo, haverá duas IDs de localização: uma para o endereço cívico; um para o endereço cívico associado e o local associado.

  Quando você atribui um local de emergência a um usuário ou site, é essa ID de local exclusiva associada ao usuário ou site.

- **Endereço registrado** – um endereço de emergência atribuído a cada usuário do Plano de Chamada; às vezes é chamado de endereço de emergência estático ou endereço de registro.  (Os endereços registrados não se aplicam aos usuários de Roteamento Direto.)

Você cria endereços de emergência para usuários do Plano de Chamada usando o Centro de administração do Teams.  

>[!Note]
>Há algumas diferenças em como você gerencia chamadas de emergência, dependendo se você está usando planos de Chamada do Sistema de Telefonia ou Roteamento Direto do Sistema de Telefonia para sua conectividade PSTN. Essas considerações são descritas ao longo deste artigo.

## <a name="emergency-address-validation"></a>Validação de endereço de emergência

Para atribuir um endereço de emergência a um usuário ou a um identificador de rede, você deve garantir que o endereço de emergência seja marcado como "validado".  A validação de endereço garante que o endereço seja legítimo e que ele não possa ser modificado depois que ele for atribuído. 

Se você definir um endereço de emergência usando o recurso de pesquisa de mapa de endereços no Centro de administração do Teams, o endereço será marcado automaticamente como validado. Não é possível modificar um endereço de emergência validado. Portanto, se o formato ou a representação do endereço mudar, você deverá criar um novo endereço com o formato atualizado.


## <a name="emergency-address-geo-codes"></a>Códigos geo de endereço de emergência

Cada endereço de emergência pode ter um código geo (latitude e longitude) associado a ele. Esses códigos gráficos são usados em alguns países para ajudar a rotear chamadas de emergência com locais dinâmicos. 

Se você definir um endereço de emergência usando o recurso de pesquisa de mapa de endereços no Centro de administração do Teams, o código geo será automaticamente associado a um endereço de emergência. Você também pode associar códigos geodados a um endereço se definir o endereço usando o PowerShell. No entanto, a Microsoft recomenda que você crie endereços de emergência para o Plano de Chamada usando o recurso de pesquisa de mapa no Centro de administração do Teams, o que garantirá que os endereços sejam formatados, validados e tenham os códigos geo apropriados.  

>[!Important]
>Para atribuir um local de emergência a um identificador de rede para uma chamada de emergência dinâmica, o endereço de emergência deve conter um código geo apropriado.


## <a name="considerations-for-calling-plans"></a>Considerações sobre planos de chamada

Para descobrir se os Planos de Chamada estão disponíveis em sua área, consulte a disponibilidade de país e [região para Planos de Chamada.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)


### <a name="emergency-call-enablement"></a>Habilitar chamada de emergência

Cada usuário do Plano de Chamada é habilitado automaticamente para chamadas de emergência e é necessário ter um endereço de emergência registrado associado ao número de telefone atribuído. 

Quando o local deve estar associado ao número de telefone depende do país/região:

- Nos Estados Unidos e no Canadá, por exemplo, um local de emergência é necessário quando um número é atribuído a um usuário.

- Para outros países( como Na Europa, Oriente Médio e África ), um local de emergência é necessário quando você obter o número de telefone do Microsoft 365 ou do Office 365 ou quando ele for transferido de outro provedor de serviços ou operadora.

### <a name="dynamic-emergency-calling"></a>Chamada de emergência dinâmica

Chamadas de emergência dinâmicas para planos de Chamada da Microsoft oferece a capacidade de configurar e encaminhar chamadas de emergência com base na localização atual do cliente do Teams. A capacidade de fazer o roteamento automático para o PSAP (Ponto de Resposta de Segurança Pública) apropriado ou para notificar a equipe de segurança varia dependendo do país de uso do usuário do Teams.  

Para usuários do Plano de Chamada, o local dinâmico para roteamento de chamadas de emergência só tem suporte nos Estados Unidos da seguinte maneira. (Para obter informações sobre chamadas de emergência dinâmicas e Roteamento Direto, consulte [Considerações sobre Roteamento Direto.](#considerations-for-direct-routing)

- Se um cliente do Teams para um usuário do Plano de Chamada dos Estados Unidos adquirir dinamicamente um endereço de emergência nos Estados Unidos, esse endereço será usado para roteamento de emergência em vez do endereço registrado, e a chamada será roteada automaticamente para o PSAP na área de serviço do endereço.

- Se um cliente do Teams para um usuário do Plano de Chamada dos Estados Unidos não adquirir dinamicamente um endereço de emergência nos Estados Unidos, o endereço de emergência registrado será usado para ajudar a tela e encaminhar a chamada. No entanto, a chamada será tela para determinar se um endereço atualizado é necessário antes de conectar o chamador ao PSAP apropriado.

Nos Estados Unidos, você deve configurar o endereço cívico que faz parte dos locais de emergência atribuídos aos identificadores de rede e incluir os &mdash; códigos geodados associados. Para obter mais informações, consulte [Planejar e configurar uma chamada de emergência dinâmica.](configure-dynamic-emergency-calling.md)


### <a name="emergency-call-routing"></a>Roteamento de chamadas de emergência

Quando um usuário do Plano de Chamada do Teams disca um número de emergência, a forma como a chamada é roteada para o PSAP depende do seguinte:

- Se o endereço de emergência é determinado dinamicamente pelo cliente do Teams.

- Se o endereço de emergência é o endereço registrado associado ao número de telefone do usuário.

- A rede de chamada de emergência desse país.

  **Nos Estados Unidos:**

  - Se um cliente do Teams estiver localizado em um local de emergência dinâmico definido pelo locatário, as chamadas de emergência desse cliente serão roteados automaticamente para o PSAP que atende a esse local geográfico. 

  - Se um cliente do Teams não estiver localizado em um local de emergência dinâmico definido pelo locatário, as chamadas de emergência desse cliente serão monitoradas por um centro de chamadas nacional para determinar a localização do chamador antes de transferir a chamada para o PSAP que atende a esse local geográfico.

  - Se um chamador de emergência não conseguir atualizar seu local de emergência para o centro de seleção, a chamada será transferida para o PSAP que atende ao endereço registrado do chamador.

  **No Canadá, na Irlanda** e no Reino Unido, as chamadas de emergência são primeiramente teladas para determinar a localização atual do usuário antes de conectar a chamada ao centro de expedição apropriado. 

  **Na França, na Alemanha e** na Espanha, as chamadas de emergência são roteada diretamente para o PSAP que atende ao endereço de emergência associado ao número, independentemente da localização do chamador.

  **Na Holanda, as** chamadas de emergência são roteada diretamente para o PSAP para o código de área local do número, independentemente da localização do chamador.

  **Na Austrália,** os endereços de emergência são configurados e roteados pelo parceiro da operadora.

  **No Japão,** não há suporte para chamada de emergência.


Para obter mais informações, consulte:

- [Planos de Chamadas](calling-plan-landing-page.md)

- [Diferentes tipos de números de telefone utilizados para Planos de Chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [Termos e condições para chamadas de emergência](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a>Considerações sobre o Roteamento Direto

Se os Planos de Chamada não estão disponíveis em sua área ou se você deseja manter sua operadora existente, considere o [Roteamento Direto.](direct-routing-landing-page.md) Para obter mais informações, consulte [Configurar Roteamento Direto](direct-routing-configure.md) e Gerenciar políticas de roteamento [de chamadas de emergência.](manage-emergency-call-routing-policies.md)

### <a name="emergency-call-enablement-and-configuration"></a>Configuração e habilitação de chamada de emergência

Você deve definir políticas de chamadas de emergência para usuários de Roteamento Direto usando uma política de roteamento de chamadas de emergência do Teams (TeamsEmergencyCallRoutingPolicy) para definir números de emergência e seu destino de roteamento associado. (Observe que locais de emergência registrados não são suportados para usuários de Roteamento Direto.)

Você pode atribuir uma política de roteamento de chamada de emergência a uma conta de usuário de Roteamento Direto do Teams, um site de rede ou ambos. Quando um cliente do Teams inicia ou altera uma conexão de rede, o Teams realiza uma busca do site de rede onde o cliente está localizado da seguinte forma:

- Se uma política de roteamento de chamadas de emergência estiver associada ao site, a política de site será usada para configurar chamadas de emergência.

- Se não houver uma política de roteamento de chamadas de emergência associada ao site ou se o cliente estiver conectado em um site não definido, a política de roteamento de chamadas de emergência associada à conta de usuário será usada para configurar chamadas de emergência. 

- Se o cliente do Teams não conseguir obter uma política de roteamento de chamadas de emergência, o usuário não está habilitado para chamadas de emergência.

### <a name="dynamic-emergency-calling"></a>Chamada de emergência dinâmica

Os clientes do Teams para usuários de Roteamento Direto podem adquirir um endereço de emergência dinâmico, que pode ser usado para encaminhar chamadas dinamicamente com base na localização do chamador. Para obter mais informações, consulte [Configurar chamada de emergência dinâmica.](configure-dynamic-emergency-calling.md)

### <a name="emergency-call-routing"></a>Roteamento de chamadas de emergência

A política de roteamento de chamadas de emergência faz referência a um uso de PSTN online, que deve ter a configuração adequada de Roteamento Direto para encaminhar corretamente as chamadas de emergência para os gateways PSTN apropriados. Em particular, você deve garantir que haja um OnlineVoiceRoute para a cadeia de discagem de emergência. Para obter mais informações, consulte [Configurar Roteamento Direto.](direct-routing-configure.md) 

(Observação: os clientes do Teams antecipam o sinal "+" na frente de números de emergência de maneira semelhante à do cliente Skype for Business; ou seja, +911. Esse comportamento será modificado nos próximos meses para que as chamadas de emergência do Teams não enviem mais um "+" antes do número; ou seja, 911.)

A capacidade de rotear dinamicamente chamadas de emergência para usuários de Roteamento Direto varia dependendo da rede de chamadas de emergência em um determinado país. Há duas soluções disponíveis:

- Provedores de Serviços de Roteamento de Emergência (somente para os EUA) 
- Aplicativos de gateway ELIN (Número de Identificação de Localização de Emergência)

#### <a name="emergency-routing-service-providers"></a>Provedores de Serviços de Roteamento de Emergência

Nos Estados Unidos, há inúmeros ERSPs (Provedores de Serviços de Roteamento de Emergência) certificados que podem rotear automaticamente chamadas de emergência com base na localização do chamador.

- Se um Provedor de Serviços de Roteamento de Emergência estiver integrado a uma implantação de Roteamento Direto, as chamadas de emergência com um local adquirido dinamicamente serão automaticamente roteada para o PSAP (Ponto de Atendimento de Segurança Pública) que atende a esse local.

-  As chamadas de emergência sem um local adquirido dinamicamente são primeiramente teladas para determinar a localização atual do usuário antes de conectar a chamada ao centro de expedição apropriado com base no local atualizado.

Para obter mais informações, consulte [Controladores de Borda de Sessão certificados para Roteamento Direto.](direct-routing-border-controllers.md)


#### <a name="emergency-location-identification-number-elin-applications"></a>Aplicativos ELIN (Número de Identificação de Localização de Emergência)

Os Controladores de Borda de Sessão (SBCs) podem incluir aplicativos ELIN (Número de Identificação de Localização de Emergência). Se um aplicativo ELIN SBC estiver integrado a uma implantação de Roteamento Direto, você deverá configurar os endereços de emergência e os números de telefone associados no aplicativo ELIN e, em seguida, carregar os registros ELIN para o banco de dados de chamadas de emergência no PSTN respectivo.  Locais de emergência do Teams com um identificador ELIN devem corresponder aos do aplicativo ELIN.

Quando uma chamada de emergência com um local adquirido dinamicamente é roteada para o SBC apropriado, o aplicativo ELIN:

- Analisar o local de emergência do chamador.
- Corresponde o local a um registro ELIN.
- Substitui o número do chamador de emergência pelo número de telefone ELIN.
- Encaminha a chamada para o PSAP que atende a esse local e, em seguida, os expedidores obtém a localização do registro ELIN carregado.

Após uma chamada de volta para o número de emergência, o aplicativo ELIN fará a substituição inversa chamada de número à do chamador de emergência original. 

Para obter mais informações, consulte [Controladores de Borda de Sessão certificados para Roteamento Direto.](direct-routing-border-controllers.md)


## <a name="security-desk-notification"></a>Notificação de segurança

A notificação de segurança está disponível nos Planos de Chamada da Microsoft e no Roteamento Direto do Sistema de Telefonia.

Você usa uma política de chamada de emergência do Teams (TeamsEmergencyCallingPolicy) para configurar quem deve ser notificado durante uma chamada de emergência e como eles são notificados: somente chat, em conferência e com mudo mudo, ou com a opção de desativar mudo.  Você também pode especificar um número PSTN externo de um usuário ou grupo para ligar e ingressar na chamada de emergência. 

Uma política de chamada de emergência pode ser concedida a uma conta de usuário do Teams, atribuída a um site de rede ou a ambos.  Quando um cliente do Teams inicia ou altera uma conexão de rede, o Teams executa uma busca do site de rede onde o cliente está localizado:

- Se uma política de chamada de emergência estiver associada a um site de rede, a política de site será usada para configurar a notificação de segurança.

- Se não houver nenhuma política de chamada de emergência associada ao site ou se o cliente estiver conectado em um site não definido, a política de chamada de emergência associada à conta de usuário será usada para configurar a notificação de segurança.  

- Se o cliente do Teams não conseguir obter uma política de chamada de emergência, o usuário não está habilitado para notificação de segurança.

Durante uma chamada de emergência, uma mesa de segurança é conferênciada na chamada e a experiência do usuário do escritório de segurança é controlada com base na política de chamada de emergência do Teams. Um chat em grupo é iniciado com cada membro do escritório de segurança, e o local do chamador de emergência é compartilhado por meio de uma notificação de mensagem importante.  Se uma opção de conferência estiver configurada como parte da política, cada usuário do security desk também será chamado como parte da conferência.

    
## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar políticas de chamadas de emergência](manage-emergency-calling-policies.md)
- [Gerenciar políticas de roteamento de chamadas de emergência ](manage-emergency-call-routing-policies.md)
- [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)
- [Atribuir ou alterar um local de emergência para o usuário](assign-change-emergency-location-user.md)
- [Planejar e configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md)
