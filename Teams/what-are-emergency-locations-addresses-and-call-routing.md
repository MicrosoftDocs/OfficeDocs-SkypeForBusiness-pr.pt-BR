---
title: Planejar e gerenciar a chamada de emergência
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz, jastark
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
ms.openlocfilehash: f6c1dd766ae14d855b9f2ffcf21c41ed8a5a1550
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634860"
---
# <a name="manage-emergency-calling"></a>Gerenciar chamada de emergência

Este artigo descreve conceitos que você precisará saber para gerenciar chamadas de emergência, incluindo informações sobre endereços de emergência, endereços de emergência dinâmicos e &mdash; roteamento de chamadas de emergência. Este artigo usa a seguinte terminologia:

- **Endereço de** emergência - Um endereço &mdash; cívico o endereço físico ou de rua de um local de negócios para sua organização.

  Por exemplo, o endereço *12345 North Main Street, Redmond, WA 98052* é usado para encaminhar chamadas de emergência para as autoridades de expedição apropriadas e para ajudar a localizar o chamador de emergência.

- **Local** - Normalmente um número de escritório, construção, construção ou ala. O local está associado a um endereço de emergência para dar um local mais exato em um edifício. Você pode ter um número ilimitado de locais associados a um endereço de emergência. Por exemplo, se sua organização tiver vários edifícios, talvez você queira incluir informações de local para cada edifício e cada andar dentro de cada edifício.  

- **Local de emergência** - Um local é um endereço &mdash; cívico com um local opcional. Se sua empresa tiver mais de um local físico, é provável que você precise de mais de um local de emergência. 

  Quando você cria um endereço de emergência, uma ID de local exclusiva é criada automaticamente para esse endereço. Se você adicionar um local a um endereço de emergência, por exemplo, se você adicionar um piso a um endereço de construção, uma ID de local será criada para a combinação do endereço e local de &mdash; &mdash; emergência.  Neste exemplo, haverá duas IDs de local: uma para o endereço cívico; um para o endereço cívico ingressado e o local associado.

  Quando você atribui um local de emergência a um usuário ou site, é essa ID de local exclusiva associada ao usuário ou site.

- **Endereço registrado** - Um endereço de emergência atribuído a cada usuário. Às vezes, um endereço registrado é conhecido como um endereço de emergência ou endereço de registro estático. (Atualmente, os endereços registrados não têm suporte para Roteamento Direto. Volte em breve para atualizações.)

>[!Note]
>Há algumas diferenças em como gerenciar chamadas de emergência, dependendo se você está usando Planos de Chamadas da Microsoft, Operador Conexão ou Roteamento Direto para sua [conectividade PSTN](pstn-connectivity.md). Essas considerações são descritas ao longo deste artigo.

## <a name="emergency-address-validation"></a>Validação de endereço de emergência

Para atribuir um endereço de emergência a um usuário ou a um identificador de rede, você deve garantir que o endereço de emergência seja marcado como "validado". A validação de endereço garante que o endereço seja legítimo e que ele não possa ser modificado depois que ele for atribuído. 

Se você definir um endereço de emergência usando o recurso de pesquisa de mapa de endereços no centro de administração Teams, o endereço será marcado automaticamente como validado. Como não é possível modificar um endereço de emergência validado se o formato ou representação do endereço for modificado, você deve criar um novo endereço &mdash; com o formato atualizado.


## <a name="emergency-address-geo-codes"></a>Códigos geo de endereço de emergência

Cada endereço de emergência pode ter um código geo (latitude e longitude) associado a ele. Esses códigos geo são usados em alguns países para ajudar a rotear chamadas de emergência com locais dinâmicos. 

Se você definir um endereço de emergência usando o recurso de pesquisa de mapa de endereços no centro de administração Teams, o código geo será automaticamente associado a um endereço de emergência. Você também pode associar códigos geo a um endereço se definir o endereço usando o PowerShell. 

A Microsoft recomenda que você crie endereços de emergência usando o recurso de pesquisa de mapa no centro de administração Teams, o que garantirá que os endereços sejam formatados, validados e tenham os códigos geo apropriados. 

>[!Important]
>Para atribuir um local de emergência a um identificador de rede para chamada de emergência dinâmica, o endereço de emergência deve conter um código geo apropriado.


