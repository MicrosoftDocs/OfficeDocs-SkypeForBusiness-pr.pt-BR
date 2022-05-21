---
title: Planejar e gerenciar chamadas de emergência
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
- seo-marvel-mar2020
description: Saiba mais sobre chamadas de emergência, incluindo informações sobre endereços de emergência, roteamento de chamadas de emergência e chamadas de emergência dinâmicas.
ms.openlocfilehash: 2806499e81b524168944e6cca2e9a6acb4d0b6a7
ms.sourcegitcommit: 4435ac0efcb95e4e5e1f21289e46761e79482ab5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2022
ms.locfileid: "65624125"
---
# <a name="manage-emergency-calling"></a>Gerenciar chamadas de emergência

Este artigo descreve os conceitos que&mdash; você precisará saber para gerenciar chamadas de emergência, incluindo informações sobre endereços de emergência, endereços de emergência dinâmicos e roteamento de chamadas de emergência. Este artigo usa a seguinte terminologia:

- **Endereço de** emergência – um endereço cívico&mdash; do endereço físico ou da rua de um local de negócios para sua organização.

  Por exemplo, o endereço *12345 North Main Street, Redmond, WA 98052* é usado para encaminhar chamadas de emergência para as autoridades de expedição apropriadas e para ajudar a localizar o chamador de emergência.

- **Local** - Normalmente um número de escritório, prédio, ala ou andar. O local está associado a um endereço de emergência para fornecer um local mais exato dentro de um prédio. Você pode ter um número ilimitado de locais associados a um endereço de emergência. Por exemplo, se sua organização tiver vários edifícios, convém incluir informações de local para cada prédio e todos os andares de cada prédio.  

- **Local de** emergência - Um local é um endereço cívico&mdash; com um local opcional. Se sua empresa tiver mais de um local físico, é provável que você precise de mais de um local de emergência. 

  Quando você cria um endereço de emergência, uma ID de local exclusiva é criada automaticamente para esse endereço. Se você adicionar um local a&mdash; um endereço de emergência por exemplo, se você adicionar um andar a&mdash; um endereço de construção, uma ID de local será criada para a combinação do endereço e do local de emergência.  Neste exemplo, haverá duas IDs de localização: uma para o endereço cívico; um para o endereço cívico ingressado e local associado.

  Quando você atribui um local de emergência a um usuário ou site, é essa ID de local exclusiva associada ao usuário ou ao site.

- **Endereço registrado** – um endereço de emergência atribuído a cada usuário. Um endereço registrado às vezes é chamado de endereço de emergência estático ou endereço de registro. (Atualmente, não há suporte para endereços registrados no Roteamento Direto. Verifique novamente em breve se há atualizações.)

>[!Note]
>Há algumas diferenças em como você gerencia chamadas de emergência, dependendo se você está usando planos de chamada da Microsoft, Conexão do operador ou roteamento direto para sua [conectividade PSTN](pstn-connectivity.md). Essas considerações são descritas ao longo deste artigo.

## <a name="emergency-address-validation"></a>Validação de endereço de emergência

Para atribuir um endereço de emergência a um usuário ou a um identificador de rede, você deve garantir que o endereço de emergência esteja marcado como "validado". A validação de endereço garante que o endereço seja legítimo e que ele não possa ser modificado depois de atribuído. 

Se você definir um endereço de emergência usando o recurso de pesquisa de mapa de endereços no centro de administração do Teams, o endereço será marcado automaticamente como validado. Como não é possível modificar um endereço de&mdash; emergência validado se o formato ou a representação do endereço for alterado, você deve criar um novo endereço com o formato atualizado.


## <a name="emergency-address-geo-codes"></a>Códigos geogeográficos de endereço de emergência

Cada endereço de emergência pode ter um código geográfica (latitude e longitude) associado a ele. Esses códigos geográficos são usados em alguns países para auxiliar no roteamento de chamadas de emergência com locais dinâmicos. 

Se você definir um endereço de emergência usando o recurso de pesquisa de mapa de endereços no centro de administração do Teams, o código geogeográfico será automaticamente associado a um endereço de emergência. Você também poderá associar códigos geogeográficos a um endereço se definir o endereço usando o PowerShell. 

A Microsoft recomenda que você crie endereços de emergência usando o recurso de pesquisa de mapa no centro de administração do Teams, o que garantirá que os endereços sejam formatados, validados e tenham os códigos geogeográficos apropriados. 

>[!Important]
>Para atribuir um local de emergência a um identificador de rede para chamadas de emergência dinâmicas, o endereço de emergência deve conter um código geogeográfico apropriado.


