---
title: Tomar decisões sobre o serviço de Sistema de Telefonia com Planos de Chamadas - Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Escolha entre planos de chamadas e licenciamento, configurar locais de emergência e recursos como correio de voz e identificação de chamadas, adquirir ou transferir números de telefone.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ddc618a4b68c8a620568eba5ae2ed52d17096b30
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232353"
---
# <a name="make-my-service-decisions"></a>Fazer minhas decisões de serviço

Para planejar a implementação técnica do sistema telefônico com planos de chamadas, você deve fazer uma série de decisões de serviço com antecedência para preparar melhor sua organização para implementar uma solução que atenda às suas necessidades comerciais definidas.

## <a name="calling-in-teams"></a>Chamadas no Teams

Com o Microsoft Teams, os usuários podem fazer e receber chamadas telefônicas de ou para a rede telefônica pública comutada (PSTN). Seus usuários podem usar seus próprios números de telefone dedicados para fazer e receber chamadas telefônicas domésticas e internacionais a partir de aplicativos cliente da Team, com recursos avançados que incluem correio de voz.

> [!NOTE]
> O mapa de equipes mais recente para identificar o sistema telefônico da equipe com recursos de plano de chamada no escopo da <https://aka.ms/O365Roadmap>sua implantação pode ser encontrado em.

## <a name="phone-system-in-teams"></a>Sistema telefônico no Teams

Para que os usuários do Team possam fazer e receber chamadas PSTN, eles precisam estar habilitados para o sistema telefônico, um recurso do Office 365.

Para habilitar a conectividade com a PSTN, sua organização pode usar a Microsoft como provedor de serviços de telecomunicações. Por fim, você também terá a opção de "criar seu próprio provedor de serviços de telecomunicações para habilitar a conectividade com a PSTN para o sistema telefônico.

> [!IMPORTANT]
> A capacidade de usar seu próprio provedor de serviços de telecomunicações para o sistema telefônico com a implantação do seu Teams também está disponível com o roteamento direto do sistema telefônico. Para saber mais sobre o roteamento direto, consulte a [orientação de roteamento direto](2-envision-make-my-service-decisions-direct-routing.md).

## <a name="phone-system-with-calling-plans"></a>Sistema telefônico com planos de chamada

Para usar a Microsoft como provedor de serviços de telecomunicações, você precisa obter licenças de plano de chamada e atribuí-las aos usuários do sistema telefônico.

Há dois tipos principais de planos de chamada:

-   Plano de chamadas domésticas

-   Plano de chamadas domésticas e internacionais

Cada tipo de plano de chamada aloca um certo número de minutos de chamadas por mês para cada usuário que tenha sido atribuído à licença. Quando a alocação de minutos de chamada for esgotada, o usuário não poderá fazer chamadas de saída, exceto para chamadas de emergência, até o ciclo de cobrança do próximo mês. Se você quiser que os usuários possam continuar a fazer uma chamada de saída, mesmo depois de terem esgotado a alocação dos minutos de chamadas, ou para permitir que os usuários que têm um plano de chamadas domésticas façam chamadas internacionais, você pode configurar créditos de comunicações para a sua organização.

<!--ENDOFSECTION-->

## <a name="availability-of-calling-plans"></a>Disponibilidade de planos de chamada