## <a name="considerations-for-calling-plans"></a>Considerações sobre planos de chamada

As seções a seguir descrevem como gerenciar a chamada de emergência para usuários do Plano de Chamada da Microsoft. Para descobrir se os Planos de Chamada da Microsoft são a solução certa para sua empresa, consulte Opções de [conectividade PSTN](pstn-connectivity.md).


### <a name="emergency-call-enablement-for-calling-plans"></a>Habilitação de chamada de emergência para planos de chamada

Cada usuário do Plano de Chamadas é habilitado automaticamente para chamadas de emergência e é necessário ter um endereço de emergência registrado associado ao número de telefone atribuído. 

Quando o local é associado ao número de telefone depende do país/região:

- Nos Estados Unidos e no Canadá, por exemplo, um local de emergência é necessário quando um número é atribuído a um usuário.

- Para outros países, como na Europa, Oriente Médio e África (EMEA), um local de emergência é necessário quando você obter o número de telefone do Microsoft 365 ou quando ele for transferido de outro provedor de serviços ou &mdash; &mdash; operadora.


### <a name="dynamic-emergency-calling-for-calling-plans"></a>Chamada de emergência dinâmica para planos de chamada

A chamada de emergência dinâmica para Planos de Chamadas oferece a capacidade de configurar e rotear chamadas de emergência com base no local atual do cliente Teams. A capacidade de fazer o roteamento automático para o PSAP (Ponto de Atendimento de Segurança Pública) apropriado ou notificar a equipe de segurança varia dependendo do país de uso do usuário Teams.  

O local dinâmico para roteamento de chamadas de emergência é suportado nos Estados Unidos da seguinte forma. 

- Se um cliente Teams para um usuário do Plano de Chamadas dos Estados Unidos adquirir dinamicamente um endereço de emergência nos Estados Unidos, esse endereço será usado para roteamento de emergência em vez do endereço registrado e a chamada será roteada automaticamente para o PSAP na área de serviço do endereço.

- Se um cliente Teams para um usuário do Plano de Chamada dos Estados Unidos não adquirir dinamicamente um endereço de emergência nos Estados Unidos, o endereço de emergência registrado será usado para ajudar a telar e roteá-la. No entanto, a chamada será triada para determinar se um endereço atualizado é necessário antes de conectar o chamador ao PSAP apropriado.

O local dinâmico para roteamento de chamadas de emergência é suportado no Canadá da mesma forma que nos Estados Unidos, com a seguinte exceção: todas as chamadas de emergência serão triadas nacionalmente antes de serem transferidas para o PSAP.

