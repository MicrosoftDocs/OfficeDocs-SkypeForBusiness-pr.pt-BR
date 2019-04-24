---
title: Tomar decisões sobre o serviço de Audioconferência - Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 12/28/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Saiba mais sobre reuniões, licenciamento e planos de discagem de disponibilidade, definindo as configurações de ponte de conferência, aquisição ou transferindo números de telefone e escolher inquilino.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b6bd854de7af09ebea6b66a6393beb751f11770
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32241536"
---
# <a name="make-my-service-decisions"></a>Tomar decisões meu serviço

Para planejar a implementação técnica de conferência de áudio, você deve fazer uma série de decisões de serviço antes do tempo para melhor preparar sua organização para implementar uma solução que atende aos seus requisitos de negócios definidas.

## <a name="audio-conferencing-in-teams"></a>Serviços de audioconferência em equipes

Como parte da definição de recursos de conferência de áudio necessários em Teams da Microsoft, uma das primeiras etapas é avaliar o mapa público mais recente para determinar:

-   Quais recursos de conferência de áudio em equipes que serão implantados para os usuários no escopo.

-   Espera-se os requisitos de funcionalidade do usuário para conferência de áudio em equipes.

-   Confirmação de que os recursos de conferência de áudio em equipes descritos no mapa público mais recente atendam seu usuário, a funcionalidade e os requisitos de escopo, na linha do tempo da sua implantação.

> [!NOTE]
> O mapa de equipes mais recente para identificar os recursos de conferência de áudio de equipes do escopo para sua implantação pode ser encontrada em <https://aka.ms/O365Roadmap>.

## <a name="meetings-in-teams"></a>Reuniões no Teams

Equipes proporciona aos seus usuários a capacidade de agendar e ingressar em reuniões online com o uso de vídeo HD, opções de conferência discada de voz sobre IP (VoIP) e PSTN.

Reuniões possam ser programadas como as reuniões privadas (somente os participantes convidados podem ingressar) ou reuniões de canal (aberta para todos os usuários tenham acesso ao canal) e os usuários também podem iniciar reuniões improvisadas dentro dos canais.

