---
title: Tomar decisões sobre o serviço de Audioconferência - Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 12/28/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Saiba mais sobre reuniões, licenciamento e disponibilidade, configurando as configurações da ponte de conferência, obtendo ou transferindo números de telefone e escolhendo planos de discagem de locatários.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d0155788ef4ba99a350be0043847edd5e705b75b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240571"
---
# <a name="make-my-service-decisions"></a>Fazer minhas decisões de serviço

Para planejar a implementação técnica da videoconferência, você deve fazer uma série de decisões de serviço com antecedência para melhor preparar a sua organização para implementar uma solução que atenda às suas necessidades comerciais definidas.

## <a name="audio-conferencing-in-teams"></a>Conferências de áudio no Microsoft Teams

Como parte da definição de recursos de audioconferência necessários no Microsoft Teams, uma das primeiras etapas é avaliar o mapa público mais recente para determinar:

-   Quais recursos de audioconferência em equipes serão implantados para usuários no escopo.

-   Requisitos de funcionalidade de usuário esperados para videoconferências no Microsoft Teams.

-   Confirme se os recursos de audioconferência em equipes descritos no mapa público mais recente atendem aos requisitos de usuário, funcionalidade e escopo na linha do tempo da sua implantação.

> [!NOTE]
> O mapa mais recente das equipes para identificar os recursos de conferência de áudio do Microsoft Teams no <https://aka.ms/O365Roadmap>escopo da sua implantação pode ser encontrado em.

## <a name="meetings-in-teams"></a>Reuniões no Teams

O Microsoft Teams dá aos usuários a funcionalidade de agendar e ingressar em reuniões online usando as opções vídeo HD, voz sobre IP (VoIP) e conferência discada PSTN.

As reuniões podem ser agendadas como reuniões particulares (somente pessoas convidadas podem ingressar) ou reuniões de canal (abertas para todos os usuários que têm acesso ao canal) e os usuários também podem iniciar reuniões improvisadas em canais.