Para obter mais informações, [consulte Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-calling-plans"></a>Roteamento de chamadas de emergência para planos de chamadas

Quando um Teams de chamada disca um número de emergência, como a chamada é roteada para o PSAP depende do seguinte:

- Se o endereço de emergência é dinamicamente determinado pelo Teams cliente.

- Se o endereço de emergência é o endereço registrado associado ao número de telefone do usuário.

- A rede de chamada de emergência desse país.

Por exemplo:

**Nos Estados Unidos:**

- Se um Teams cliente estiver localizado em um local de emergência dinâmico definido pelo locatário, as chamadas de emergência desse cliente serão roteados automaticamente para o PSAP que atende a essa localização geográfica.

- Se um cliente Teams não estiver localizado em um local de emergência dinâmico definido pelo locatário, as chamadas de emergência desse cliente serão monitoradas por um centro de chamada nacional para determinar o local do chamador antes de transferir a chamada para o PSAP que atende a essa localização geográfica.

- Se um chamador de emergência não puder atualizar seu local de emergência para o centro de triagem, a chamada será transferida para o PSAP que atende ao endereço registrado do chamador.

**No Canadá, na Irlanda** e no Reino Unido, as chamadas de emergência são primeiramente triadas para determinar o local atual do usuário antes de conectar a chamada ao centro de expedição apropriado.

**Na França, Alemanha** e Espanha, as chamadas de emergência são roteados diretamente para o PSAP que atende ao endereço de emergência associado ao número, independentemente do local do chamador.

**Nos Países Baixos,** as chamadas de emergência são roteados diretamente para o PSAP para o código de área local do número, independentemente do local do chamador.

**Na Austrália,** os endereços de emergência são configurados e roteados pelo parceiro de operadora.

**No Japão,** não há suporte para chamada de emergência.


Para obter mais informações, consulte:

- [Planos de Chamadas](calling-plan-landing-page.md)
- [Configurar Planos de Chamadas](set-up-calling-plans.md)
- [Diferentes tipos de números de telefone utilizados para Planos de Chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Termos e condições para chamadas de emergência](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-operator-connect"></a>Considerações sobre o operador Conexão

As seções a seguir descrevem como gerenciar a chamada de emergência para usuários Conexão operadores. Para descobrir se o operador Conexão é a solução certa para sua empresa, consulte Opções de [conectividade PSTN](pstn-connectivity.md).

### <a name="emergency-call-enablement-for-operator-connect"></a>Habilitação de chamada de emergência para operador Conexão

Cada usuário Conexão operador é habilitado automaticamente para chamada de emergência. As chamadas de emergência são roteados automaticamente para a operadora Conexão operador para um determinado número.

A capacidade de um administrador de locatário definir o endereço registrado para um usuário Conexão operador dependerá dos recursos atribuídos ao número quando a operadora os carregar em um inventário de clientes. Com base nessa configuração, o administrador do locatário pode ou não ser necessário ou capaz de definir, modificar ou excluir o local de emergência &mdash; &mdash; de um usuário. 

### <a name="dynamic-emergency-calling-for-operator-connect"></a>Chamada de emergência dinâmica para operador Conexão

A chamada de emergência dinâmica para operador Conexão oferece a capacidade de configurar e rotear chamadas de emergência com base no local atual do cliente Teams. A capacidade de fazer o roteamento automático para o PSAP (Ponto de Atendimento de Segurança Pública) apropriado ou notificar a equipe de segurança varia dependendo do país de uso do usuário Teams. 

O local dinâmico para roteamento de chamadas de emergência é suportado nos Estados Unidos da seguinte forma. 

- Se um cliente Teams para um usuário dos Estados Unidos adquirir dinamicamente um endereço de emergência nos Estados Unidos, esse endereço será usado para roteamento de emergência em vez do endereço registrado e a chamada será roteada automaticamente para o PSAP na área de serviço do endereço.

- Se um Teams cliente para um usuário dos Estados Unidos não adquirir dinamicamente um endereço de emergência nos Estados Unidos, o endereço de emergência registrado será usado para ajudar a tela e roteá-la. No entanto, a chamada será triada para determinar se um endereço atualizado é necessário antes de conectar o chamador ao PSAP apropriado.

O local dinâmico para roteamento de chamadas de emergência é suportado no Canadá da mesma forma que nos Estados Unidos, com as seguintes exceções: todas as chamadas de emergência serão triadas nacionalmente antes de serem transferidas para o PSAP.

Para obter mais informações, [consulte Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-operator-connect"></a>Roteamento de chamadas de emergência para operador Conexão

Quando um Teams operador Conexão disca um número de emergência, como a chamada é roteada para o PSAP depende do seguinte:

- Se o endereço de emergência é dinamicamente determinado pelo Teams cliente.

- Se o endereço de emergência é o endereço registrado associado ao número de telefone do usuário.

- A rede de chamada de emergência desse país.

- Nos Estados Unidos e no Canadá, o roteamento dinâmico faz parte do serviço da operadora. Você não precisa adquirir esse serviço de outro provedor de serviços.

Nos Estados Unidos e no Canadá:

- Se um Teams cliente estiver localizado em um local de emergência dinâmico definido pelo locatário, as chamadas de emergência desse cliente serão roteados automaticamente para o PSAP que atende a essa localização geográfica.

- Se um cliente Teams não estiver localizado em um local de emergência dinâmico definido pelo locatário, as chamadas de emergência desse cliente serão monitoradas por um centro de chamada nacional para determinar o local do chamador antes de transferir a chamada para o PSAP que atende a essa localização geográfica.

- Se um chamador de emergência não puder atualizar seu local de emergência para o centro de triagem, a chamada será transferida para o PSAP que atende ao endereço registrado do chamador.


## <a name="considerations-for-direct-routing"></a>Considerações sobre roteamento direto

As seções a seguir descrevem como gerenciar chamadas de emergência para usuários de Roteamento Direto. Para descobrir se o Roteamento Direto é a solução certa para sua empresa, consulte Opções de [conectividade PSTN](pstn-connectivity.md).

### <a name="emergency-call-enablement-for-direct-routing"></a>Habilitação de chamada de emergência para Roteamento Direto

Para Roteamento Direto, você deve definir [](manage-emergency-call-routing-policies.md) políticas de chamadas de emergência para usuários usando uma política de roteamento de chamadas de emergência Teams para definir números de emergência e seu destino de roteamento associado. (Atualmente, locais de emergência registrados não são suportados para usuários de Roteamento Direto.)

Você pode atribuir uma política de roteamento de chamadas de emergência a uma conta de usuário de Roteamento Direto, um site de rede ou ambos. Quando um cliente Teams inicia ou altera uma conexão de rede, o Teams executa uma busca do site de rede no qual o cliente está localizado da seguinte forma:

- Se uma política de roteamento de chamadas de emergência estiver associada ao site, a política de site será usada para configurar chamadas de emergência.

- Se não houver nenhuma política de roteamento de chamadas de emergência associada ao site, se o cliente estiver conectado em um site indefinido ou se o número discado não corresponder a nenhum dos números de emergência definidos na política de roteamento de chamadas de emergência associada ao site, a política de roteamento de chamadas de emergência associada à conta de usuário será usada para configurar a chamada de emergência. 

- Se o Teams cliente não conseguir obter uma política de roteamento de chamadas de emergência, o usuário não está habilitado para chamadas de emergência.


### <a name="dynamic-emergency-calling-for-direct-routing"></a>Chamada de emergência dinâmica para Roteamento Direto

A chamada de emergência dinâmica para Roteamento Direto oferece a capacidade de configurar e rotear chamadas de emergência com base no local atual do Teams cliente. A capacidade de fazer o roteamento automático para o PSAP (Ponto de Atendimento de Segurança Pública) apropriado ou notificar a equipe de segurança varia dependendo do país de uso do usuário Teams.

Para usuários de Roteamento Direto, o local dinâmico para roteamento de chamadas de emergência só é suportado nos Estados Unidos da seguinte maneira:

-   Se um cliente Teams para um usuário de Roteamento Direto dos Estados Unidos adquirir dinamicamente um endereço de emergência nos Estados Unidos, esse endereço será usado para roteamento de emergência e a chamada será roteada automaticamente para o PSAP na área de serviço do endereço.

-   Se um cliente Teams para um usuário de Roteamento Direto dos Estados Unidos não adquirir dinamicamente um endereço de emergência nos Estados Unidos, a chamada será triada para determinar se um endereço atualizado é necessário antes de conectar o chamador ao PSAP apropriado.

O local dinâmico para roteamento de chamadas de emergência é suportado no Canadá da mesma forma que nos Estados Unidos, com a seguinte exceção: todas as chamadas de emergência serão triadas nacionalmente antes de serem transferidas para o PSAP.

Para obter mais informações, consulte [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-direct-routing"></a>Roteamento de chamadas de emergência para Roteamento Direto

A política de roteamento de chamadas de emergência para Roteamento Direto faz referência a um uso PSTN online, que deve ter a configuração de Roteamento Direto apropriada para rotear corretamente as chamadas de emergência para os gateways PSTN apropriados. Em particular, você deve garantir que haja um OnlineVoiceRoute para a cadeia de caracteres de discagem de emergência. Para obter mais informações, consulte [Configure Direct Routing](direct-routing-configure.md). 

> [!NOTE]
> Teams clientes não mais prependam o sinal "+" em frente aos números de emergência; ou seja, +911. Consequentemente, Teams chamadas de emergência não enviarão mais um "+" anterior ao número 911. Certifique-se de que seus padrões de rota de voz reflitam essa alteração.

A capacidade de rotear dinamicamente chamadas de emergência para usuários de Roteamento Direto varia dependendo da rede de chamadas de emergência em um determinado país. Há duas soluções disponíveis:

- [Provedores de Serviços de Roteamento de Emergência (somente eua)](#emergency-routing-service-providers)
- [Aplicativos de Número de Identificação de Local de Emergência](#emergency-location-identification-number-applications)

#### <a name="emergency-routing-service-providers"></a>Provedores de Serviços de Roteamento de Emergência

Nos Estados Unidos, há vários ERSPs (Provedores de Serviços de Roteamento de Emergência) certificados que podem rotear automaticamente chamadas de emergência com base no local do chamador.

- Se um Provedor de Serviços de Roteamento de Emergência estiver integrado a uma implantação de Roteamento Direto, as chamadas de emergência com um local adquirido dinamicamente serão roteados automaticamente para o PSAP (Ponto de Atendimento de Segurança Pública) que atende a esse local.

-  Chamadas de emergência sem um local adquirido dinamicamente são primeiramente triadas para determinar o local atual do usuário antes de conectar a chamada ao centro de expedição apropriado com base no local atualizado.

Para obter mais informações, consulte [Controladores de Borda de Sessão certificados para Roteamento Direto](direct-routing-border-controllers.md).


#### <a name="emergency-location-identification-number-applications"></a>Aplicativos de Número de Identificação de Local de Emergência

Os Controladores de Borda de Sessão (SBCs) podem incluir aplicativos ELIN (Número de Identificação de Local de Emergência). Se um aplicativo ELIN SBC estiver integrado a uma implantação de Roteamento Direto, configure os endereços de emergência e números de telefone associados no aplicativo ELIN e carregue os registros ELIN no banco de dados de chamadas de emergência no PSTN respectivo. Teams locais de emergência com um identificador ELIN devem corresponder àqueles no aplicativo ELIN.

Quando uma chamada de emergência com um local adquirido dinamicamente é roteada para o SBC apropriado, o aplicativo ELIN:

- Analisado o local de emergência do chamador.
- Corresponde o local a um registro ELIN.
- Substitui o número do chamador de emergência pelo número de telefone ELIN.
- Encaminha a chamada para o PSAP que atende a esse local e, em seguida, os despachantes obtém o local do registro ELIN carregado.

Após uma chamada de volta para o número de emergência, o aplicativo ELIN fará a substituição inversa chamada de número para a do chamador de emergência original. 

Para obter mais informações, consulte [Controladores de Borda de Sessão certificados para Roteamento Direto](direct-routing-border-controllers.md).


## <a name="security-desk-notification"></a>Notificação de segurança

A notificação de segurança está disponível com planos de chamadas da Microsoft, Conexão operador e Roteamento Direto.

Você usa uma política de chamada de emergência do Teams (TeamsEmergencyCallingPolicy) para configurar quem deve ser notificado durante uma chamada de emergência e como eles são notificados: somente chat, conferências e mudos, ou conferências e mudos, mas com a capacidade de desmute. Você também pode especificar um número PSTN externo de um usuário ou grupo para chamar e ingressar na chamada de emergência. Observe que a parte PSTN não tem permissão para desatar.

Uma política de chamada de emergência pode ser concedida a uma Teams de usuário, atribuída a um site de rede ou a ambos.  Quando um cliente Teams inicia ou altera uma conexão de rede, Teams executa uma busca do site de rede onde o cliente está localizado:

- Se uma política de chamada de emergência estiver associada a um site de rede, a política de site será usada para configurar a notificação de segurança.

- Se não houver política de chamada de emergência associada ao site ou se o cliente estiver conectado em um site indefinido, a política de chamada de emergência associada à conta de usuário será usada para configurar a notificação de segurança.  

- Se o Teams cliente não conseguir obter uma política de chamada de emergência, o usuário não está habilitado para notificação de segurança.

Durante uma chamada de emergência, um escritório de segurança é conferênciado na chamada e a experiência do usuário do security desk é controlada com base na política de chamada Teams de emergência. Um chat em grupo é iniciado com cada membro do security desk e o local do chamador de emergência é compartilhado por meio de uma notificação de mensagem importante.  Se uma opção de conferência for configurada como parte da política, cada usuário do security desk será chamado como parte da conferência.

    
## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar políticas de chamadas de emergência](manage-emergency-calling-policies.md)
- [Gerenciar políticas de roteamento de chamadas de emergência ](manage-emergency-call-routing-policies.md)
- [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)
- [Atribuir ou alterar um local de emergência para o usuário](assign-change-emergency-location-user.md)
- [Planejar e configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md)