## <a name="considerations-for-calling-plans"></a>Considerações sobre planos de chamadas

As seções a seguir descrevem como gerenciar chamadas de emergência para usuários do Plano de Chamadas da Microsoft. Para descobrir se os Planos de Chamadas da Microsoft são a solução certa para sua empresa, confira as [opções de conectividade PSTN](pstn-connectivity.md).


### <a name="emergency-call-enablement-for-calling-plans"></a>Habilitação de chamada de emergência para Planos de Chamadas

Cada usuário do Plano de Chamadas é habilitado automaticamente para chamadas de emergência e precisa ter um endereço de emergência registrado associado ao número de telefone atribuído. 

Quando o local está associado ao número de telefone depende do país/região:

- No Estados Unidos e no Canadá, por exemplo, um local de emergência é necessário quando um número é atribuído a um usuário.

- &mdash;Para outros países, como na Europa, no Oriente Médio e na África (EMEA),&mdash; um local de emergência é necessário quando você obtém o número de telefone do Microsoft 365 ou quando ele é transferido de outro provedor de serviços ou operadora.


### <a name="dynamic-emergency-calling-for-calling-plans"></a>Chamada de emergência dinâmica para planos de chamada

A chamada de emergência dinâmica para Planos de Chamadas fornece a capacidade de configurar e rotear chamadas de emergência com base na localização atual do Teams cliente. A capacidade de fazer o roteamento automático para o PSAP (Ponto de Atendimento à Segurança Pública) apropriado ou notificar a equipe do suporte de segurança varia dependendo do país de uso do Teams usuário.  

Há suporte para o local dinâmico para roteamento de chamadas de emergência no Estados Unidos da seguinte maneira. 

- Se um cliente do Teams para um usuário do Plano de Chamada do Estados Unidos adquirir dinamicamente um endereço de emergência dentro do Estados Unidos, esse endereço será usado para roteamento de emergência em vez do endereço registrado e a chamada será roteada automaticamente para o PSAP na área de serviço do endereço.

- Se um cliente Teams para um usuário do Plano de Chamadas do Estados Unidos não adquirir dinamicamente um endereço de emergência dentro do Estados Unidos, o endereço de emergência registrado será usado para ajudar a tela e rotear a chamada. No entanto, a chamada será exibida para determinar se um endereço atualizado é necessário antes de conectar o chamador ao PSAP apropriado.

Há suporte para o local dinâmico para roteamento de chamadas de emergência no Canadá da mesma forma que no Estados Unidos com a seguinte exceção: todas as chamadas de emergência serão teladas nacionalmente antes de serem transferidas para o PSAP.

