---
title: Tomar decisões sobre o serviço de Sistema de Telefonia com Planos de Chamadas - Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Escolha de chamar planos e licenciamento, configure locais de emergência e recursos, como ID do chamador e de caixa postal, adquirir ou transferir os números de telefone.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 513519e95951676dc9e5a9b69d2fe3c5ace2824b
ms.sourcegitcommit: 16b3ee042e8f0efacc92811ff8be093b240df9fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/25/2019
ms.locfileid: "33304833"
---
# <a name="make-my-service-decisions"></a>Tomar decisões meu serviço

Para planejar a implementação técnica do sistema telefônico com planos de chamada, você deve fazer uma série de decisões de serviço antes do tempo para melhor preparar sua organização para implementar uma solução que atende aos seus requisitos de negócios definidas.

## <a name="calling-in-teams"></a>Chamando em equipes

Com Teams da Microsoft, os usuários podem fazer ou receber chamadas telefônicas para ou da rede telefônica pública comutada (PSTN). Seus usuários podem usar seus próprios números de telefone dedicado para fazer e receber chamadas telefônicas de nacionais e internacionais de aplicativos do cliente de equipes, com recursos avançados que incluem a caixa postal.

> [!NOTE]
> O mapa de equipes mais recente para identificar o sistema telefônico de equipes com recursos de chamada planejar no escopo para sua implantação pode ser encontrada em <https://aka.ms/O365Roadmap>.

## <a name="phone-system-in-teams"></a>Sistema telefônico em equipes

Para usuários de equipes poder fazer e receber chamadas PSTN, elas precisam ser habilitados para o sistema telefônico, um recurso do Office 365.

Para habilitar a conectividade à PSTN, sua organização pode usar o Microsoft como seu provedor de serviços de telecomunicações. Eventualmente, você também terá a opção de provedor de serviços de telecomunicações "trazer suas próprias" para habilitar a conectividade PSTN para o sistema telefônico.

> [!IMPORTANT]
> A capacidade de usar seu próprio provedor de serviços de telecomunicações para o sistema telefônico com sua implantação de equipes também está disponível com o roteamento direto de sistema do telefone. Para saber mais sobre o roteamento direto, revise as [orientações de roteamento direto](2-envision-make-my-service-decisions-direct-routing.md).

## <a name="phone-system-with-calling-plans"></a>Sistema telefônico com a chamada de planos

Para usar o Microsoft como seus telecomunicações provedor de serviço, você precisará obter licenças chamar planejar e atribuí-las aos usuários de seu sistema telefônico.

Existem dois tipos principais de planos de chamada:

-   Plano de chamada doméstico

-   Plano de chamada nacionais e internacional

Cada tipo de chamada plano aloca um determinado número de minutos de chamada por mês para cada usuário que tenha sido atribuído a licença. Quando for esgotada a alocação de minutos de chamada, o usuário não será possível fazer chamadas de saída — exceto para chamadas de emergência — até que o ciclo de cobrança do próximo mês. Se você quiser que os usuários possam continuar a fazer chamadas de saída, mesmo depois que eles já esgotada sua alocação de minutos de chamada, ou para permitir que os usuários que têm um plano de chamada doméstico chamadas internacionais, você pode configurar créditos de comunicações para sua organização.

<!--ENDOFSECTION-->

## <a name="availability-of-calling-plans"></a>Disponibilidade dos planos de chamada