Antes de planejar a implementação de planos de chamada no Microsoft Teams, verifique se o serviço planos de chamadas está disponível na sua área revisando a [disponibilidade de país e região para videoconferências e planos de chamadas](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

> [!IMPORTANT]
> Devido a restrições legais, para que os planos de chamadas sejam disponibilizados para organizações multinacionais, o contrato para assinaturas do Office 365 deve ser baseado em um país ou região onde o serviço planos de chamada está disponível, ou onde o serviço planos de chamada pode ser Comprei.

> [!NOTE]
> Se os planos de chamada não estiverem disponíveis em sua área, você poderá usar o [Roteamento direto do sistema telefônico](2-envision-make-my-service-decisions-direct-routing.md) para permitir que os usuários usem o Microsoft Teams com recursos PSTN.

Depois de confirmar que a sua organização pode obter o serviço de planos de chamada, Compile a lista de locais de usuários ou escritórios em que você implementará o serviço de planos de chamadas, com base na lista de países e regiões disponíveis.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida quais locais ou escritórios do usuário Você implementará o serviço de planos de chamadas.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documentar os locais do usuário ou os escritórios a serem habilitados para o serviço de planos de chamada.</li></ul>|

> [!TIP]
> Veja a seguir um exemplo de um sistema telefônico com planos de chamada na lista de habilitação de sites.
> 
> | **Office**                     | **Local**   | **Serviço do sistema telefônico** |
> |--------------------------------|----------------|--------------------------|
> | One Epping Road                | Austrália      | Serviço PSTN herdado |
> | 100 Alma Road             | Hong Kong SAR  | Roteamento Direto do Sistema Telefônico |
> | One Marina Boulevard           | Cingapura      | Roteamento Direto do Sistema Telefônico |
> | 32 London Bridge Street        | Reino Unido | Sistema telefônico com planos de chamada |
> | 39 quai du Président Roosevelt | França         | Sistema telefônico com planos de chamada |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>Números de telefone e locais de emergência

Com planos de chamada no Office 365, todos os usuários de sua organização precisam ter um número de telefone exclusivo de discagem direta (DID) e um endereço de emergência validado correspondente. Revise [gerenciar números de telefone de voz na nuvem](2-envision-make-my-service-decisions-phone-system.md#manage-cloud-voice-telephone-numbers) para planejar a aquisição de número de telefone para a implementação dos seus planos de chamadas.

Quando estiver configurando números de telefone para planos de chamadas, você deverá atribuir um endereço de emergência a cada número de telefone antes de atribuir o número a um usuário. Isso é necessário para dar suporte a chamadas de emergência. O endereço de emergência deve ser validado para garantir que ele esteja no formato correto a ser usado por serviços de resposta de emergência.

> [!IMPORTANT]
> A chamada de serviços de emergência funciona de forma diferente no serviço de planos de chamada do que nos serviços telefônicos tradicionais. É importante que você compreenda essas diferenças e as comunique a todos os usuários. Consulte [termos e condições para chamadas de emergência](emergency-calling-terms-and-conditions.md) para obter mais detalhes.

Além de fornecer um endereço de emergência validado, você pode definir locais de emergência e associá-los com o endereço de emergência validado para dar um local mais exato em um endereço. Normalmente, um local de emergência consiste no número de um edifício, andar, bloco ou o número do escritório onde o usuário está localizado.

Para saber mais sobre locais de emergência em relação a planos de chamada, consulte os seguintes artigos:

-   [O que são locais e endereços de emergência e encaminhamento de chamadas?](what-are-emergency-locations-addresses-and-call-routing.md)

-   [Termos e condições da chamada de emergência](emergency-calling-terms-and-conditions.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decidir a granularidade das informações de localização de emergência a serem coletadas para locais de usuários ou escritórios em escopo para a implementação de planos de chamada.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente o endereço de emergência e locais de emergência detalhados de cada local de usuário ou escritório em escopo para a implementação de planos de chamada.</li></ul>|

> [!TIP]
> Você pode usar o modelo a seguir para documentar os detalhes dos números de telefone e dos detalhes do local de emergência.
> 
> |Usuário |Localização e endereço de emergência |Número de telefone |
> |-----|-------------------------------|-------------|
> |Emily Braun |Rua da ponte 1034/32 Londres, Londres, SE1, Reino Unido |+ 44 23 4567 8901 |
> |Lidia Holloway |Rua da ponte 1065/32 Londres, Londres, SE1, Reino Unido |+ 44 23 4567 89112 |
> |Lahr de Louis |Rua da ponte 1023/32 Londres, Londres, SE1, Reino Unido |+ 44 23 4567 8921 |
> |Marcel Beauchamp |07E15D/39 quaI du Président Roosevelt, 92130 Issy-les-Moulineaux, França | TBA |
> |Rachelle Cormier |07N15D/39 quaI du Président Roosevelt, 92130 Issy-les-Moulineaux, França | TBA |
> |Isabell Potvin |07F05E/39 quaI du Président Roosevelt, 92130 Issy-les-Moulineaux, França | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>Caixa postal

O correio de voz na nuvem, da plataforma de correio de voz do Azure, oferece suporte a depósitos de correio de voz para trocar caixas de correio somente e não é compatível com sistemas de email

Por padrão, o correio de voz na nuvem funciona com o Exchange Online; no entanto, ele tem uma versão do Exchange local e um modelo de implantação compatíveis com o Exchange para permitir a entrega de mensagens de correio de voz para caixas de correio de usuário na implantação do Exchange local.

O correio de voz na nuvem inclui a transcrição de correio de voz, que é habilitada para todos os usuários da sua organização por padrão. Suas necessidades comerciais podem exigir que você desabilite a transcrição de correio de voz para usuários específicos ou todos em toda a organização. Se sua organização decidir manter a transcrição de correio de voz habilitada, você também precisará considerar se o mascaramento de obscenidades da transcrição de correio de voz precisa estar habilitado. Para obter mais detalhes, consulte [definindo políticas de correio de voz em sua organização](set-up-phone-system-voicemail.md) .

>[!NOTE]
> Um mecanismo de fallback foi implementado para que o correio de voz na nuvem possa reenviar mensagens usando SMTP, o que significa que os usuários que têm uma caixa de correio em um sistema de email de terceiros receberão suas mensagens de correio de voz. Esse mecanismo não inclui o tempo de atividade do serviço garantido ou outros recursos de correio de voz, como alterar a saudação da caixa postal.

Para obter mais informações sobre o correio de voz em uma implementação de sistema telefônico, consulte [sistema telefônico com planos de chamada](calling-plan-landing-page.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se você habilitará o correio de voz na nuvem na implementação dos seus planos de chamada.</li><li>Se você estiver usando o Exchange local e a implantação existente não atender aos requisitos para dar suporte ao correio de voz na nuvem, escolha entre as opções disponíveis (atualização e configuração para suporte ao correio de voz na nuvem, migrar para o Exchange Online ou aproveitar o fallback mecanismo descrito anteriormente).</li><li>Decida se você habilitará ou desabilitará a transcrição de correio de voz e o mascaramento de obscenidades da transcrição de correio de voz em toda a organização ou para usuários específicos.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Se aplicável, documente os pontos de decisão do Exchange para dar suporte ao correio de voz na nuvem.</li><li>Se você habilitar/desabilitar o correio de voz, a transcrição de correio de voz e o mascaramento de obscenidades da transcrição somente para usuários específicos, documente a lista de usuários.</li></ul>|

> [!TIP]
> Os detalhes do correio de voz na nuvem para o sistema telefônico com a implementação de planos de chamada podem ser documentados da seguinte maneira.
> 
> |Usuário |Caixa de correio do Exchange |Habilitar correio de voz? |Transcrição do correio de voz |Máscara de obscenidade de transcrição de correio de voz |
> |------------------|------------------|-------------------|----------|----------|
> |Emily Braun      |Online      |Sim |Habilitado |Habilitado |
> |Lidia Holloway   |Online      |Sim |Habilitado |Desabilitado |
> |Lahr de Louis       |Local |Sim |Habilitado |Habilitado |
> |Marcel Beauchamp |Local |Sim |Desabilitado |N/D |
> |Rachelle Cormier |Online      |Sim |Desabilitado |N/D |
> |Isabell Potvin   |Local |Sim |Desabilitado |N/D |

<!--ENDOFSECTION-->

## <a name="calling-identity"></a>Identidade de chamada

Por padrão, todas as chamadas de saída usam o número de telefone atribuído como identidade de chamada (identificação de chamadas). O destinatário da chamada pode identificar o autor da chamada rapidamente e decidir se deseja aceitar ou rejeitar a chamada. Em alguns casos, há requisitos comerciais legítimos para mascarar a identificação de chamadas para proteger a identidade dos chamadores usando o número da linha principal do Office — geralmente é um número de serviço atendido pela configuração do atendedor automático (como identificação de chamada) ou para bloquear a identificação de chamadas apresentação totalmente.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se a manipulação de identificação de chamadas é necessária para a implementação dos seus planos de chamada.</li><li>Se aplicável, decida quais tipos de manipulação de identificação de chamadas (máscara com número de serviço ou anonimato) serão implementadas.</li><li>Se aplicável, decida quais usuários exigem a manipulação de identificação de chamadas e o tipo de manipulação de identificação de chamadas a serem atribuídas a cada usuário.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente os usuários que receberão a manipulação de identificação de chamadas e o tipo de manipulação de identificação de chamadas a atribuir.</li></ul>|

> [!TIP]
> Veja a seguir um exemplo de documentação de detalhes da máscara de identificação de chamadas.
> 
> |Usuário  |Habilitar o mascaramento da identificação de chamadas de saída  |Tipo de mascaramento da identificação de chamadas  |Permitir substituição pelo usuário  | Habilitar o mascaramento da identificação de chamadas de entrada  |
> |---------|---------|---------|---------|---------|
> |Emily Braun|Não|N/D|Sim|Não|
> |Lidia Holloway|Sim|Número do serviço (OrgAA, + 44 20 7946 0000)|Não|Sim|
> |Lahr de Louis|Não|N/D|Sim|Não|
> |Marcel Beauchamp|Sim|Número de serviço (OrgAA, TBA)|Não|Sim|
> |Rachelle Cormier|Sim|Anonimato|Sim|Não|
> |Isabell Potvin|Sim|Número de serviço (OrgAA, TBA)|Não|Sim|

<!--ENDOFSECTION-->

## <a name="licensing-for-cloud-voice-capabilities"></a>Licenciamento para recursos de voz na nuvem

Conferência de áudio e sistema telefônico são recursos do Office 365. Eles podem ser licenciados separadamente como serviços complementares para clientes existentes que têm planos de assinatura do Office 365 E3 ou E1; Eles já estão incluídos como parte do plano de assinatura do Office 365 e5.

Planos de chamada é um complemento ao recurso do sistema telefônico no Office 365, portanto, você deve ter um sistema telefônico licenciado habilitado para usar planos de chamada.

Para dar suporte a outras conferências de áudio e planos de chamadas, os casos de uso (chamadas discadas internacionais, chamadas externas após o plano de chamada e as atribuições de minutos esgotadas e assim por diante), você pode configurar créditos de comunicações para sua organização.

## <a name="licensing-for-calling-plans"></a>Licenciamento para planos de chamada

Se a sua organização pretende usar a Microsoft como provedor de serviços de telecomunicações, você precisará obter Complementos de plano de chamada apropriados para os requisitos comerciais dos seus usuários. Geralmente, nem todos os usuários de uma organização precisam fazer chamadas internacionais, para que você possa provisionar a maioria dos usuários com licenças de plano de chamadas domésticas.

Há dois tipos de licenças de plano de chamada:

-   Plano de Chamadas Domésticas

-   Plano de Chamadas Internacionais e Domésticas

> [!NOTE]
> O que é considerado "doméstico" para um usuário específico é determinado pelo local de uso atribuído do Office 365 atribuído a ele.

Cada tipo de plano de chamada fornece uma atribuição de minutos de chamada que os usuários podem usar por mês, seja para fazer chamadas domésticas ou chamadas internacionais. O plano de chamadas domésticas custa menos em comparação ao plano de chamadas internacionais e nacionais.

A flexibilidade de assinatura e atribuição do tipo de plano de chamada mais apropriado para requisitos comerciais de usuários individuais ajuda sua organização a controlar os custos da implementação de seus planos de chamadas.

Para cada locatário do Office 365, o número combinado de minutos de chamadas são agrupados por país ou região e por tipo de plano de chamada. Quando o limite de minutos de chamadas mensais para o locatário for atingido, o serviço de planos de chamada (exceto chamadas de emergência) será suspenso pelo restante do mês. O serviço planos de chamada será retomado automaticamente no primeiro dia do próximo mês do calendário.

Você pode configurar créditos de comunicações para suas organizações para permitir que os usuários façam chamadas após a reserva dos minutos de chamada sem ter que esperar até o próximo ciclo de cobrança do mês. Além disso, os créditos de comunicação dão aos usuários a atribuição do plano de chamadas domésticas a capacidade de fazer chamadas internacionais, que são cobradas por meio de um modelo "pague por minuto".

Para saber mais sobre o sistema telefônico e planos de chamada, consulte os seguintes artigos:

-   [Sistema Telefônico](https://products.office.com/en-us/skype-for-business/phone-system)

-   [Planos de chamadas](https://products.office.com/en-us/skype-for-business/calling-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Se a sua organização não tiver a licença do sistema de telefonia necessária, decida se você adquirirá a licença do sistema de telefone, faça o acompanhamento de suas assinaturas existentes do Office 365 ou da aquisição do serviço de complemento do sistema telefônico.</li><li>Decida quais usuários exigem uma licença do plano de chamadas domésticas e quais são necessárias uma licença de plano de chamadas doméstica e internacional.</li><li>Decida se você precisará de créditos de comunicações para a implementação dos seus planos de chamadas.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente os grupos de divisão, departamento, escritório ou usuário você atribuirá uma licença de sistema telefônico com plano de chamadas domésticas ou plano de chamadas doméstica e internacional.</li></ul>|

> [!TIP]
> Você pode usar o exemplo a seguir para documentar a atribuição de licença do sistema telefônico com usuários de planos de chamada.
> 
> |Usuário |Escritório |Licença do Office 365 |Plano de chamada |
> |----|----|----|----|
> |Emily Braun |32 London Bridge Street |Office 365 E5 |Plano de Chamadas Internacionais e Domésticas |
> |Lidia Holloway |32 London Bridge Street |Office 365 E5 |Plano de Chamadas Domésticas |
> |Lahr de Louis |32 London Bridge Street |Office 365 E5 |Plano de Chamadas Domésticas |
> |Marcel Beauchamp |39 quai du Président Roosevelt |Office 365 E3, complemento do sistema de telefonia |Plano de Chamadas Domésticas |
> |Rachelle Cormier |39 quai du Président Roosevelt |Office 365 E5 |Plano de Chamadas Internacionais e Domésticas |
> |Isabell Potvin |39 quai du Président Roosevelt |Office 365 E3, complemento do sistema de telefonia |Plano de Chamadas Domésticas |

<!--ENDOFSECTION-->

## <a name="communications-credits"></a>Créditos de Comunicação

Usando créditos de comunicações, os usuários podem discar de uma reunião de conferência de áudio para adicionar outra pessoa de qualquer lugar do mundo (fora do país de origem do organizador da reunião). Você pode configurar créditos de comunicações para sua organização para permitir que os usuários façam chamadas de saída depois de terem esgotado a atribuição de minutos de chamadas, sem precisar esperar até o ciclo de cobrança do próximo mês. Além disso, os créditos de comunicação dão aos usuários atribuídos ao plano de chamadas domésticas a capacidade de fazer chamadas internacionais, que são então cobradas por meio de um modelo "pay-per-minute".

A primeira consideração a fazer ao implementar os Créditos de Comunicação é decidir o valor inicial de fundos a serem comprados. Se a sua organização optar por usar o recurso de recarga automática, você determinará o valor ideal medindo o uso real. Monitore o uso dos créditos de comunicações ao longo do tempo e ajuste o valor da recarga conforme necessário.

Para a implementação de seus planos de chamadas, você pode controlar o uso de créditos de comunicações por usuário, o que o ajuda a garantir que você tenha atribuído esses créditos de acordo com suas necessidades de negócios.

Para saber mais sobre os créditos de comunicações, confira [o que são créditos de comunicações?](what-are-communications-credits.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se você precisa de créditos de comunicações para a sua conferência de áudio ou planos de chamadas.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente os grupos de divisão, departamento, escritório ou usuário para os quais você habilitará créditos de comunicações.</li><li>Documente seu plano de créditos de comunicações para a sua implementação de áudio ou planos de chamadas.</li></ul>|

> [!TIP]
> Use o exemplo a seguir para documentar a lista de atribuições de créditos de comunicações para usuários de planos de chamada.
> 
> |Usuário |Escritório |Plano de chamada |Créditos de Comunicação |
> |----|----|----|----|
> |Emily Braun |32 London Bridge Street |Plano de Chamadas Internacionais e Domésticas |Habilitado |
> |Lidia Holloway |32 London Bridge Street |Plano de Chamadas Domésticas |Desabilitado |
> |Lahr de Louis |32 London Bridge Street |Plano de Chamadas Domésticas |Habilitado |
> |Marcel Beauchamp |39 quai du Président Roosevelt |Plano de Chamadas Domésticas |Desabilitado |
> |Rachelle Cormier |39 quai du Président Roosevelt |Plano de Chamadas Internacionais e Domésticas |Habilitado |
> |Isabell Potvin |39 quai du Président Roosevelt |Plano de Chamadas Domésticas |Desabilitado |

<br>

> [!TIP]
> Seus números de planejamento de créditos de comunicações podem ser documentados como no exemplo a seguir.
>
> |         |         |
> |---------|---------|
> |Valor inicial|US$ 1.000|
> |Valor do gatilho|US$ 400|
> |Valor da recarga automática|TBA|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Gerenciar números de telefone de voz na nuvem

Se você implementar o sistema telefônico ao trazer seu provedor de serviços de telecomunicações, o gerenciamento de números de telefone permanecerá como está.

Para implementações de áudio e planos de chamadas, você pode optar por adquirir novos números de telefone ou transferir (porta) números de telefone existentes.

Para permitir que os usuários disquem números de telefone da maneira como estão acostumados, como omitir códigos de área para chamadas locais, omitindo o código de país para chamadas domésticas ou usando a discagem de curto-dígito ao executar a discagem de conferência ou ligar para outros usuários da organização, Você pode configurar um plano de discagem personalizado e atribuí-lo a usuários.

## <a name="acquire-new-telephone-numbers"></a>Adquirir novos números de telefone

Os dois tipos de números de telefone nas soluções Microsoft Cloud Voice são:

-   Números de assinante (usuário), que podem ser atribuídos a usuários em sua organização.

-   Números de serviço, disponíveis como números de serviço de chamada tarifada e gratuita, que têm capacidade de chamada simultânea maior do que os números de assinantes e podem ser atribuídos a serviços como videoconferências, atendedores automáticos ou filas de chamadas.

Para obter mais informações sobre os tipos de números de telefone, consulte [diferentes tipos de números de telefone usados para planos de chamada](different-kinds-of-phone-numbers-used-for-calling-plans.md).

A contagem total de números de telefone que você pode obter depende do tipo de número de telefone e do número de licenças que você comprou e atribuiu aos seus usuários.

Para obter mais informações sobre a contagem total de números de telefone que você pode obter, consulte quantos [números de telefone você pode obter?](how-many-phone-numbers-can-you-get.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida quais são os locais do usuário ou os escritórios nos quais novos números de telefone serão adquiridos da Microsoft.</li><li>Decida o tipo de número de telefone a ser adquirido da Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documentar os locais do usuário ou os escritórios nos quais novos números de telefone serão adquiridos da Microsoft.</li><li>Documentar o tipo de número de telefone a ser adquirido da Microsoft.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Transferir números de telefone existentes

Se sua organização quer transferir (ou porta) números de telefone existentes para a Microsoft, você pode fazer isso enviando uma solicitação de pedido de portabilidade à Microsoft.

Você pode transferir todos os seus números de telefone existentes ao mesmo tempo (porta completa) e, em alguns mercados, você pode transferir um subconjunto de seus números de telefone existentes (porta parcial). Uma porta parcial pode ser útil em casos em que você apenas deseja mover gradualmente os usuários para o sistema telefônico com planos de chamada.

Um único pedido de portabilidade só pode transferir os números de telefone para um único tipo de número de telefone. Se você precisar transferir alguns números de telefone como números de assinante e alguns como números de serviço, recomendamos que primeiro conclua a transferência para a Microsoft e, em seguida, realize a conversão assim que os números estiverem no controle da Microsoft.

Como alternativa (se houver suporte para a porta parcial), você pode enviar várias solicitações de porta, uma solicitação de porta por vez. No entanto, essa abordagem alternativa prolongará seu contrato com o provedor de serviços de telecomunicações existente.

Portabilidade de número de telefone é um tópico complexo e requer planejamento, coordenação e gerenciamento adequado das expectativas dos seus participantes. Para saber mais, confira os seguintes artigos:

-   [Transferir números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md)

-   [Perguntas comuns sobre transferência de números de telefone](transferring-phone-numbers-common-questions.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida quais são os locais do usuário ou os escritórios nos quais os números de telefone existentes serão transferidos para a Microsoft.</li><li>Decida o tipo de número de telefone a ser transferido para a Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documentar os locais do usuário ou os escritórios nos quais os números de telefone existentes serão transferidos para a Microsoft.</li><li>Documentar o tipo de número de telefone a ser transferido para a Microsoft.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Planos de discagem

Um plano de discagem no recurso do sistema de telefonia do Office 365 é um conjunto de regras de normalização que traduz os números de telefone discada em um formato alternativo (geralmente o formato E. 164) para autorização de chamadas e encaminhamento de chamadas. O serviço de audioconferência usa os mesmos recursos usados pelo sistema telefônico para converter números de telefone discados em cenários de discagem de conferência (por exemplo, convidar participantes via PSTN e discagem, recurso "ligar para mim").

No recurso do sistema de telefonia do Office 365, há dois tipos de planos de discagem:

-   **Plano de discagem do serviço:** Esse é o plano de discagem padrão que é aplicado aos usuários com base no local de uso do Office 365 e não pode ser modificado.

-   **Plano de discagem do locatário:** Esse é um plano de discagem personalizável dentro de um locatário, que é dividido em dois tipos:

    -   **Locatário-plano de discagem global:** O plano de discagem que se aplica a todos os usuários no locatário.

    -   **Locatário-plano de discagem do usuário:** O plano de discagem que se aplica somente a usuários específicos.

O plano de discagem efetivo atribuído a usuários é a combinação do plano de discagem de serviço (com base no local de uso do Office 365 de um usuário) e o plano de discagem do locatário (que pode ser um plano de discagem global do locatário ou um plano de discagem do usuário do locatário).

A ![tabela mostra três combinações de planos de discagem de serviço e locatário.] A (media/audio_conferencing_image8.png "tabela mostra três combinações de planos de discagem de serviço e locatário.")

> [!IMPORTANT]
> Pode haver no máximo 25 regras de normalização em cada plano de discagem de locatário; Portanto, é importante evitar a duplicação de regras de normalização que já estão disponíveis como parte do plano de discagem do serviço.

Para obter mais informações sobre os planos de discagem, confira [O que são os planos de discagem?](what-are-dial-plans.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se sua organização requer planos de discagem personalizados (requisitos comerciais, requisitos de adoção e assim por diante).</li><li>Se aplicável, decida o escopo do plano de discagem do locatário (locatário-global ou locatário-User) para dar suporte a seus requisitos para planos de discagem personalizados.</li><li>Se aplicável, decida os planos de discagem de locatário que você criará para dar suporte a locais de usuário ou escritórios em escopo para a implementação de voz na nuvem.</li><li>Se aplicável, decida quais usuários exigem um plano de discagem personalizado e o plano de discagem do locatário a ser atribuído para cada usuário.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente os planos de discagem personalizados e as regras de normalização associadas a serem configuradas como parte da implementação de voz na nuvem.</li><li>Documente os usuários aos quais será atribuído um plano de discagem personalizado e o plano de discagem de locatário a ser atribuído para cada usuário.</li></ul>|

> [!TIP]
> Se for aplicável ao seu projeto, você poderá usar o modelo a seguir para documentar as configurações de plano de discagem de locatário.
> 
> |Nome do plano de discagem de locatário<br>_Descrição_  |Nome das regras de normalização<br>_Descrição_  |Padrão<br>Conversão<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_One Epping Road North Ryde, NSW, AU Dial Plan_|**AU-NSW-NorthRyde-OER-Internal**<br>_Número interno (x7000 - x7999) para o escritório de One Epping Road, North Ryde, NSW, Austrália_|^ (7 \ d{3}) $<br>+6125550$1<br>True|
> ||**AU-NSW-Local**<br>_Normalização do número local para NSW, Austrália_|^ ([2-9] \d{7}) $<br>+612$1<br>False|
> ||**AU-TollFree**<br>_Normalização de número gratuito na Austrália_|^ (1 [38] \d{4,8}) \d * $<br>+61$1<br>False|
> ||**AU-Service**<br>_Normalização de número de serviço na Austrália_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>False|
> |**SG-Singapore-OMB**<br>_OMB Singapore, SG Dial Plan_|**SG-OMB-Internal**<br>_Número interno (x8000 â € "x8999) para OMB Office, Cingapura_|^ (8 \ d{3}) $<br>+656888$1<br>True|
> ||**SG-TollFree**<br>_Normalização de número gratuito em Cingapura_|^ (1? 800 \ d{7}) \d * $<br>+65$1<br>False|
> ||**SG-Service**<br>_Normalização de número de serviço em Cingapura_|^ (1 \ d{3,4}\|9 \ d{2}) $<br>$1<br>False|
> |**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux, France Dial Plan_|**FR-39qdPR-Internal**<br>_Número interno (x7000 â € "x7999) para 39 quaI du Président Roosevelt Office, Issy-les-Moulineaux, França_|^ (7 \ d{3}) $<br>+3319999$1<br>True|
> ||**FR-TollFree**<br>_Normalização de número gratuito na França_|^ 0? (80 \ d{7}) \d * $<br>+33$1<br>False|
> ||**FR-Service**<br>_Normalização de número de serviço na França_|^ (1 \ d{1,2}\|11 [68] \d{3}\|10 \ d{2}\|3 \ d{3}) $<br>$1<br>False|

<br>

> [!TIP]
> O modelo de exemplo a seguir pode ser utilizado para documentar atribuições de planos de discagem para dar suporte ao seu projeto:
>
> |Usuário  |Escritório  |Tipo do plano de discagem  |Nome do plano de discagem  |
> |---------|---------|---------|---------|
> |Adele Vance|One Epping Road|Plano de discagem para locatários|AU-NSW-NorthRyde-OER|
> |Alex Wilber|One Epping Road|Plano de discagem para locatários|AU-NSW-NorthRyde-OER|
> |Ben Walters|One Epping Road|Plano de discagem para locatários|AU-NSW-NorthRyde-OER|
> |Christie Cline|One Marina Boulevard|Plano de discagem para locatários|SG-Singapore-OMB|
> |Debra Berger|One Marina Boulevard|Plano de discagem para locatários|SG-Singapore-OMB|
> |Lee Gu|One Marina Boulevard|Plano de discagem para locatários|SG-Singapore-OMB|
> |Emily Braun|32 London Bridge Street|Plano de discagem para serviço|N/A|
> |Lidia Holloway|32 London Bridge Street|Plano de discagem para serviço|N/A|
> |Lahr de Louis|32 London Bridge Street|Plano de discagem para serviço|N/A|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Plano de discagem para locatários|FR-Paris-Issy-30qdPR|
> |Rachelle Cormier|39 quai du Président Roosevelt|Plano de discagem para locatários|FR-Paris-Issy-30qdPR|
> |Isabell Potvin|39 quai du Président Roosevelt|Plano de discagem para locatários|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Decisões de serviço de documento 

Use as informações das seções anteriores deste artigo para documentar suas decisões de serviço. Em geral, esta documentação conterá as seguintes seções principais:

-   Sistema telefônico com planos de chamada lista de habilitação de sites

-   Atribuição de licença para sistema telefônico com planos de chamada usuários

-   Número de planejamento de Créditos de Comunicação

-   Aquisição de número de telefone, números de telefone e detalhes de localização de emergência

-   Detalhes da configuração do correio de voz

-   Detalhes da configuração da máscara de identificação de chamadas

-   Planos de discagem para locatários

-   Atribuições de planos de discagem

<!--ENDOFSECTION-->