> [!NOTE]
> Para saber mais sobre os recursos de reuniões no Microsoft Teams, consulte o [mapa do Microsoft 365](https://aka.ms/O365Roadmap).

Os participantes da reunião podem ingressar em reuniões de equipes ao discar para os números de telefone da ponte de conferência discada chamada tarifada ou chamada tarifada por telefones fixos ou celulares. Além disso, os usuários podem permitir que o serviço de audioconferência inicie o recurso "ligar para mim" para que ele possa participar de uma reunião fazendo com que a ponte de conferência chame seus telefones (útil quando a conexão de dados não é confiável) ou permitir que os organizadores da reunião convidem a reunião participantes discando para seus telefones.

> [!IMPORTANT]
> A videoconferência no Microsoft Teams não oferece suporte a provedores de audioconferência (ACPs) de terceiros.

<!--ENDOFSECTION-->

## <a name="availability-of-audio-conferencing"></a>Disponibilidade da Audioconferência

Antes de planejar a implementação da conferência de áudio no Microsoft Teams, você precisa rever a disponibilidade do serviço de audioconferência, conforme detalhado na [disponibilidade de país e região para videoconferências e planos de chamada](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

> [!IMPORTANT]
> Devido a restrições legais para a conferência de áudio estar disponível para organizações multinacionais, o contrato para assinaturas do Office 365 deve ser originado a partir de países e regiões onde o serviço de audioconferência está disponível comercialmente.

Depois de confirmar que sua organização está qualificada a obter o serviço de audioconferência, Compile a lista de locais do usuário ou dos escritórios nos quais você implementará o serviço de audioconferência, com base na lista de países e regiões disponíveis.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decidir quais locais de usuário ou escritórios implementarão o serviço de audioconferência.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documentar os locais do usuário ou os escritórios a serem habilitados para o serviço de audioconferência.</li></ul>|

> [!TIP]
> Veja a seguir um exemplo de um modelo de lista de habilitação de sites do referencing de áudio:
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

Uma [licença de audioconferência](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) está disponível como parte dos planos de assinatura do Office 365 E5 ou como um serviço complementar para o Office 365 E1 ou planos de assinatura do Office 365 E3.

> [!NOTE]
> A conferência discada ou PSTN no Microsoft Teams não oferece suporte a provedores de audioconferência (ACPs) de terceiros.
> <br>Se você já usa a Conferência PSTN do Skype for Business hoje, você pode aproveitar a Audioconferência no Teams imediatamente.

Para fornecer números de telefone de chamada de conferência gratuita e para dar suporte à discagem de conferência discada para números de telefone internacionais, você deve configurar [créditos de comunicações](what-are-communications-credits.md) para a sua organização.

> [!IMPORTANT]
> Alguns países são atendidos somente por números de telefone de ponte de conferência de chamadas gratuitas. Para dar suporte à discagem nestes países, você deve usar créditos de comunicações.

A primeira consideração ao implementar créditos de comunicações é decidir a quantidade inicial de fundos que você deseja comprar. Se a sua organização optar por usar o recurso de recarga automática, você precisará decidir o valor do gatilho (menor valor dos fundos) e o valor da recarga automática. Seu uso real determinará o valor da recarga automática. Você deve monitorar o uso dos seus créditos de comunicações ao longo do tempo e ajustar o valor de recarga conforme necessário.

Você pode saber mais sobre créditos de comunicações [aqui](what-are-communications-credits.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Se a sua organização ainda não tiver adquirido o licenciamento de audioconferência necessário, decida se você adquirirá licenças de conferência de áudio recorrendo as assinaturas existentes do Office 365 ou adquirindo licenças do complemento do áudio de audioconferência.</li><li>Decida se os créditos de comunicações são necessários para a implementação da videoconferência. Em caso positivo, decida o valor inicial de fundos a serem comprados. Onde aplicável, decida o valor do gatilho e o valor da recarga automática.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente os usuários que serão atribuídas a licenças de conferência de áudio.</li><li>Documentar o plano de créditos de comunicações (valor inicial, valor do gatilho, valor do Recarregamento automático)</li></ul>|

> [!TIP]
> Você pode documentar a lista de atribuição de licenças para usuários de audioconferência usando o exemplo a seguir.
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
> |Lahr de Louis|32 London Bridge Street|Office 365 E5|
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

-   Vários tipos de números de telefone da ponte de conferência (chamada tarifada e gratuita)

-   Várias categorias de números de telefone da ponte de conferência (dedicada e compartilhada)

-   Suporte de vários idiomas para a ponte de conferência (primária e secundária)

-   Um número de telefone padrão para o locatário

> [!NOTE]
> Os números de telefone da ponte de conferência dedicada contam para o limite de números de telefone que podem ser adquiridos por locatário, com base no número de licenças aplicáveis. Os números de telefone gratuitos da ponte de conferência não precisam de Créditos de Comunicação.

Se você deve transferir números de telefone da ponte de conferência existentes para o serviço de audioconferência, presumindo que eles atendam aos requisitos específicos do país — você pode transferir esses números de telefone da ponte de conferência existentes para a Microsoft.

> [!NOTE]
> A complexidade de transferir números de telefone para a Microsoft varia muito dependendo do país ou da região, da operadora, do número de circuitos envolvidos e de muitos outros fatores que contribuem. Trabalhe com seu provedor atual para investigar quanto tempo deve levar para ajudar a garantir que você inicie o processo cedo o suficiente para atender às suas linhas do tempo.

Para saber mais sobre os números de telefone da ponte de conferência, confira os seguintes artigos:

-   [Configurar Audioconferência no Microsoft Teams](set-up-audio-conferencing-in-teams.md)

-   [Números de telefone para audioconferência](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)

-   [Obter números de telefone de serviço](getting-service-phone-numbers.md)

-   [Transferir números de telefone para o Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se sua organização precisa de números de telefone de ponte de conferência dedicada.</li><li>Decida como os números de telefone da ponte de conferência dedicada serão obtidos para locais de usuários ou escritórios no escopo para a implementação de audioconferência (ou seja, obter da Microsoft ou transferir números de telefone existentes).</li><li>Se você optar por obtê-los da Microsoft, decida qual método usar (envio de formulário ou automático) para locais de usuários ou escritórios no escopo para a implementação de audioconferência.</li><li>Escolha as preferências de idioma a serem configuradas para cada número de telefone de uma ponte de conferência dedicada.</li><li>Determine o número de telefone da ponte de conferência padrão do locatário.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documentar o plano mestre para aquisição de número de telefone, detalhando como os números de telefone serão obtidos para cada local de usuário ou escritório em escopo para a implementação de audioconferência.</li><li>Se for aplicável, conclua o novo formulário de solicitação de número de telefone, um formulário para cada local ou Office.</li><li>Documentar as configurações detalhadas de número de telefone da ponte de conferência e os números de telefone da ponte de conferência compartilhada e dedicada, as preferências de idioma para cada número de telefone de Bridge de conferência dedicada, número de telefone da ponte de conferência padrão.</li></ul>|

Veja a seguir um exemplo de um modelo que você pode usar para capturar detalhes da ponte de conferência.

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

Para personalizar ainda mais a experiência do usuário, você pode configurar as opções de toda a organização para ingressar em reuniões de conferência de áudio (entrada de reunião e notificação de saída e registro de nome de chamadas), o comprimento do PIN do organizador da reunião e a notificação por email:

-   As notificações de entrada e saída de reuniões estão disponíveis na forma de nome, número de telefone e tons registrados.

-   O comprimento do PIN pode ter de 4 a 12 dígitos, com um PIN de 5 dígitos como padrão.

-   Os emails de notificação enviados na habilitação da licença de audioconferência ou de qualquer outra alteração controlada pelo administrador são habilitados por padrão. Você pode desabilitar esse recurso e assumir o controle das comunicações de usuário da sua organização.

Para os usuários que receberem uma licença de audioconferência, os números de chamada tarifada e de chamada gratuita padrão, exibidos nas coordenadas de audioconferência, podem ser configurados para usar:

-   O padrão no nível do locatário.

-   Os números de telefone da ponte de conferência atribuídos automaticamente.

-   Os números de telefone de uma ponte de conferência configurados manualmente para cada usuário.

Os números de telefone da ponte de conferência específica do usuário são geralmente úteis em organizações mundiais ou mundiais nas quais os usuários são distribuídos e devem fornecer números locais como os números de telefone da ponte de conferência padrão em seus convites de reunião.

Os participantes que ingressam em diferentes cidades ou no exterior podem procurar números adicionais configurados no nível do locatário, mas esses números não aparecem diretamente nos convites da reunião. Os convites da reunião fornecem um link que leva os participantes à página de números de discagem de **conferência** do teams para que eles procurem o número de telefone da ponte de conferência mais próximo à sua localização.

Você também pode configurar como os chamadores não autenticados são manipulados por cada organizador de reunião — seja para exigir que o organizador da reunião inicie a reunião antes que os chamadores não autenticados possam ser admitidos ou permitir que chamadores não autenticados iniciem uma reunião .

Você também pode aplicar configurações adicionais para cada usuário para controlar o uso de números de telefone de pontes de conferência gratuitas e discar de uma conferência.

> [!NOTE]
> Esses controles relacionados a custo estão atualmente disponíveis somente para clientes da prévia. Você pode inscrever sua organização no programa de visualização https://www.skypepreview.comde.

Com esses controles, você pode decidir se os organizadores da reunião podem fornecer números de telefone da ponte de conferência gratuita para reuniões organizadas por eles e se os participantes podem discar a partir das reuniões que organizam. O nível de controle de discagem externa não impede completamente o acesso discado, para permitir a discagem para números domésticos, permitindo discagem para números domésticos e internacionais.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se a sua organização requer notificações de entrada e de saída e, se houver, o tipo de notificação a ser implementada (tons, número de telefone ou nome registrado).</li><li>Determine o comprimento do PIN da audioconferência que atenda aos requisitos de segurança da sua organização.</li><li>Decida se a sua organização deseja assumir o controle das comunicações dos usuários relacionadas ao serviço de audioconferência.</li><li>Decidir os números de telefone da ponte de conferência a serem atribuídos a cada organizador da reunião.</li><li>Decida se alguns organizadores de reuniões precisam usar números de telefone de ponte de conferência de chamadas gratuitas para suas reuniões.</li><li>Decida se alguns organizadores de reuniões precisam permitir que chamadores não autenticados iniciem uma reunião.</li><li>Decida se alguns organizadores da reunião precisam de controle de discagem para serem controlados.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documentar detalhadamente as configurações de ponte de conferência (notificações de entrada e saída, tamanho do PIN, notificação por email de alteração do configurações)</li><li>Documente os números de telefone da ponte de conferência a serem atribuídos a cada organizador da reunião e a configuração correspondente para controlar a política de chamadores não autenticados e os controles de chamada gratuita e de discagem.</li></ul>|

> [!TIP]
> As configurações da ponte de conferência podem ser documentadas como no exemplo a seguir.
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
> Você pode documentar a lista de atribuições de configurações de ponte de conferência para usuários de audioconferência usando o exemplo a seguir.
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
> |Lahr de Louis|32 London Bridge Street|+44 20 7946 0001|TBA|Sim|Desabilitado|Não permitido|
> |Marcel Beauchamp|39 quai du Président Roosevelt|TBA|TBA|Não|Desabilitado|Doméstico|
> |Rachelle Cormier|39 quai du Président Roosevelt|TBA|TBA|Sim|Habilitado|Doméstico e internacional|
> |Isabell Potvin|39 quai du Président Roosevelt|TBA|TBA|Não|Desabilitado|Doméstico|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Gerenciar números de telefone de voz na nuvem

Para a implementação de videoconferência, você pode optar por adquirir novos números de telefone ou transferir/portar números de telefone existentes.

Para permitir que os usuários disquem números de telefone de acordo com o qual estão acostumados, como omitir códigos de área para chamadas locais, omitindo o código do país para chamadas domésticas ou usando a discagem de dígito curto ao executar a discagem de conferência, você pode configurar um plano de discagem personalizado e atribua-o a usuários.

## <a name="acquire-new-telephone-numbers"></a>Adquirir novos números de telefone

Os dois tipos de números de telefone dentro do Microsoft Cloud Voice soluções são:

-   Números de assinante (usuário), que podem ser atribuídos a usuários em sua organização.

-   Números de serviço, disponíveis como números de serviço de chamada tarifada e gratuita, que têm capacidade de chamada simultânea maior do que os números de assinantes e podem ser atribuídos a serviços como videoconferências, atendedores automáticos ou filas de chamadas.

Para obter mais informações sobre esses tipos de números de telefone, consulte [diferentes tipos de números de telefone usados para planos de chamada](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans).

A contagem total de números de telefone que você pode obter depende dos tipos de número de telefone e do número de licenças que você comprou e atribuiu aos seus usuários.

Quando se trata de números de serviço, você precisa planejar cuidadosamente a implementação da videoconferência. Avalie se a sua empresa exige números de telefone de ponte de conferência dedicada; caso contrário, sua organização pode optar por usar números de telefone de ponte de conferência compartilhada.

Para obter mais informações sobre a contagem total de números de telefone que você pode obter, consulte quantos [números de telefone você pode obter?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida quais são os locais do usuário ou os escritórios nos quais novos números de telefone serão adquiridos da Microsoft.</li><li>Decida o tipo de número de telefone a ser adquirido da Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documentar os locais do usuário ou os escritórios nos quais novos números de telefone serão adquiridos da Microsoft.</li><li>Documentar o tipo de número de telefone a ser adquirido da Microsoft.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Transferir números de telefone existentes

Se sua organização quer transferir (ou porta) números de telefone existentes para a Microsoft, você pode fazer isso enviando uma solicitação de pedido de portabilidade à Microsoft.

Você pode transferir todos os seus números de telefone existentes ao mesmo tempo (porta completa) e, em alguns mercados, você pode transferir um subconjunto de seus números de telefone existentes (porta parcial). Uma porta parcial pode ser útil em casos em que você apenas deseja mover sua ponte de conferência discada para o serviço de audioconferência.

Um único pedido de portabilidade só pode transferir os números de telefone para um único tipo de número de telefone. Se você precisar transferir alguns números de telefone como números de assinante e alguns como números de serviço, recomendamos que primeiro conclua a transferência para a Microsoft e, em seguida, realize a conversão assim que os números estiverem dentro do controle da Microsoft.

Como alternativa, se houver suporte para a porta parcial, você pode enviar várias solicitações de porta, uma solicitação de uma porta por vez. No entanto, essa abordagem alternativa prolongará seu contrato com o provedor de serviços de telecomunicações existente.

Portabilidade de número de telefone é um tópico complexo e requer planejamento, coordenação e gerenciamento adequado das expectativas dos seus participantes. Para saber mais, confira os seguintes artigos:

-   [Transferir números de telefone para o Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [Perguntas comuns sobre transferência de números de telefone](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida quais são os locais do usuário ou os escritórios nos quais os números de telefone existentes serão transferidos para a Microsoft.</li><li>Decida o tipo de número de telefone a ser transferido para a Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documentar os locais do usuário ou os escritórios nos quais os números de telefone existentes serão transferidos para a Microsoft.</li><li>Documentar o tipo de número de telefone a ser transferido para a Microsoft.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Planos de discagem

Um plano de discagem no recurso do sistema de telefonia do Office 365 é um conjunto de regras de normalização que traduz os números de telefone discados para um formato alternativo (normalmente, o formato E. 164) para autorização de chamadas e roteamento de chamadas. O serviço de audioconferência usa os mesmos recursos usados pelo sistema telefônico para converter números de telefone discados em cenários de discagem de conferência (por exemplo, convidar participantes via PSTN e discagem, recurso "ligar para mim").

No recurso do sistema de telefonia do Office 365, há dois tipos de planos de discagem:

-   **Plano de discagem do serviço:** Esse é o plano de discagem padrão que é aplicado aos usuários com base no local de uso do Office 365 e não pode ser modificado.

-   **Plano de discagem do locatário:** Esse é um plano de discagem personalizável dentro de um locatário, que é dividido em dois tipos:

    -   **Locatário-plano de discagem global:** O plano de discagem que se aplica a todos os usuários no locatário.

    -   **Locatário-plano de discagem do usuário:** O plano de discagem que se aplica somente a usuários específicos.

O plano de discagem efetivo atribuído a usuários é a combinação do plano de discagem de serviço (com base no local de uso do Office 365 de um usuário) e o plano de discagem do locatário (pode ser o plano de discagem global do locatário ou o plano de discagem do usuário do locatário).

A ![tabela mostra três combinações de planos de discagem de serviço e locatário.] A (media/audio_conferencing_image8.png "tabela mostra três combinações de planos de discagem de serviço e locatário.")

> [!Important]
> Pode haver no máximo 25 regras de normalização em cada plano de discagem de locatário; Portanto, é importante evitar a duplicação de regras de normalização que já estão disponíveis como parte do plano de discagem do serviço.

Para saber mais sobre planos de discagem, consulte [o que são planos de discagem?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Decida se sua organização requer planos de discagem personalizados (requisitos comerciais, requisitos de adoção e assim por diante).</li><li>Se aplicável, decida o escopo do plano de discagem de locatário (locatário-global ou locatário-User) para dar suporte aos requisitos para planos de discagem personalizados.</li><li>Se aplicável, decida os planos de discagem de locatário que você criará para dar suporte a locais do usuário ou escritórios no escopo para a implementação de voz na nuvem.</li><li>Se aplicável, decida quais usuários exigem um plano de discagem personalizado e o plano de discagem do locatário a ser atribuído para cada usuário.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximas etapas|<ul><li>Documente os planos de discagem personalizados e as regras de normalização associadas a serem configuradas como parte da sua implementação de voz em nuvem.</li><li>Documente os usuários aos quais será atribuído um plano de discagem personalizado e o plano de discagem de locatário a ser atribuído para cada usuário.</li></ul>|

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