Antes de planejar a implementação de chamar planos em equipes, verificar se o serviço de planos de chamada está disponível na sua área examinando a [disponibilidade do país e região para conferência de áudio e planos de chamada](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

> [!IMPORTANT]
> Devido a restrições legais, para chamar planos esteja disponível para organizações multinacionais, o contrato para assinaturas do Office 365 deve ser baseado em um país ou região onde o serviço de planos de chamada está disponível ou onde o serviço de planos de chamada pode ser adquirida.

> [!NOTE]
> Se os planos de chamada não estão disponíveis na sua área, você pode usar o [Roteamento direto de sistema do telefone](2-envision-make-my-service-decisions-direct-routing.md) para habilitar os usuários usando equipes com recursos PSTN.

Depois de confirmar que sua organização pode obter o serviço chamando planos, compile a lista de locais do usuário ou de onde você vai Implementando o serviço de planos de chamada, com base na lista de países disponíveis e regiões de escritórios.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida qual usuário locais ou escritórios você implementará o ato de chamar planos de serviço no.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente os locais do usuário ou escritórios estar habilitado para o serviço de planos de chamada.</li></ul>|

> [!TIP]
> Abaixo é um exemplo de um sistema telefônico com lista planos de chamada de habilitação de site.
> 
> | **Office**                     | **Local**   | **Serviço de sistema telefônico** |
> |--------------------------------|----------------|--------------------------|
> | One Epping Road                | Austrália      | Serviço PSTN herdado |
> | 100 Alma Road             | Hong Kong SAR  | Roteamento Direto do Sistema Telefônico |
> | One Marina Boulevard           | Cingapura      | Roteamento Direto do Sistema Telefônico |
> | 32 London Bridge Street        | Reino Unido | Sistema telefônico com a chamada de planos |
> | 39 quai du Président Roosevelt | França         | Sistema telefônico com a chamada de planos |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>Números de telefone e locais de emergência

Com a chamada estiver planejando no Office 365, cada usuário na sua organização deve ter um inward direto exclusivo discando o número de telefone (DID) e um endereço de emergência validado correspondente. Rever os [números de telefone de voz de nuvem de gerenciar](2-envision-make-my-service-decisions-phone-system.md#manage-cloud-voice-telephone-numbers) para planejar a aquisição de número de telefone para sua implementação chamando planos.

Quando você estiver configurando os números de telefone para planos de chamada, você deve atribuir um endereço de emergência para cada número de telefone antes de atribuir o número a um usuário. Isso é necessário para dar suporte a chamadas de emergência. O endereço de emergência deve ser validado para garantir que ele está no formato correto a ser usado pelos serviços de resposta de emergência.

> [!IMPORTANT]
> Serviços de emergência chamar funciona de modo diferente no serviço chamando planos que nos serviços de telefonia tradicional. É importante que você entenda essas diferenças e comunicar-se a todos os usuários. Para obter mais detalhes, consulte [Emergency chamar termos e condições](emergency-calling-terms-and-conditions.md) .

Além de fornecer um endereço de emergência validado, você pode definir o locais de emergência e associá-los com o endereço de emergência validado dar um local mais exato dentro de um endereço. Normalmente, um local de emergência consiste no número de um edifício, andar, bloco ou o número do escritório onde o usuário está localizado.

Para saber mais sobre os locais de emergência em relação à chamada planos, revise os seguintes artigos:

-   [O que são locais e endereços de emergência e encaminhamento de chamadas?](what-are-emergency-locations-addresses-and-call-routing.md)

-   [Termos e condições da chamada de emergência](emergency-calling-terms-and-conditions.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida a granulação das informações de local de emergência a serem coletados para os locais do usuário ou de escritórios em escopo para a implementação de planos de chamada.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>O endereço de emergência detalhado e locais de emergência para cada local do usuário ou do office no escopo para a implementação de planos de chamar do documento.</li></ul>|

> [!TIP]
> Você pode usar o modelo a seguir para documentar os detalhes dos números de telefone e detalhes do local de emergência.
> 
> |Usuário |Endereço e o local de emergência |Número de telefone |
> |-----|-------------------------------|-------------|
> |Emily Braun |Reino Unido de 1034/32 Londres ponte rua, London, SE1, |+ 44 23 4567 8901 |
> |Lidia Holloway |Reino Unido de 1065/32 Londres ponte rua, London, SE1, |+ 44 23 4567 89112 |
> |Louis Lahr |Reino Unido de 1023/32 Londres ponte rua, London, SE1, |+ 44 23 4567 8921 |
> |Marcel Beauchamp |Quai 07E15D/39 du Président Roosevelt, Issy 92130-les-Moulineaux, França | TBA |
> |Rachelle Cormier |Quai 07N15D/39 du Président Roosevelt, Issy 92130-les-Moulineaux, França | TBA |
> |Isabell Potvin |Quai 07F05E/39 du Président Roosevelt, Issy 92130-les-Moulineaux, França | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>Caixa postal

Caixa postal de nuvem, possibilitada pela serviços de caixa postal do Azure, suporta depósitos de correio de voz em somente caixas postais do Exchange e não oferece suporte a sistemas de email de terceiros.

Por padrão, a caixa postal de nuvem funciona com o Exchange Online; No entanto ele tenha um mínimo com suporte Exchange local versão e implantação modelo para permitir a entrega de mensagens de caixa postal para caixas de correio do usuário na implantação do Exchange local.

Caixa postal de nuvem inclui transcrições de caixa postal, que é ativada por padrão para todos os usuários em sua organização. Suas necessidades de negócios podem exigir que você desative as transcrições de caixa postal para usuários específicos ou todos em toda a organização. Se a sua organização decidir manter a transcrição do correio de voz habilitada, você precisa considerar também se mascaramento de obscenidades transcrição caixa postal precisa estar habilitado. Consulte [definir políticas de caixa postal na sua organização](set-up-phone-system-voicemail.md) para obter mais detalhes.

>[!NOTE]
> Um mecanismo de fallback foi implementado para que a caixa postal de nuvem pode reenviar mensagens usando o SMTP, o que significa que os usuários que têm uma caixa de correio em um sistema de email de terceiros receberá suas mensagens de caixa postal. Esse mecanismo não inclui o tempo de atividade de serviço garantido ou outros recursos de caixa postal, como alterar a saudação da caixa postal.

Para obter mais informações sobre a caixa postal na implementação de um sistema telefônico, consulte [Sistema telefônico com planos de chamada](calling-plan-landing-page.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se você habilitará o correio de voz de nuvem na sua implementação chamando planos.</li><li>Se usando o Exchange local e a implantação existente não atender seus requisitos para dar suporte a caixa postal de nuvem, escolha uma das opções disponíveis (atualização e o programa de instalação para suporte de caixa postal de nuvem, migrar para o Exchange Online ou aproveitar o fallback mecanismo descrito anteriormente).</li><li>Decida se vai habilitar ou desabilitar a transcrição do correio de voz e caixa postal mascaramento de obscenidades transcrição em toda a organização ou usuários específicos.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Se aplicável, documente os pontos de decisão do Exchange para oferecer suporte à caixa postal de nuvem.</li><li>Se você vai habilitar/desabilitar caixa postal, transcrições de caixa postal e caixa postal mascaramento de obscenidades transcrição somente para usuários específicos, essa lista de usuários do documento.</li></ul>|

> [!TIP]
> Detalhes de caixa postal de nuvem para o sistema telefônico com implementação chamando planos podem ser documentados como a seguir.
> 
> |Usuário |Caixa de correio do Exchange |Habilitar a caixa postal? |Transcrição do correio de voz |Mascaramento de obscenidades de transcrição de caixa postal |
> |------------------|------------------|-------------------|----------|----------|
> |Emily Braun      |Online      |Sim |Habilitado |Habilitado |
> |Lidia Holloway   |Online      |Sim |Habilitado |Desabilitado |
> |Louis Lahr       |No local |Sim |Habilitado |Habilitado |
> |Marcel Beauchamp |No local |Sim |Desabilitado |N/D |
> |Rachelle Cormier |Online      |Sim |Desabilitado |N/D |
> |Isabell Potvin   |No local |Sim |Desabilitado |N/D |

<!--ENDOFSECTION-->

## <a name="calling-identity"></a>Identidade de chamada

Por padrão, todas as chamadas de saída usam o número de telefone atribuído como identidade de chamada (ID de chamador). O destinatário da chamada pode identificar o autor da chamada rapidamente e decidir se deseja aceitar ou rejeitar a chamada. Em alguns casos, existem requisitos de negócios legítimos para mascarar a identificação do chamador para proteger a identidade de chamadores usando o número de linha principal do office — esse é normalmente um número de serviço atendido pela configuração do atendedor automático — como ID do chamador ou bloquear a ID do chamador apresentação todo.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se manipulação da ID do chamador é necessária para a implementação de planos de chamada.</li><li>Se aplicável, decidir os tipos de manipulação da ID do chamador (máscara com o número de serviço ou tornar anônimo) a serem implementadas.</li><li>Se aplicável, decida quais usuários exigem manipulação da ID do chamador e o tipo de manipulação de ID do chamador a ser atribuído a cada usuário.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Os usuários que devem ser atribuídas a manipulação da ID do chamador e o tipo de manipulação de ID do chamador para atribuir do documento.</li></ul>|

> [!TIP]
> Este é um exemplo de mascaramento de documentação de detalhes de ID do chamador.
> 
> |Usuário  |Habilitar o mascaramento de ID de chamadas de saída  |Tipo de mascaramento de ID do chamador  |Permitir substituição do usuário  | Habilitar o mascaramento de ID de chamadas de entrada  |
> |---------|---------|---------|---------|---------|
> |Emily Braun|Não|N/D|Sim|Não|
> |Lidia Holloway|Sim|Número de serviço (OrgAA + 44 20 7946 0000)|Não|Sim|
> |Louis Lahr|Não|N/D|Sim|Não|
> |Marcel Beauchamp|Sim|Número de serviço (OrgAA, TBA)|Não|Sim|
> |Rachelle Cormier|Sim|Tornar anônimo|Sim|Não|
> |Isabell Potvin|Sim|Número de serviço (OrgAA, TBA)|Não|Sim|

<!--ENDOFSECTION-->

## <a name="licensing-for-cloud-voice-capabilities"></a>Licenciamento para recursos de voz de nuvem

Conferência de áudio e sistema telefônico são recursos no Office 365. Eles podem ser licenciados separadamente como serviços de complemento para os clientes existentes que têm o Office 365 E3 ou E1 planos de assinatura; eles já estão incluídos como parte do plano de assinatura do Office 365 E5.

Planos de chamada é um complemento para o recurso de sistema telefônico no Office 365, portanto, você deve ter um sistema telefônico licenciados habilitado para usar planos de chamar.

Para oferecer suporte para conferência de áudio adicionais e planos de chamar usam casos (conferência internacional discagem externa chamar após chamar planejar alocações minutos são esgotadas e assim por diante), você pode configurar créditos de comunicações para sua organização.

## <a name="licensing-for-calling-plans"></a>Licenciamento de planos de chamada

Se sua organização pretende usar o Microsoft como provedor de serviços de telecomunicações, você precisa obter chamar planejar complementos adequados às necessidades de negócios dos usuários. Geralmente, nem todas as pessoas em uma organização precisam colocar chamadas internacionais, portanto você pode provisionar a maioria dos usuários com licenças de chamar planejar domésticas.

Existem dois tipos de licenças chamar planejar:

-   Plano de Chamadas Domésticas

-   Plano de Chamadas Internacionais e Domésticas

> [!NOTE]
> O que é considerado "nacionais" para um usuário específico é determinado pelo local de uso do Office 365 atribuído do usuário.

Cada tipo de chamada planejar fornece uma alocação da chamada de minutos que os usuários podem utilizar por mês, ou fazer chamadas nacionais ou chamadas internacionais. Os custos domésticas chamar planejar que menor comparada com o plano de chamar nacionais e internacionais.

A flexibilidade da inscrição e atribuindo o tipo de chamada planejar mais adequado para as necessidades de negócios de usuários individuais ajuda a sua organização a controlar os custos da sua implementação chamando planos.

Para cada inquilino do Office 365, combinado número de minutos de chamada é agrupado por país ou região e por tipo de chamada planejar. Quando o limite de minutos de chamada mensal para o locatário é atingido, chamar planos de serviço (exceto para chamadas de emergência) será suspenso para o restante do mês. O serviço de planos de chamar voltarão automaticamente no primeiro dia do próximo mês do calendário.

Você pode configurar créditos de comunicações para suas organizações para permitir que os usuários façam chamadas de saída após a alocação de minutos de chamada é esgotada sem precisar esperar até o próximo mês ciclo de cobrança. Além disso, Communications créditos conceder os usuários atribuídos a planejar chamar domésticas a capacidade de fazer chamadas internacionais, que são então cobradas por meio de um modelo de "pagamento por minuto".

Para saber mais sobre o sistema telefônico e chamar planos, revise os seguintes artigos:

-   [Sistema Telefônico](https://products.office.com/en-us/skype-for-business/phone-system)

-   [Planos de chamadas](https://products.office.com/en-us/skype-for-business/calling-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Se sua organização não tiver a licença de sistema telefônico necessária, decida se você vai adquirir a licença do sistema telefônico passando o backup de suas assinaturas do Office 365 existentes ou adquirindo o serviço de complemento do sistema telefônico.</li><li>Decida quais usuários exigem uma licença domésticas chamar planejar e que exigem uma licença nacionais e internacionais chamar planejar.</li><li>Decida se você precisará créditos de comunicações para sua implementação chamando planos.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente a divisão, departamento, office ou grupos de usuários que você irá atribuir uma licença de sistema telefônico com domésticas chamar planejar ou nacionais e internacionais chamar planejar.</li></ul>|

> [!TIP]
> Você pode usar o exemplo a seguir para documentar a atribuição de licença para o sistema telefônico com usuários de planos de chamada.
> 
> |Usuário |Escritório |Licença do Office 365 |Chamar o plano |
> |----|----|----|----|
> |Emily Braun |32 London Bridge Street |Office 365 E5 |Plano de Chamadas Internacionais e Domésticas |
> |Lidia Holloway |32 London Bridge Street |Office 365 E5 |Plano de Chamadas Domésticas |
> |Louis Lahr |32 London Bridge Street |Office 365 E5 |Plano de Chamadas Domésticas |
> |Marcel Beauchamp |39 quai du Président Roosevelt |Office 365 E3, complemento de sistema telefônico |Plano de Chamadas Domésticas |
> |Rachelle Cormier |39 quai du Président Roosevelt |Office 365 E5 |Plano de Chamadas Internacionais e Domésticas |
> |Isabell Potvin |39 quai du Président Roosevelt |Office 365 E3, complemento de sistema telefônico |Plano de Chamadas Domésticas |

<!--ENDOFSECTION-->

## <a name="communications-credits"></a>Créditos de Comunicação

Usando créditos de comunicações, os usuários podem discar a partir de uma reunião de conferência de áudio para adicionar outra pessoa de qualquer lugar no mundo (para o exterior originador do organizador da reunião). Você pode configurar créditos de comunicações para sua organização para permitir que os usuários façam chamadas de saída após ele ter esgotado sua alocação de chamar minutos, sem precisar esperar até o ciclo de cobrança do próximo mês. Além disso, o Communications créditos aos usuários atribuídos com o plano chamar domésticas a capacidade de fazer chamadas internacionais, que são então cobradas por meio de um modelo de "pagamento por minuto".

A primeira consideração a fazer ao implementar os Créditos de Comunicação é decidir o valor inicial de fundos a serem comprados. Se sua organização optar por usar autocarga, você vai determinar a quantidade ideal medindo o uso real. Monitorar o uso de comunicações créditos ao longo do tempo e ajuste o valor do seu recarga conforme necessário.

Para obter sua implementação chamando planos, você pode controlar o uso de créditos de comunicações em uma base por usuário, que ajuda a garantir que você tenha atribuído esses créditos no alinhamento com suas necessidades comerciais.

Para saber mais sobre créditos de comunicações, revise [Cite Communications créditos?](what-are-communications-credits.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se você precisa créditos de comunicações para a implementação da conferência de áudio ou chamar planos.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Os grupos de divisão, departamento, office ou usuário que você habilitará o créditos de comunicações do documento.</li><li>Documente o seu planejamento de comunicações créditos para a implementação da conferência de áudio ou chamar planos.</li></ul>|

> [!TIP]
> Você pode usar o exemplo a seguir para documentar a lista de atribuição de créditos de comunicações para chamar planos de usuários.
> 
> |Usuário |Escritório |Chamar o plano |Créditos de Comunicação |
> |----|----|----|----|
> |Emily Braun |32 London Bridge Street |Plano de Chamadas Internacionais e Domésticas |Habilitado |
> |Lidia Holloway |32 London Bridge Street |Plano de Chamadas Domésticas |Desabilitado |
> |Louis Lahr |32 London Bridge Street |Plano de Chamadas Domésticas |Habilitado |
> |Marcel Beauchamp |39 quai du Président Roosevelt |Plano de Chamadas Domésticas |Desabilitado |
> |Rachelle Cormier |39 quai du Président Roosevelt |Plano de Chamadas Internacionais e Domésticas |Habilitado |
> |Isabell Potvin |39 quai du Président Roosevelt |Plano de Chamadas Domésticas |Desabilitado |

<br>

> [!TIP]
> Sua créditos Communications planejamento números pode ser documentados como no exemplo a seguir.
>
> |         |         |
> |---------|---------|
> |Valor inicial|US$ 1.000|
> |Valor do gatilho|US$ 400|
> |Valor da recarga automática|TBA|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Gerenciar números de telefone de voz de nuvem

Se você implementar um sistema telefônico, trazendo seu próprio provedor de serviços de telecomunicações, gerenciamento de número de telefone permanecerá como-é.

Implementações de conferência de áudio e planos de chamada, você pode optar por adquirir novos números de telefone ou transferir números de telefone existentes (porta).

Para permitir que os usuários a maneira como eles estão acostumados os números de telefone de discagem — como omitindo os códigos de área para chamadas locais, omitindo o código de país para chamadas domésticas ou mesmo usando dígitos short discagem durante a execução de discar conferência ou chamar outros usuários na organização — Você pode configurar um plano de discagem personalizada e atribuí-lo aos usuários.

## <a name="acquire-new-telephone-numbers"></a>Adquirir novos números de telefone

Os dois tipos de números de telefone nas soluções do Microsoft cloud voz são:

-   Números de assinante (usuário), que podem ser atribuídos aos usuários em sua organização.

-   Números de serviço, disponíveis como Chamada Tarifada e números gratuitos de serviço, que têm a capacidade de chamadas simultâneas maior do que os números de telefone do assinante e podem ser atribuídos aos serviços, como a conferência de áudio, atendedores automáticos ou chamada filas.

Para obter mais informações sobre os tipos de números de telefone, consulte [tipos diferentes de números de telefone usados para chamar planos](different-kinds-of-phone-numbers-used-for-calling-plans.md).

A contagem total dos números de telefone que você pode obter dependem do tipo de número de telefone e o número de licenças que você comprou e atribuído aos seus usuários.

Para obter mais informações sobre a contagem total dos números de telefone que você pode obter, consulte [números de telefone de quantos você consegue?](how-many-phone-numbers-can-you-get.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida os locais do usuário ou escritórios onde os novos números de telefone serão adquiridos da Microsoft.</li><li>Escolher o tipo de números de telefone a ser adquirida da Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente os locais do usuário ou escritórios onde os novos números de telefone serão adquiridos da Microsoft.</li><li>O tipo de números de telefone a ser adquirida da Microsoft do documento.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Transferir os números de telefone existente

Se sua organização deseja transferir (ou porta) existente de números de telefone à Microsoft, você poderá fazer isso enviando uma solicitação de pedido de porta para a Microsoft.

Você pode transferir todos os seus existente números de telefone ao mesmo tempo (porta completo), e — em alguns mercados — você pode transferir um subconjunto dos seus números de telefone existente (porta parcial). Uma porta parcial pode ser útil em casos em que você deseja apenas gradualmente mover os usuários para o sistema telefônico com planos de chamada.

Ordem de uma única porta pode transferir apenas os números de telefone para um tipo de número de telefone único. Se você precisar transferir alguns dos seus números de telefone como números de telefone do assinante e algumas, como números de serviço, recomendamos que você primeiro concluir a transferência para a Microsoft e, em seguida, executar a conversão assim que os números são no controle da Microsoft.

Como alternativa (se há suporte para a porta parcial), você pode enviar várias solicitações de porta, a solicitação de uma porta ao mesmo tempo. No entanto, essa abordagem alternativa será prolongar seu contrato com seu provedor de serviços de telecomunicações existente.

Portabilidade de número de telefone é um tópico complexo e requer planejamento completo, coordenação e gerenciando adequadamente expectativas os públicos envolvidos. Para saber mais, consulte os seguintes artigos:

-   [Transferindo números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md)

-   [Perguntas comuns sobre transferência de números de telefone](transferring-phone-numbers-common-questions.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida os locais do usuário ou escritórios onde os números de telefone existente serão transferidos para a Microsoft.</li><li>Escolher o tipo de números de telefone a ser transferido para a Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente os locais do usuário ou escritórios onde os números de telefone existente serão transferidos para a Microsoft.</li><li>O tipo de números de telefone a ser transferido para a Microsoft de documento.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Planos de discagem

Um plano de discagem no recurso de sistema telefônico do Office 365 é um conjunto de regras de normalização convertem discado números de telefone em um formato alternativo (normalmente o formato e. 164) para autorização de chamada e roteamento de chamada. O serviço de conferência de áudio aproveita os mesmos recursos usados pelo sistema telefônico para converter números de telefone discado em cenários de discagem de conferência (por exemplo, convidar participantes via PSTN e discagem novamente, o recurso "ligar para mim").

No recurso de sistema telefônico do Office 365, existem dois tipos de planos de discagem:

-   **Plano de discagem de serviço:** Este é o padrão plano de discagem que se aplica a usuários com base em seu local de uso do Office 365, e não pode ser modificado.

-   **Plano de discagem de locatário:** Este é um plano de discagem personalizáveis em um locatário, que é dividido em dois tipos:

    -   **Plano de discagem global de locatário:** O plano de discagem que se aplica a todos os usuários no inquilino.

    -   **Plano de discagem do usuário de Inquilino:** O plano de discagem que se aplica apenas para usuários específicos.

O plano de discagem efetivas atribuído aos usuários é a combinação do plano de discagem de serviço (com base no local de uso do Office 365 do usuário) e plano (que pode ser um plano de discagem global de locatário ou o plano de discagem do usuário de Inquilino) de discagem de locatário.

![Tabela mostra três combinações de serviço e locatário planos de discagem.] (media/audio_conferencing_image8.png "Tabela mostra três combinações de serviço e locatário planos de discagem.")

> [!IMPORTANT]
> Pode haver um máximo de 25 regras de normalização em cada plano de discagem de locatário; Portanto, é importante evitar a duplicação de regras de normalização que já estão disponíveis como parte do serviço de plano de discagem.

Para obter mais informações sobre os planos de discagem, confira [O que são os planos de discagem?](what-are-dial-plans.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se sua organização requer planos de discagem personalizada (requisitos de negócios, requisitos de adoção e assim por diante).</li><li>Se aplicável, decida o plano de discagem de locatário do escopo (global de locatário ou Locatário do usuário) para dar suporte a seus requisitos para planos de discagem personalizada.</li><li>Se aplicável, decida os planos de discagem de locatário que você vai criar para suportar os locais do usuário ou escritórios no escopo para a implementação de voz de nuvem.</li><li>Se aplicável, decida quais usuários exigem um plano de discagem personalizada e o plano de discagem de locatário a ser atribuído para cada usuário.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente os planos de discagem personalizada e as regras de normalização associadas a ser configurado como parte da implementação de voz de nuvem.</li><li>Os usuários que devem ser atribuídos a um plano de discagem personalizada e o plano de discagem de locatário a ser atribuído para cada usuário do documento.</li></ul>|

> [!TIP]
> Se ele for aplicável ao seu projeto, você pode usar o modelo a seguir para documentar as configurações de plano de discagem de locatário.
> 
> |Nome do plano de discagem de locatário<br>_Descrição_  |Nome das regras de normalização<br>_Descrição_  |Padrão<br>Conversão<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_One Epping Road North Ryde, NSW, AU Dial Plan_|**AU-NSW-NorthRyde-OER-Internal**<br>_Número interno (x7000 - x7999) para o escritório de One Epping Road, North Ryde, NSW, Austrália_|^(7\d{3})$<br>+6125550$1<br>True|
> ||**AU-NSW-Local**<br>_Normalização do número local para NSW, Austrália_|^ ([2-9] \d{7}) $<br>+612$1<br>False|
> ||**AU-TollFree**<br>_Normalização de número gratuito na Austrália_|^ (1 [38] \d{4,8}) \d*$<br>+61$1<br>False|
> ||**AU-Service**<br>_Normalização de número de serviço na Austrália_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>False|
> |**SG-Singapore-OMB**<br>_OMB Singapore, SG Dial Plan_|**SG-OMB-Internal**<br>_Número interno (x8000 â €"x 8999) do office orientações, Cingapura_|^(8\d{3})$<br>+656888$1<br>True|
> ||**SG-TollFree**<br>_Normalização de número gratuito em Cingapura_|^(1?800\d{7}) \d*$<br>+65$1<br>False|
> ||**SG-Service**<br>_Normalização de número de serviço em Cingapura_|^ (1\d{3,4}\|9\d{2}) $<br>$1<br>False|
> |**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux, France Dial Plan_|**FR-39qdPR-Internal**<br>_Número interno (x7000 â €"x 7999) para 39 quai du Président Roosevelt do escritório, Issy-les-Moulineaux, França_|^(7\d{3})$<br>+3319999$1<br>True|
> ||**FR-TollFree**<br>_Normalização de número gratuito na França_|^ 0?(80\d{7}) \d*$<br>+33$1<br>False|
> ||**FR-Service**<br>_Normalização de número de serviço na França_|^ (1\d{1,2}\|11 [68] \d{3}\|10\d{2}\|3\d{3}) $<br>$1<br>False|

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
> |Louis Lahr|32 London Bridge Street|Plano de discagem para serviço|N/A|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Plano de discagem para locatários|FR-Paris-Issy-30qdPR|
> |Rachelle Cormier|39 quai du Président Roosevelt|Plano de discagem para locatários|FR-Paris-Issy-30qdPR|
> |Isabell Potvin|39 quai du Président Roosevelt|Plano de discagem para locatários|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Decisões de serviço de documento 

Use as informações das seções anteriores deste artigo para documentar suas decisões de serviço. Em geral, esta documentação irá conter as seguintes seções principais:

-   Sistema telefônico com lista planos de chamada de habilitação de site

-   Atribuição de licença para o sistema telefônico com usuários de planos de chamada

-   Número de planejamento de Créditos de Comunicação

-   Aquisição de número de telefone, números de telefone e detalhes do local de emergência

-   Detalhes de configuração de caixa postal

-   ID do chamador mascaramento de detalhes de configuração

-   Planos de discagem para locatários

-   Atribuições de planos de discagem

<!--ENDOFSECTION-->