> [!NOTE]
> Para saber mais sobre os recursos de reuniões em equipes, consulte o [Microsoft 365 Roadmap](https://aka.ms/O365Roadmap).

Os participantes da reunião podem ingressar em reuniões suas equipes por discar para a chamada Tarifada ou uma ponte de conferência discada gratuitos números de telefone via landlines ou telefones celulares. Além disso, os usuários podem permitir que o serviço de conferência de áudio iniciar o recurso "ligar para mim" para que eles podem participar de uma reunião por ter a ponte de conferência chame seus telefones (útil quando a conexão de dados não é confiável) ou reunião permitem que os organizadores convidem reunião participantes discando a eles para seus telefones.

> [!IMPORTANT]
> Serviços de audioconferência em equipes não oferece suporte a provedores de serviços de audioconferência de terceiros (ACPs).

<!--ENDOFSECTION-->

## <a name="availability-of-audio-conferencing"></a>Disponibilidade da Audioconferência

Antes de planejar a implementação da conferência de áudio em equipes, você precisará revisar a disponibilidade do serviço de conferência de áudio, conforme detalhado no [país e região disponibilidade para conferência de áudio e planos de chamada](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

> [!IMPORTANT]
> Devido a restrições legais, para conferência de áudio esteja disponível para organizações multinacionais, o contrato para assinaturas do Office 365 deve ser originado países e regiões onde o serviço de conferência de áudio está disponível comercialmente.

Depois de confirmar que sua organização está qualificada obter o serviço de conferência de áudio, compilar a lista de locais do usuário ou de escritórios onde você implementará o serviço de conferência de áudio, com base na lista de regiões e países disponíveis.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida qual usuário locais ou escritórios implementará o serviço de conferência de áudio.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente os locais do usuário ou escritórios estar habilitado para o serviço de conferência de áudio.</li></ul>|

> [!TIP]
> Abaixo é um exemplo de um modelo de lista de habilitação de site de conferência de áudio:
> 
> |Office   |Localização |Serviço de Conferência PSTN  |
> |---------|---------|---------|
> |One Epping Road|Austrália|Audioconferência|
> |100 Alma Road|Hong Kong SAR|Conferência PSTN herdada|
> |One Marina Boulevard|Cingapura|Audioconferência|
> |32 London Bridge Street|Reino Unido|Audioconferência|
> |39 quai du Président Roosevelt|França|Audioconferência|

<!--ENDOFSECTION-->

## <a name="licensing-for-audio-conferencing"></a>Licença para a Audioconferência

Uma [licença de conferência de áudio](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) está disponível como parte dos planos de assinatura do Office 365 E5 ou como um serviço complementar para planos de assinatura do Office 365 E1 ou Office 365 E3.

> [!NOTE]
> Conferência PSTN ou discada em equipes não oferece suporte a provedores de serviços de audioconferência de terceiros (ACPs).
> <br>Se você já usa a Conferência PSTN do Skype for Business hoje, você pode aproveitar a Audioconferência no Teams imediatamente.

Para fornecer números de telefone de ponte de conferência de discagem gratuita e para oferecer suporte a discagem de conferência aos números de telefone internacional, você deve configurar [Créditos de comunicações](what-are-communications-credits.md) para sua organização.

> [!IMPORTANT]
> Alguns países forem atendidos pelo números de telefone de ponte de conferência de discagem gratuita apenas. Para oferecer suporte à discagem nesses países, você deve usar créditos de comunicações.

A primeira consideração ao implementar créditos de comunicações é decidir a quantidade inicial de fundos que você deseja comprar. Se sua organização optar por usar autocarga, você precisará decidir o valor de gatilho (valor mais baixo de fundos) e a quantidade de autocarga. Seu uso real determinará a quantidade de autocarga. Monitore o uso de comunicações créditos ao longo do tempo e ajustar a quantidade de carga, conforme necessário.

Você pode aprender mais sobre Communications créditos [aqui](what-are-communications-credits.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Se sua organização não tiver já adquiriu a conferência de áudio necessários licenciamento, decida se você vai adquirir licenças de conferência de áudio por assinaturas do Office 365 existentes de revisão ou por adquirir licenças de complemento de conferência de áudio.</li><li>Decida se Communications créditos são necessários para a implementação da conferência de áudio. Em caso positivo, decida o valor inicial de fundos a serem comprados. Onde aplicável, decida o valor do gatilho e o valor da recarga automática.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Os usuários que serão atribuídos licenças de conferência de áudio do documento.</li><li>Documentar o plano de comunicação créditos (quantidade inicial, quantidade de gatilho, quantidade de autocarga)</li></ul>|

> [!TIP]
> Você pode documentar a lista de atribuição de licença para usuários de conferência de áudio usando o exemplo a seguir.
> 
> |Usuário  |Escritório  |Licença do Office 365  |
> |---------|---------|---------|
> |Adele Vance|One Epping Road|Office 365 E5|
> |Alex Wilber|One Epping Road|Office 365 E3, complemento de Audioconferência|
> |Ben Walters|One Epping Road|Office 365 E3, complemento de Audioconferência|
> |Christie Cline|One Marina Boulevard|Office 365 E3, complemento de Audioconferência|
> |Debra Berger|One Marina Boulevard|Office 365 E5|
> |Lee Gu|One Marina Boulevard|Office 365 E5|
> |Emily Braun|32 London Bridge Street|Office 365 E5|
> |Lidia Holloway|32 London Bridge Street|Office 365 E5|
> |Louis Lahr|32 London Bridge Street|Office 365 E5|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3, complemento de Audioconferência|
> |Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5|
> |Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3, complemento de Audioconferência|

<br>

> [!TIP]
> Os números do planejamento de seus Créditos de Comunicação podem ser documentados da seguinte maneira:
>
> |         |         |
> |---------|---------|
> |Valor inicial|US$ 1.000|
> |Valor do gatilho|US$ 400|
> |Valor da recarga automática|TBA|
> 
<!--ENDOFSECTION-->

## <a name="conference-bridge-phone-numbers"></a>Números de telefone de ponte de conferência

O serviço de Audioconferência do Office 365 inclui:

-   Números de telefone de ponte de vários tipos de conferência (tarifas e gratuitos)

-   (Dedicados e compartilhados) de números de telefone de várias categorias de ponte de conferência

-   Suporte de vários idiomas para a ponte de conferência (primária e secundária)

-   Um número de telefone padrão para o locatário

> [!NOTE]
> Contagem de números conferência dedicado ponte telefone em relação ao limite dos números de telefone que podem ser adquiridos por locatário, com base no número de licenças aplicáveis. Os números de telefone gratuitos da ponte de conferência não precisam de Créditos de Comunicação.

Se você deve transferir números de telefone de ponte de conferência existente para o serviço de conferência de áudio — supondo que eles atendam aos requisitos específicos do país — você pode transferir esses números de telefone de ponte de conferência existente à Microsoft.

> [!NOTE]
> A complexidade de transferência de números de telefone para o Microsoft significativamente varia dependendo do país ou região, operadora, número de circuitos envolvidos e muitos outros fatores que contribuem. Trabalhar com o provedor atual para investigar quanto tempo isso é provavelmente precisará executar para ajudar a garantir que você iniciar o processo de antecedência suficiente para atender às suas linhas de tempo.

Para saber mais sobre os números de telefone de ponte de conferência, revise os seguintes artigos:

-   [Configurar Audioconferência no Microsoft Teams](set-up-audio-conferencing-in-teams.md)

-   [Números de telefone para audioconferência](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)

-   [Obter números de telefone de serviço](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

-   [Transferir números de telefone para o Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se sua organização precisa números de telefone de ponte de conferência dedicado.</li><li>Decidir como os números de telefone de ponte de conferência dedicado serão obtidos para os locais do usuário ou de escritórios em escopo para a implementação da conferência de áudio (isto é, obtém de números de telefone existentes da Microsoft ou transferência).</li><li>Se você escolher obtê-las da Microsoft, decidir o método a ser usado (envio do formulário ou automatizada) para os locais do usuário ou de escritórios em escopo para a implementação da conferência de áudio.</li><li>Decida as preferências de idioma para configurar o para cada número de telefone de ponte de conferência dedicado.</li><li>Decida o número de telefone de ponte de conferência do locatário padrão.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente o planejamento de mestre de aquisição de número de telefone, detalhando como números de telefone serão obtidos para cada local do usuário ou do office no escopo para a implementação da conferência de áudio.</li><li>Se aplicável, conclua o formulário de nova solicitação de número de telefone — um formulário para cada local ou do office.</li><li>Documento números configurações (shared e dedicada números de telefone de ponte de conferência, as preferências de idioma para cada número de telefone de ponte de conferência dedicado, número de telefone de ponte de conferência do locatário padrão) de telefone de ponte de conferência detalhadas.</li></ul>|

Abaixo é um exemplo de um modelo que você pode usar para capturar detalhes de ponte de conferência.

> [!TIP]
> Veja a seguir o exemplo de um modelo para capturar detalhes da ponte de conferência:
> 
> |Escritório   |Aquisição do número da ponte e Tipo da ponte |Número da ponte  |Idioma da ponte|
> |---------|---------|---------|---------|
> |One Epping Road|Adquirir novo, exclusivo|TBA|Inglês (Austrália)|
> |One Marina Boulevard|Adquirir novo, compartilhado|TBA|Inglês (Estados Unidos); Chinês (Simplificado, PRC)|
> |32 London Bridge Street|Porta existente, exclusiva|+44 20 7946 0001|Inglês (Reino Unido)|
> |39 quai du Président Roosevelt|Adquirir novo, exclusivo|TBA|Francês (França), Inglês (Reino Unido)|

<!--ENDOFSECTION-->

## <a name="conference-bridge-settings"></a>Configurações de ponte de conferência

Para ajustar ainda mais a experiência do usuário, você pode configurar opções de toda a organização para ingressar em reuniões de conferência de áudio (entrada e saída registro de nomes de notificação e o chamador da reunião), tamanho do PIN do organizador da reunião e notificação por e-mail:

-   As notificações de entrada e saída de reuniões estão disponíveis na forma de nome, número de telefone e tons registrados.

-   O comprimento do PIN pode ter de 4 a 12 dígitos, com um PIN de 5 dígitos como padrão.

-   Notificação de emails enviados sobre a habilitação da licença de audioconferências ou qualquer outra alteração de conduzido pelo administrador estão habilitados por padrão. Você pode desabilitá-lo e assumir o controle das comunicações do usuário da sua organização.

Para usuários que receberem uma licença de conferência de áudio, os Chamada Tarifada/toll-livre números padrão, mostrados nas coordenadas de conferência de áudio, podem ser configurados para usar:

-   O padrão de nível de locatário.

-   Os números de telefone de ponte de conferência atribuída automaticamente.

-   Um números de telefone de ponte conferência configurado manualmente para cada usuário.

Conferência específica do usuário ponte telefone números são normalmente é útil em organizações globais ou em todo o país onde os usuários são distribuídos e devem fornecer números locais como os números de telefone de ponte de conferência padrão em seus convites para reunião.

Os participantes ingressando a partir de diferentes cidades ou no exterior podem procurar números adicionais configurados no nível de locatário, mas esses números não apareçam diretamente os convites de reunião. Os convites de reunião fornecem um link que leva participantes para a página de **números de discagem da conferência de equipes** para que eles possam procurar o número de telefone de ponte de conferência mais próximo ao seu local.

Você também pode configurar os chamadores como não-autenticados são manipuladas por cada organizador da reunião individuais — se será exigido para iniciar a reunião antes que os chamadores não autenticados podem ser admitidos ou permitir que o organizador da reunião não autenticado chamadores para iniciar uma reunião .

Você também pode aplicar configurações adicionais para cada usuário controlar o uso de números de telefone de ponte de conferência de discagem gratuita e discagem externa de uma conferência.

> [!NOTE]
> Esses controles relacionados a custo estão atualmente disponíveis somente para clientes da prévia. Você pode registrar sua organização no programa de visualização de https://www.skypepreview.com.

Com esses controles, você poderá decidir se os organizadores de reunião podem fornecer números de telefone de ponte de conferência de discagem gratuita para reuniões organizadas por eles e os participantes podem discar as reuniões organizados por eles. O nível de controle de discagem engloba desde completamente impedindo a discagem externa, para permitir apenas a discagem externa para números de domésticas, permitindo a discagem externa aos números nacionais e internacionais.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decidir se sua organização requer notificações de entrada e saída, e — se contiver — o tipo de notificação a serem implementados (tons, número de telefone ou nome registrado).</li><li>Decida o comprimento de PIN de conferência de áudio que atende aos seus requisitos de segurança da organização.</li><li>Decida se sua organização deseja assumir o controle das comunicações do usuário relacionadas ao serviço de conferência de áudio.</li><li>Decida os números de telefone de ponte de conferência a ser atribuído a cada organizador da reunião.</li><li>Decida se alguns organizadores de reunião precisam usar números de telefone de ponte de conferência de discagem gratuita para suas reuniões.</li><li>Decida se precisam de alguns organizadores de reunião permitir que os chamadores não autenticados iniciar uma reunião.</li><li>Decida se alguns organizadores de reunião precisam discar conferência seja controlado.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documentar detalhadamente as configurações de ponte de conferência (notificações de entrada e saída, tamanho do PIN, notificação por email de alteração do configurações)</li><li>Documente os números de telefone de ponte de conferência a ser atribuído a cada organizador da reunião e a configuração correspondente para controlar a diretiva para os chamadores não-autenticados e gratuitos e discar controles.</li></ul>|

> [!TIP]
> As configurações de ponte de conferência podem ser documentadas como no exemplo a seguir.
> 
> |         |         |
> |---------|---------|
> |Permitir notificações de entrada e saída de reuniões|Habilitado|
> |Tipo de anúncio de entrada/saída|Tons|
> |Solicitar que os autores de chamadas registrem seus nomes antes de ingressar na reunião|Desabilitado|
> |Tamanho do PIN|5|
> |Enviar emails automaticamente para os usuários quando suas configurações de discagem forem alteradas|Desabilitado|

<br>

> [!TIP]
> Você pode documentar a lista de atribuição de configurações de ponte conferência para usuários de conferência de áudio usando o exemplo a seguir.
>
> |Usuário  |Escritório  |Número de chamada padrão  |Número de chamada gratuita padrão  |Permitir chamada gratuita  |Autores de chamada não autenticados ignoram o lobby  |Discagem de saída de conferência  |
> |---------|---------|---------|---------|---------|---------|---------|
> |Adele Vance|One Epping Road|TBA|TBA|Sim|Habilitado|Doméstico e internacional|
> |Alex Wilber|One Epping Road|TBA|TBA|Não|Desabilitado|Não permitido|
> |Ben Walters|One Epping Road|TBA|TBA|Não|Desabilitado|Não permitido|
> |Christie Cline|One Marina Boulevard|TBA|TBA|Sim|Desabilitado|Doméstico|
> |Debra Berger|One Marina Boulevard|TBA|TBA|Sim|Habilitado|Doméstico|
> |Lee Gu|One Marina Boulevard|TBA|TBA|Sim|Habilitado|Doméstico|
> |Emily Braun|32 London Bridge Street|+44 20 7946 0001|TBA|Sim|Habilitado|Não permitido|
> |Lidia Holloway|32 London Bridge Street|+44 20 7946 0001|TBA|Sim|Desabilitado|Não permitido|
> |Louis Lahr|32 London Bridge Street|+44 20 7946 0001|TBA|Sim|Desabilitado|Não permitido|
> |Marcel Beauchamp|39 quai du Président Roosevelt|TBA|TBA|Não|Desabilitado|Doméstico|
> |Rachelle Cormier|39 quai du Président Roosevelt|TBA|TBA|Sim|Habilitado|Doméstico e internacional|
> |Isabell Potvin|39 quai du Président Roosevelt|TBA|TBA|Não|Desabilitado|Doméstico|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Gerenciar números de telefone de voz de nuvem

Para a implementação da conferência de áudio, você pode optar por adquirir novos números de telefone ou transferência/porta números de telefone existente.

Para permitir que os usuários disquem números de telefone a maneira como eles estão acostumados — como omitindo os códigos de área para chamadas locais, omitindo o código de país para chamadas domésticas ou mesmo usando curto dígito discando durante a execução de conferência discar — você pode configurar um plano de discagem personalizada e atribuí-lo aos usuários.

## <a name="acquire-new-telephone-numbers"></a>Adquirir novos números de telefone

Os dois tipos de números de telefone em soluções do Microsoft cloud voice são:

-   Números de assinante (usuário), que podem ser atribuídos aos usuários em sua organização.

-   Números de serviço, disponíveis como Chamada Tarifada e números gratuitos de serviço, que têm a capacidade de chamadas simultâneas maior do que os números de telefone do assinante e podem ser atribuídos aos serviços, como a conferência de áudio, atendedores automáticos ou chamada filas.

Para obter mais informações sobre esses tipos de números de telefone, consulte [tipos diferentes de números de telefone usados para chamar planos](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans).

A contagem total de telefone números que você pode obter dependem os tipos de número de telefone e o número de licenças você comprei e atribuído aos seus usuários.

Quando se trata de números de serviço, você precisará planejar cuidadosamente a implementação de conferência de áudio. Avalie se sua empresa requer números de telefone de ponte de conferência dedicado; Caso contrário, sua organização pode optar por usar números de telefone de ponte de conferência compartilhado.

Para obter mais informações sobre a contagem total dos números de telefone que você pode obter, consulte [números de telefone de quantos você consegue?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida os locais do usuário ou escritórios onde os novos números de telefone serão adquiridos da Microsoft.</li><li>Escolher o tipo de números de telefone a ser adquirida da Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente os locais do usuário ou escritórios onde os novos números de telefone serão adquiridos da Microsoft.</li><li>O tipo de números de telefone a ser adquirida da Microsoft do documento.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Transferir os números de telefone existente

Se sua organização deseja transferir (ou porta) existente de números de telefone à Microsoft, você poderá fazer isso enviando uma solicitação de pedido de porta para a Microsoft.

Você pode transferir todos os seus existente números de telefone ao mesmo tempo (porta completo), e — em alguns mercados — você pode transferir um subconjunto dos seus números de telefone existente (porta parcial). Uma porta parcial pode ser útil em casos onde você deseja apenas mover sua ponte de conferência discada a serviço de conferência de áudio.

Ordem de uma única porta pode transferir apenas os números de telefone para um tipo de número de telefone único. Se você precisar transferir alguns dos seus números de telefone como números de telefone do assinante e algumas, como números de serviço, recomendamos que você primeiro concluir a transferência para a Microsoft e, em seguida, executar a conversão assim que os números são dentro do controle da Microsoft.

Como alternativa, se houver suporte parcial porta, você pode enviar várias solicitações de porta, a solicitação de uma porta ao mesmo tempo. No entanto, essa abordagem alternativa será prolongar seu contrato com seu provedor de serviços de telecomunicações existente.

Portabilidade de número de telefone é um tópico complexo e requer planejamento completo, coordenação e gerenciando adequadamente expectativas os públicos envolvidos. Para saber mais, consulte os seguintes artigos:

-   [Transferindo números de telefone para o Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [Perguntas comuns sobre transferência de números de telefone](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida os locais do usuário ou escritórios onde os números de telefone existente serão transferidos para a Microsoft.</li><li>Escolher o tipo de números de telefone a ser transferido para a Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente os locais do usuário ou escritórios onde os números de telefone existente serão transferidos para a Microsoft.</li><li>O tipo de números de telefone a ser transferido para a Microsoft de documento.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Planos de discagem

Um plano de discagem no recurso de sistema telefônico do Office 365 é um conjunto de regras de normalização que converte discado números de telefone em um formato alternativo (normalmente o formato e. 164) para autorização de chamada e roteamento de chamada. O serviço de conferência de áudio aproveita os mesmos recursos usados pelo sistema telefônico para converter números de telefone discado em cenários de discagem de conferência (por exemplo, convidar participantes via PSTN e discagem novamente, o recurso "ligar para mim").

No recurso de sistema telefônico do Office 365, existem dois tipos de planos de discagem:

-   **Plano de discagem de serviço:** Este é o padrão plano de discagem que se aplica a usuários com base em seu local de uso do Office 365, e não pode ser modificado.

-   **Plano de discagem de locatário:** Este é um plano de discagem personalizáveis em um locatário, que é dividido em dois tipos:

    -   **Plano de discagem global de locatário:** O plano de discagem que se aplica a todos os usuários no inquilino.

    -   **Plano de discagem do usuário de Inquilino:** O plano de discagem que se aplica apenas para usuários específicos.

O plano de discagem efetivas atribuído aos usuários é a combinação do plano de discagem de serviço (com base no local de uso do Office 365 do usuário) e o plano de discagem de locatário (pode ser o plano de discagem global de locatário ou plano de discagem do usuário de Inquilino).

![Tabela mostra três combinações de serviço e locatário planos de discagem.] (media/audio_conferencing_image8.png "Tabela mostra três combinações de serviço e locatário planos de discagem.")

> [!Important]
> Pode haver um máximo de 25 regras de normalização em cada plano de discagem de locatário; Portanto, é importante evitar a duplicação de regras de normalização que já estão disponíveis como parte do serviço de plano de discagem.

Para saber mais sobre os planos de discagem, consulte [quais são os planos de discagem?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se sua organização requer planos de discagem personalizada (requisitos de negócios, requisitos de adoção e assim por diante).</li><li>Se aplicável, decida o escopo do plano de discagem de locatário (inquilino global ou Locatário do usuário) para suportar os requisitos para planos de discagem personalizada.</li><li>Se aplicável, decidir os planos de discagem de locatário que você vai criar para suportar os locais do usuário ou escritórios em escopo para a implementação de voz de nuvem.</li><li>Se aplicável, decida quais usuários exigem um plano de discagem personalizada e o plano de discagem de locatário a ser atribuído para cada usuário.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente os planos de discagem personalizada e as regras de normalização associadas a ser configurado como parte da sua implementação de voz de nuvem.</li><li>Os usuários que devem ser atribuídos a um plano de discagem personalizada e o plano de discagem de locatário a ser atribuído para cada usuário do documento.</li></ul>|

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

-   Lista de habilitação do site do serviço de Audioconferência

-   Lista de atribuição de licenças para organizadores de reunião de Audioconferência

-   Número de planejamento de Créditos de Comunicação

-   Detalhes de ponte de conferência

-   Configurações de ponte de conferência

-   Atribuições das configurações de ponte de conferência

-   Planos de aquisição de números de telefone

-   Planos de discagem para locatários

-   Atribuições de planos de discagem

<!--ENDOFSECTION-->