Para obter mais informações, consulte [Planejar e configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-calling-plans"></a>Roteamento de chamadas de emergência para Planos de Chamadas

Quando um Teams de Chamadas disca um número de emergência, como a chamada é roteada para o PSAP depende do seguinte:

- Se o endereço de emergência é determinado dinamicamente pelo Teams cliente.

- Se o endereço de emergência é o endereço registrado associado ao número de telefone do usuário.

- A rede de chamadas de emergência desse país.

Por exemplo:

**No Estados Unidos:**

- Se um Teams cliente estiver localizado em um local de emergência dinâmico definido pelo locatário, as chamadas de emergência desse cliente serão roteadas automaticamente para o PSAP que atende a essa localização geográfica.

- Se um cliente do Teams não estiver localizado em um local de emergência dinâmico definido pelo locatário, as chamadas de emergência desse cliente serão teladas por um call center nacional para determinar a localização do chamador antes de transferir a chamada para o PSAP que atende a essa localização geográfica.

- Se um chamador de emergência não puder atualizar seu local de emergência para o centro de triagem, a chamada será transferida para o PSAP que atende ao endereço registrado do chamador.

**No Canadá, na Irlanda** e no Reino Unido, as chamadas de emergência são exibidas primeiro para determinar a localização atual do usuário antes de conectar a chamada ao centro de expedição apropriado.

**Na França, na Alemanha** e na Espanha, as chamadas de emergência são roteados diretamente para o PSAP que atende ao endereço de emergência associado ao número, independentemente da localização do chamador.

**Nos Países Baixos**, as chamadas de emergência são roteados diretamente para o PSAP para o código de área local do número, independentemente da localização do chamador.

**Na Austrália**, os endereços de emergência são configurados e roteados pelo parceiro da operadora.

**No Japão**, não há suporte para chamadas de emergência.


Para obter mais informações, consulte:

- [Planos de Chamadas](calling-plan-landing-page.md)
- [Configurar Planos de Chamadas](set-up-calling-plans.md)
- [Diferentes tipos de números de telefone utilizados para Planos de Chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Termos e condições para chamadas de emergência](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-operator-connect"></a>Considerações sobre Conexão do operador

As seções a seguir descrevem como gerenciar chamadas de emergência para Conexão do operador usuários. Para descobrir se o Conexão do operador é a solução certa para sua empresa, confira as opções de [conectividade PSTN](pstn-connectivity.md).

### <a name="emergency-call-enablement-for-operator-connect"></a>Habilitação de chamada de emergência para Conexão do operador

Cada Conexão do operador usuário é habilitado automaticamente para chamadas de emergência. Chamadas de emergência são roteadas automaticamente para a Conexão do operador para um determinado número.

A capacidade de um administrador de locatários definir o endereço registrado para um usuário do Conexão do operador dependerá dos recursos atribuídos ao número quando a operadora os carregar em um inventário de clientes. Com base nessa configuração, o administrador de locatários&mdash; pode ou não ser necessário ou&mdash; não ser capaz de definir, modificar ou excluir o local de emergência de um usuário. 

### <a name="dynamic-emergency-calling-for-operator-connect"></a>Chamada de emergência dinâmica para Conexão do operador

A chamada de emergência dinâmica para Conexão do operador fornece a capacidade de configurar e rotear chamadas de emergência com base na localização atual do Teams cliente. A capacidade de fazer o roteamento automático para o PSAP (Ponto de Atendimento à Segurança Pública) apropriado ou notificar a equipe do suporte de segurança varia dependendo do país de uso do Teams usuário. 

Há suporte para o local dinâmico para roteamento de chamadas de emergência no Estados Unidos da seguinte maneira. 

- Se um cliente do Teams para um usuário do Estados Unidos adquirir dinamicamente um endereço de emergência dentro do Estados Unidos, esse endereço será usado para roteamento de emergência em vez do endereço registrado e a chamada será roteada automaticamente para o PSAP na área de serviço do endereço.

- Se um Teams para um usuário do Estados Unidos não adquirir dinamicamente um endereço de emergência no Estados Unidos, o endereço de emergência registrado será usado para ajudar a tela e rotear a chamada. No entanto, a chamada será exibida para determinar se um endereço atualizado é necessário antes de conectar o chamador ao PSAP apropriado.

Há suporte para o local dinâmico para roteamento de chamadas de emergência no Canadá da mesma forma que no Estados Unidos com as seguintes exceções: todas as chamadas de emergência serão teladas nacionalmente antes de serem transferidas para o PSAP.

Para obter mais informações, consulte [Planejar e configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-operator-connect"></a>Roteamento de chamadas de emergência para Conexão do operador

Quando um Teams Conexão do operador disca um número de emergência, a maneira como a chamada é roteada para o PSAP depende do seguinte:

- Se o endereço de emergência é determinado dinamicamente pelo Teams cliente.

- Se o endereço de emergência é o endereço registrado associado ao número de telefone do usuário.

- A rede de chamadas de emergência desse país.

- No Estados Unidos e no Canadá, o roteamento dinâmico faz parte do serviço da operadora. Você não precisa adquirir esse serviço de outro provedor de serviços.

- Se um Teams cliente estiver localizado em um local de emergência dinâmico definido pelo locatário:

   - No Estados Unidos, as chamadas de emergência desse cliente são roteadas automaticamente para o PSAP que atende a essa localização geográfica.
   - No Canadá, todas as chamadas de emergência serão filtradas por um call center nacional antes de transferir a chamada para o PSAP que atende a essa localização geográfica.

- Se um cliente do Teams não estiver localizado em um local de emergência dinâmico definido pelo locatário, as chamadas de emergência desse cliente serão teladas por um call center nacional para determinar a localização do chamador antes de transferir a chamada para o PSAP que atende a essa localização geográfica.

- Se um chamador de emergência não puder atualizar seu local de emergência para o centro de triagem, a chamada será transferida para o PSAP que atende ao endereço registrado do chamador.


## <a name="considerations-for-direct-routing"></a>Considerações sobre roteamento direto

As seções a seguir descrevem como gerenciar chamadas de emergência para usuários de Roteamento Direto. Para descobrir se o Roteamento Direto é a solução certa para sua empresa, confira as [opções de conectividade PSTN](pstn-connectivity.md).

### <a name="emergency-call-enablement-for-direct-routing"></a>Habilitação de chamada de emergência para Roteamento Direto

Para o Roteamento Direto, você deve definir políticas de chamada de emergência [](manage-emergency-call-routing-policies.md) para usuários usando uma política de roteamento de chamadas de Teams para definir números de emergência e seu destino de roteamento associado. (Atualmente, não há suporte para locais de emergência registrados para usuários de Roteamento Direto.)

Você pode atribuir uma política de roteamento de chamadas de emergência a uma conta de usuário de Roteamento Direto, um site de rede ou ambos. Quando um Teams inicia ou altera uma conexão de rede, o Teams executa uma pesquisa do site de rede em que o cliente está localizado da seguinte maneira:

- Se uma política de roteamento de chamadas de emergência estiver associada ao site, a política de site será usada para configurar a chamada de emergência.

- Se não houver nenhuma política de roteamento de chamadas de emergência associada ao site, se o cliente estiver conectado em um site indefinido ou se o número discado não corresponder a nenhum dos números de emergência definidos na política de roteamento de chamadas de emergência associada ao site, a política de roteamento de chamadas de emergência associada à conta de usuário será usada para configurar a chamada de emergência. 

- Se o Teams cliente não puder obter uma política de roteamento de chamadas de emergência, o usuário não estará habilitado para chamadas de emergência.


### <a name="dynamic-emergency-calling-for-direct-routing"></a>Chamada de emergência dinâmica para Roteamento Direto

A chamada de emergência dinâmica para Roteamento Direto fornece a capacidade de configurar e rotear chamadas de emergência com base na localização atual do Teams cliente. A capacidade de fazer o roteamento automático para o PSAP (Ponto de Atendimento à Segurança Pública) apropriado ou notificar a equipe do suporte de segurança varia dependendo do país de uso do Teams usuário.

Para usuários de Roteamento Direto, o local dinâmico para roteamento de chamadas de emergência só tem suporte no Estados Unidos da seguinte maneira:

-   Se um cliente Teams para um usuário de Roteamento Direto do Estados Unidos adquirir dinamicamente um endereço de emergência dentro do Estados Unidos, esse endereço será usado para roteamento de emergência e a chamada será roteada automaticamente para o PSAP na área de serviço do endereço.

-   Se um cliente Teams para um usuário de Roteamento Direto do Estados Unidos não adquirir dinamicamente um endereço de emergência dentro do Estados Unidos, a chamada será exibida para determinar se um endereço atualizado é necessário antes de conectar o chamador ao PSAP apropriado.

Há suporte para o local dinâmico para roteamento de chamadas de emergência no Canadá da mesma forma que no Estados Unidos com a seguinte exceção: todas as chamadas de emergência serão teladas nacionalmente antes de serem transferidas para o PSAP.

Para obter mais informações, consulte [Configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-direct-routing"></a>Roteamento de chamadas de emergência para Roteamento Direto

A política de roteamento de chamadas de emergência para Roteamento Direto faz referência a um uso PSTN online, que deve ter a configuração de Roteamento Direto apropriada para rotear corretamente as chamadas de emergência para os gateways PSTN apropriados. Em particular, você deve garantir que haja um OnlineVoiceRoute para a cadeia de caracteres de discagem de emergência. Para obter mais informações, consulte [Configurar Roteamento Direto](direct-routing-configure.md). 

> [!NOTE]
> Teams clientes não precedem mais o sinal "+" na frente dos números de emergência, ou seja, +911. Consequentemente, Teams chamadas de emergência não enviarão mais um "+" antes do número 911. Verifique se os padrões de rota de voz refletem essa alteração.

A capacidade de rotear dinamicamente chamadas de emergência para usuários de Roteamento Direto varia dependendo da rede de chamadas de emergência em um determinado país. Há duas soluções disponíveis:

- [Provedores de Serviços de Roteamento de Emergência (somente EUA)](#emergency-routing-service-providers)
- [Aplicativos número de identificação de local de emergência](#emergency-location-identification-number-applications)

#### <a name="emergency-routing-service-providers"></a>Provedores de Serviços de Roteamento de Emergência

No Estados Unidos, há vários ERSPs (Provedores de Serviços de Roteamento de Emergência) certificados que podem rotear automaticamente chamadas de emergência com base na localização do chamador.

- Se um Provedor de Serviços de Roteamento de Emergência estiver integrado a uma implantação de Roteamento Direto, as chamadas de emergência com um local adquirido dinamicamente serão roteadas automaticamente para o PSAP (Ponto de Atendimento à Segurança Pública) que atende a esse local.

-  As chamadas de emergência sem um local adquirido dinamicamente são primeiro filtradas para determinar o local atual do usuário antes de conectar a chamada ao centro de expedição apropriado com base no local atualizado.

Para obter mais informações, consulte [Controladores de borda de sessão certificados para Roteamento Direto](direct-routing-border-controllers.md).


#### <a name="emergency-location-identification-number-applications"></a>Aplicativos número de identificação de local de emergência

Os SBCs (Controladores de Borda de Sessão) podem incluir aplicativos ELIN (Número de Identificação de Local de Emergência). Se um aplicativo SBC ELIN estiver integrado a uma implantação de Roteamento Direto, você deverá configurar os endereços de emergência e os números de telefone associados no aplicativo ELIN e, em seguida, carregar os registros ELIN no banco de dados de chamadas de emergência no respectivo PSTN. Teams locais de emergência com um identificador ELIN devem corresponder àqueles dentro do aplicativo ELIN.

Quando uma chamada de emergência com um local adquirido dinamicamente é roteada para o SBC apropriado, o aplicativo ELIN:

- Analisa o local de emergência do chamador.
- Corresponde o local a um registro ELIN.
- Substitui o número do chamador de emergência pelo número de telefone ELIN.
- Roteia a chamada para o PSAP que atende a esse local e, em seguida, os dispatchers obtêm o local do registro ELIN carregado.

Após uma chamada de volta para o número de emergência, o aplicativo ELIN fará a substituição inversa chamada de número à do chamador de emergência original. 

Para obter mais informações, consulte [Controladores de borda de sessão certificados para Roteamento Direto](direct-routing-border-controllers.md).


## <a name="security-desk-notification"></a>Notificação de suporte de segurança

A notificação de suporte de segurança está disponível com planos de chamadas da Microsoft, Conexão do operador e Roteamento Direto.

Você usa uma política de chamada de emergência do Teams (TeamsEmergencyCallingPolicy) para configurar quem deve ser notificado durante uma chamada de emergência e como eles são notificados: somente chat, em conferência e mudo, ou em conferências e mudo, mas com a capacidade de desativar mudo. Você também pode especificar um número PSTN externo de um usuário ou grupo para chamar e ingressar na chamada de emergência. Observe que a parte PSTN não tem permissão para desativar o mudo.

Uma política de chamada de emergência pode ser concedida a uma Teams de usuário, atribuída a um site de rede ou a ambos.  Quando um Teams inicia ou altera uma conexão de rede, Teams executa uma pesquisa do site de rede em que o cliente está localizado:

- Se uma política de chamada de emergência estiver associada a um site de rede, a política de site será usada para configurar a notificação do suporte de segurança.

- Se não houver nenhuma política de chamada de emergência associada ao site ou se o cliente estiver conectado em um site indefinido, a política de chamada de emergência associada à conta de usuário será usada para configurar a notificação do suporte de segurança.  

- Se o Teams cliente não puder obter uma política de chamada de emergência, o usuário não estará habilitado para notificação do suporte de segurança.

Durante uma chamada de emergência, uma central de segurança é conferênciada na chamada e a experiência do usuário do suporte de segurança é controlada com base Teams política de chamada de emergência. Um chat em grupo é iniciado com cada membro do suporte de segurança e o local do chamador de emergência é compartilhado por meio de uma notificação de mensagem importante.  Se uma opção de conferência estiver configurada como parte da política, cada usuário do suporte de segurança também será chamado como parte da conferência.

### <a name="custom-emergency-disclaimer"></a>Aviso de isenção de responsabilidade de emergência personalizado

Os administradores têm a capacidade de adicionar uma faixa personalizada no locatário para que seus usuários habilitem o E911. Os usuários podem ignorar a faixa quando confirmarem seu endereço e a faixa reaparecerá quando Teams for reiniciado. Para habilitar esse recurso, defina  o aviso de isenção de responsabilidade do serviço de emergência na política de chamada de Teams de emergência e insira uma mensagem de cadeia de caracteres a ser exibida aos usuários. Esse campo é opcional ao configurar uma política personalizada e o campo de cadeia de caracteres é limitado a 250 caracteres.

    
## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar políticas de chamadas de emergência](manage-emergency-calling-policies.md)
- [Gerenciar políticas de roteamento de chamadas de emergência ](manage-emergency-call-routing-policies.md)
- [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)
- [Atribuir ou alterar um local de emergência para o usuário](assign-change-emergency-location-user.md)
- [Planejar e configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md)
