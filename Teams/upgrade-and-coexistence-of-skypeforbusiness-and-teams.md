---
title: Escolha sua jornada de atualização de Skype for Business para Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl, bjwhalen
description: Detalhes das Skype for Business e Microsoft Teams de coexistência e de possíveis viagens de atualização para Teams, com cenários de exemplo.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: deb64412a96ece539decd8dc2145067a91a1b95f
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2021
ms.locfileid: "61562813"
---
# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Escolha a jornada de atualização do Skype for Business para o Teams

![Atualize o diagrama de jornada, enfatizando o estágio Project Definição.](media/upgrade-banner-project-definition.png "Etapas da jornada de atualização, com ênfase no estágio de Definição do Projeto")

Este artigo faz parte do estágio de Definição do Projeto da sua jornada de atualização. Antes de prosseguir, confirme se você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](./upgrade-define-project-scope.md)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)

Como um cliente existente do Skype for Business, sua transição completa para o Teams poderá levar algum tempo. Além disso, para começar a tirar proveito ainda hoje das vantagens do Microsoft Teams, você pode habilitá-lo juntamente com o Skype for Business. Como há algumas funcionalidades sobrepostas entre os dois aplicativos, recomendamos que você revise os modos de coexistência e atualização disponíveis para ajudar a determinar qual caminho é o certo para sua organização. Por exemplo, você pode optar por habilitar todas as cargas de trabalho nas duas soluções sem interoperabilidade. Ou então, você pode optar por gerenciar a experiência do usuário, introduzindo gradualmente os recursos do Teams ou direcionando grupos de usuários para os recursos selecionados, até que sua organização esteja pronta para atualizar todos para o Teams. Use o resultado do seu piloto para ajudar a determinar a melhor jornada de atualização para sua organização.

> [!IMPORTANT]
> Skype for Business Online foi aposentado em 31 de julho de 2021. Para maximizar a realização dos benefícios e garantir que sua organização tenha tempo adequado para implementar a atualização, recomendamos que você comece hoje sua jornada para o Microsoft Teams.

Esse artigo descreve os vários modos que lhe permitem gerenciar quais modalidades no Skype for Business e no Teams estarão disponíveis para seus usuários. Como em qualquer implantação, recomendamos que você [teste seu plano pretendido](pilot-essentials.md) com um grupo selecionado de usuários antes de atualizar sua organização para o Teams. Lembre-se de que a introdução de novas tecnologias pode causar problemas aos usuários. Reserve um tempo para avaliar a prontidão do usuário e implementar um plano de comunicação e treinamento antes de implementar qualquer um dos modos descritos aqui.

> [!TIP]
> Junte-se a nós para workshops interativos ao vivo nos quais compartilharemos orientações, práticas recomendadas e recursos projetados para iniciar o planejamento e a implementação de atualização.
>
>Para começar, participe primeiro da sessão de [Planejamento da atualização](./upgrade-workshops-landing-page.yml).


## <a name="upgrade-journey-building-blocks"></a>Blocos de construção da jornada de atualização

Para preparar formalmente sua organização para a jornada para o Teams, você precisa começar a planejar os cenários de atualização que permitirão que sua organização adote totalmente o Teams como única solução de comunicação e colaboração.

Para lhe ajudar no processo de tomada de decisão, familiarize-se com os vários modos, conceitos e terminologia relevantes para a atualização do Skype for Business para o Teams. Para obter mais informações, [consulte Microsoft Teams e Skype for Business coexistência e interoperabilidade.](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)

> [!NOTE]
> Você também precisará considerar seus cenários de migração de voz. Sistema de Telefonia é a tecnologia da Microsoft para habilenciar o controle de chamada e recursos de PBX (Private Branch Exchange) na Microsoft 365 ou Office 365 nuvem. Para conectar Sistema de Telefonia à PSTN (Rede Telefônica Pública Comucionada) para que os usuários possam fazer chamadas telefônicas em todo o mundo, você tem opções com base na sua necessidade de negócios. Para obter mais informações sobre Sistema de Telefonia e opções de conectividade PSTN, consulte [Voice - Sistema de Telefonia e conectividade PSTN](cloud-voice-landing-page.md).

Um usuário que migrou para o Teams não usa mais um cliente do Skype for Business, exceto para ingressar em uma reunião hospedada no Skype for Business. Todos os chats e chamadas de entrada chegam no cliente Teams usuário, independentemente de o remetente usar Teams ou Skype for Business. Todas as novas reuniões organizadas pelo usuário atualizado serão agendadas como reuniões do Teams. Se o usuário tentar usar o cliente do Skype for Business, o início de chats e chamadas será bloqueado <sup>1</sup>. No entanto, o usuário ainda pode (e deve) usar o cliente do Skype for Business para ingressar nas reuniões que tenha sido convidado.

Os administradores gerenciam a transição para o Teams usando o conceito de [modo](migration-interop-guidance-for-teams-with-skype.md), que é uma propriedade do [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps&preserve-view=true). Um usuário que foi migrado para Teams conforme descrito acima está no modo "TeamsOnly". Para uma organização que esteja migrando para o Teams, o objetivo final é mover todos os usuários para o modo TeamsOnly.

Há dois métodos para migrar uma organização existente com o Skype for Business (online ou local) para o Teams:

- **Método de recursos sobrepostos** (usando o modo de Uso Paralelo): os usuários de uma organização existente do Skype for Business são introduzidos ao Teams para que possam usar os dois clientes lado a lado durante uma fase de transição. Durante esse período, quase todas as funcionalidades do Teams estarão disponíveis para eles. O modo para essa configuração é referenciado como Uso Paralelo, e esse é o modo padrão para qualquer organização existente com o Skype for Business. Assim que a organização estiver pronta, o administrador moverá os usuários para o modo TeamsOnly.

- **Método de recursos selecionados** (usando um ou mais dos modos Skype for Business): o administrador gerencia a transição (do Skype for Business para as equipes) da funcionalidade de chat, chamadas e agendamento de reunião para os usuários da organização. Cada uma dessas funções está disponível no Skype for Business ou no Teams, mas não em ambas. Os administradores usam o TeamsUpgradePolicy para controlar quando mudar essa funcionalidade para o Teams dos seus usuários. Os usuários que ainda não estão no modo TeamsOnly continuarão a usar o Skype for Business para chats e chamadas, e os dois conjuntos de usuários poderão se comunicar por meio da funcionalidade de interoperabilidade. Os administradores gerenciam a transição migrando progressivamente mais usuários para o modo TeamsOnly.

<sup>1</sup> Clientes Skype for Business antigos enviados antes de 2017 não honram TeamsUpgradePolicy. Verifique se você está usando o cliente do Skype for Business mais recente disponível no canal do Office.

Depois de entender e escolher seu método de atualização, você pode aprender sobre as ferramentas para gerenciar a atualização da sua organização [para](upgrade-to-teams-on-prem-tools.md)Teams .

A seguir estão os principais fatores que ajudarão a decidir o caminho apropriado para sua organização.

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Método de recursos sobrepostos (usando o modo de Uso Paralelo)

Com o método de recursos sobrepostos, os usuários podem usar os clientes do Teams e do Skype for Business para chats, chamadas VoIP e reuniões. Nesse método, o chat e as chamadas VOIP no Teams são focadas na organização, enquanto o Skype for Business permite o chat e as chamadas VOIP/PSTN com organizações externas (se for configurado). As reuniões podem ser agendadas e assistidas nos dois produtos.

Ao usar o método de recursos sobrepostos, o tráfego de comunicação do Skype for Business e do Teams permanece separado (mesmo que seja para o mesmo usuário), e os dois clientes diferentes nunca se comunicam entre si (para usuários da mesma organização). As experiências do usuário se baseiam na configuração do destinatário. Por exemplo, suponha que o usuário A do destinatário está no modo Ilhas:

- A comunicação iniciada a partir do cliente Skype for Business usuário sempre será acionada no cliente de Skype for Business usuário A.

- A comunicação iniciada Teams cliente  de um usuário na mesma organização sempre será iniciada no cliente Teams usuário A.

- A comunicação iniciada Teams cliente de um usuário em uma *organização externa* sempre estará no cliente Skype for Business Usuário A.

Se você tiver atribuído uma licença Microsoft 365 ou Office 365 aos usuários, essa será a experiência de atualização padrão para sua organização. Quando você atribui uma Microsoft 365 ou Office 365, as licenças Teams e Skype for Business Online são atribuídas por padrão.<sup> 2</sup>

Para que esse método funcione efetivamente, todos os usuários devem executar ambos os clientes simultaneamente. Os chats e chamadas recebidos de dentro da organização para um usuário no modo de Uso Paralelo podem chegar ao cliente do Skype for Business ou do Teams, mas isso não está sob o controle do destinatário. Depende de qual cliente o remetente usa para iniciar a comunicação. Se o remetente e o destinatário estiverem em organizações diferentes, chamadas e chats recebidos para um usuário no modo de Uso Paralelo sempre chegam ao cliente do Skype for Business.

Por exemplo, se um destinatário do modo de Uso Paralelo estiver conectado ao Skype for Business, mas não ao Teams, e alguém enviar mensagens pelo Teams, o destinatário do modo de Uso Paralelo não verá a mensagem (mas, eventualmente, receberá um email informando que uma mensagem no Teams foi perdida). Da mesma forma, se um usuário estiver executando o Teams, mas não o Skype for Business, e alguém enviar mensagens a esse usuário pelo Skype for Business, o usuário não verá esse chat. O comportamento em cada um desses casos é semelhante para chamadas. Se os usuários não executarem ambos clientes, isso poderá terminar facilmente em frustração.

A presença também funciona independentemente entre Teams e Skype for Business quando você usa esse método de atualização. Isso significa que outros usuários podem ver estados diferentes de presença para o Usuário A, dependendo do cliente usado. Para saber mais, confira [Presença](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence).

- Outros usuários, ao usar Teams, verão presença com base na atividade do Usuário A no Teams.

- Outros usuários, ao usar Skype for Business, verão presença com base na atividade do Usuário A no Skype for Business.

Assim que estiver pronto para atualizar os usuários para o modo TeamsOnly, você poderá atualizar os usuários individualmente ou atualizar todo o locatário de uma só vez usando a política do locatário<sup>3</sup>. Assim que um usuário é atualizado para o modo TeamsOnly, ele recebe todos os chats e chamadas recebidos no Teams. (Observe que a migração de reuniões Skype for Business para reuniões Teams somente é disparada ao aplicar o TeamsUpgradePolicy a usuários individuais, não por locatário. Consulte [Migração de Reunião](upgrade-to-teams-on-prem-tools.md#meeting-migration) para obter detalhes.)

No entanto, os destinatários não atualizados para o modo de Uso Paralelo poderão continuar recebendo chats e chamadas de um usuário do TeamsOnly nos clientes do Skype for Business ou do Teams. Para conversas existentes, o usuário do TeamsOnly responderá ao cliente do remetente que iniciou o chat ou a chamada. 

Para novas conversas do ponto de vista do usuário teamsOnly, o chat ou a chamada sempre irão para o modo de ilhas usuários Teams cliente. Isso ocorre porque o cliente do Teams mantém threads de conversas separadas para comunicações de Teams para Teams e de Teams para Skype for Business, mesmo que seja para o mesmo usuário. Para saber mais, confira [Conversas do Teams – Interoperabilidade versus threads nativos](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability).

A tabela a seguir resume a experiência do Teams no modo de Uso Paralelo e no modo TeamsOnly:

| Experiência do Teams | No modo de Uso Paralelo | No modo TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Chats e chamadas recebidos no:|  Teams ou Skype for Business | Teams |
| Chamadas PSTN recebidas em: | Skype for Business <br>(Não há suporte para o uso da funcionalidade PSTN no Teams no modo de Uso Paralelo.)     | Teams |   
 |Presença    | A presença no Skype for Business e no Teams é independente. Os usuários podem ver estados diferentes para o mesmo usuário de Uso Paralelo, dependendo do cliente usado. | A presença baseia-se exclusivamente na atividade do usuário no Teams. Todos os outros usuários, independentemente de qual cliente usam, veem essa presença. | 
 | Agendamento de reuniões    | Os usuários podem agendar reuniões no Teams ou no Skype for Business. Por padrão, eles verão os dois Outlook. Você pode definir uma política de reunião Teams para controlar se os usuários só podem usar o add-in de reunião do Teams ou os Teams de reunião e Skype for Business de reunião. Para saber mais, confira [definir o provedor de reunião para usuários no modo Ilhas.](meeting-policies-in-teams-general.md#meeting-provider-for-islands-mode) |     Os usuários só agendam reuniões no Teams. Somente o suplemento do Teams está disponível no Outlook. | 

A tabela a seguir resume os prós e os contras de usar o método de recursos sobrepostos para migrar sua organização para o Teams.

| Prós     |       Contras |
| :------------------ | :---------------- |
| Permite a adoção rápida dentro de uma organização.| Potencial para confundir o usuário final, porque há dois clientes com funcionalidade semelhante, mas interfaces de usuário diferentes. Além disso, eles não têm controle sobre em qual cliente chegarão os chats/chamadas recebidos. |
| Permite que os usuários aprendam e se familiarizem com o Teams enquanto ainda têm acesso total ao Skype for Business. | Potencial de insatisfação do usuário final devido a mensagens perdidas, caso o usuário não esteja executando ambos os clientes.|
| Esforço administrativo mínimo para começar a usar o Teams. | Pode ser um desafio sair do modo "sair das Ilhas" e ir para o modo TeamsOnly se os usuários e aqueles com quem eles se comunicam regularmente não estão usando ativamente Teams. Por exemplo, uma vez que um subconjunto de usuários é atualizado para o modo TeamsOnly, esses usuários só enviarão Teams. Para o restante da população no modo Ilhas, essas mensagens sempre serão Teams. Mas se parte dessa população não estiver executando Teams, elas perceberão essas mensagens como perdidas.|
|Permite que os usuários aproveitem os recursos para aprimorar o trabalho em equipe que não está disponível no Skype for Business.| Um usuário que esteja usando o Skype for Business no local e o Teams não poderá se comunicar do Teams com outro usuário que esteja usando o Skype for Business no local, mas não tenha o Teams.  |
|  | Ao usar Teams, os usuários que têm uma conta local no Skype for Business Server não têm suporte de interop ou federação.  Isso pode gerar confusão se você tiver uma mistura de usuários de Ilhas, alguns que estão no Skype for Business Online e outros no Skype for Business local.   |

<sup>2</sup> Isso é verdadeiro mesmo se o usuário estiver no local no Skype for Business Server. Se o usuário estiver hospedado no local ou online, deixe a licença do Skype for Business Online habilitada, pois atualmente ela é necessária para a funcionalidade completa do Teams.

<sup>3</sup> Observe que a migração de reuniões Skype for Business para reuniões Teams só é disparada ao aplicar o TeamsUpgradePolicy a usuários individuais, não por locatário. Para obter detalhes, confira [Migração de reunião](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Método de recursos selecionados (usando os modos do Skype for Business)

Algumas organizações podem optar por fornecer aos usuários finais uma experiência mais previsível à medida que a organização faz a transição do Skype for Business para o Teams. Nesse modelo, os administradores de TI usam um dos modos do Skype for Business no TeamsUpgradePolicy para designar explicitamente quais recursos permanecem no Skype for Business antes de migrar para o modo TeamsOnly. Quando os usuários estiverem prontos para mudar os recursos selecionados para o modo TeamsOnly, o administrador atualizará o modo deles para o TeamsOnly. Durante a transição:

- Os administradores têm opções para habilitar determinados recursos do Teams para os usuários, mantendo os recursos de chat e chamadas no Skype for Business antes dos usuários migrarem para a experiência do TeamsOnly. A administração pode habilitar os recursos de colaboração do Teams ou os recursos de colaboração e reuniões do Teams.

- Os usuários ainda em Skype for Business recebem todos os chats de entrada e chamadas em seu cliente Skype for Business, independentemente de a comunicação ter se originado do cliente Teams ou Skype for Business do outro usuário. Além disso, para esses usuários Skype for Business, a funcionalidade de chamada e chat no cliente Teams está desabilitada para ajudar a evitar a confusão do usuário final e a garantir o roteamento e a presença adequadas.

- Os usuários no modo TeamsOnly recebem todos os chats e chamadas recebidos no cliente do Teams e a presença é fornecida pelo Teams, independentemente de onde a comunicação se originou: Teams, Skype for Business ou qualquer tipo de usuário federado.

Ao contrário do método de recursos sobrepostos (Ilhas), no método select capabilities, os usuários que usam Skype for Business podem se comunicar com os usuários que estão no TeamsOnly. A comunicação entre um Skype for Business usuário e Teams usuário é conhecida como [interoperabilidade](teams-and-skypeforbusiness-coexistence-and-interoperability.md#interoperability) ou "interoperabilidade". A comunicação de interoperabilidade é possível bilateralmente para chats e chamadas entre um usuário no Skype for Business e outro usuário no Teams. Além disso, os usuários convidados sempre podem participar de uma reunião do Skype for Business ou do Teams; embora, devam usar um cliente que corresponda ao tipo de reunião. Para mais informações, confira [Reuniões](teams-and-skypeforbusiness-coexistence-and-interoperability.md#meetings).

Para usuários em um método de transição de recursos selecionado, a presença de um usuário é consistente independentemente de qual cliente é usado pelo outro usuário. Se o usuário estiver em um dos modos Skype for Business, todos os outros usuários verão presença com base na atividade desse usuário no Skype for Business. Da mesma forma, se um usuário estiver no modo TeamsOnly, todos os outros usuários verão presença com base na atividade desse usuário no Teams. Para obter detalhes, confira [Presença](teams-and-skypeforbusiness-coexistence-and-interoperability.md#presence).

Para uma organização que ainda não começou a usar Teams, o administrador deve alterar o modo de locatário de Ilhas para SfbWithTeamsCollab. (Para organizações que já têm algum uso Teams, o administrador deve "avô" usuários já ativos no Teams para garantir que essa alteração não se aplique a eles. Para obter detalhes, consulte [Um método select capabilities para uma organização que](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)já está usando Teams no modo Ilhas .) 

As experiências dos usuários convidados irão aderir ao modo de coexistência atribuído ao locatário. Se você definir um modo do Skype for Business no nível de locatário, os convidados não poderão usar o chat, fazer chamadas ou mostrar sua presença. Para saber mais, leia [Acesso de convidados no Teams](guest-access.md).

Quando o modo muda de Uso Paralelo para SfbWithTeamsCollab, um usuário que nunca usou o Teams não verá diferença na maneira como usa o Skype for Business. No entanto, se esse usuário começasse a usar o Teams, ele estaria exposto apenas a funcionalidades como Arquivos, Teams e Canal. O agendamento de chats, chamadas e reuniões não estaria disponível no Teams, pois o administrador (por enquanto) designou o Skype for Business como o cliente desejado para essas funções.

> [!NOTE]
> Quando o Usuário A muda de Ilhas para um dos modos Skype for Business, o cliente Teams de qualquer outro usuário que se comunica com o Usuário A precisa saber que o modo do Usuário A foi alterado para que ele possa rotear a comunicação para o cliente apropriado para o Usuário A. Para qualquer usuário que já tenha estabelecido conversas Teams para Teams nativas com o Usuário A, pode levar até 36 horas para que os clientes do Teams desses outros usuários tenham conhecimento da mudança de modo de Ilhas para qualquer modo Skype for Business. Por outro lado, as alterações de um usuário existente para o modo TeamsOnly são descobertas por outros clientes dentro de 2 horas.<br>
> Quando os administradores estão prontos, eles podem transferir o chat, a chamada e o agendamento de reunião para um determinado usuário Teams de uma vez atualizando o modo do usuário para o TeamsOnly.

Como alternativa, o administrador poderá primeiro mudar apenas o agendamento de reuniões para o Teams, deixando as funções de chats e chamadas no Skype for Business usando o modo SfBWithTeamsCollabAndMeetings. Esse modo permite que as organizações transigam para o Teams para reuniões— se os usuários ainda não estão prontos para migrar para o modo TeamsOnly (por exemplo, se você ainda não estiver pronto para migrar a funcionalidade PSTN existente). Esse cenário de transição é conhecido como [Primeiro Reuniões](meetings-first.md).


|Experiência do Teams  |No modo SfBWithTeamsCollab |No modo SfBWithTeamsCollabAndMeetings |No modo TeamsOnly  |
|---------|---------|---------|---------|
|Chats e chamadas VOIP de usuários em sua organização recebidos em:     | Skype for Business        | Skype for Business       | Teams        |
|Chamadas PSTN recebidas em:     | Skype for Business        |Skype for Business         | Teams        |
|Presença     | Skype for Business        |Skype for Business         | Teams        |
|Agendamento de Reunião     | Skype for Business         | Teams        | Teams        |


A tabela a seguir resume os prós e os contras do uso dos modos do Skype for Business como uma etapa de transição para o modo TeamsOnly.

| Prós     |       Contras |
| :------------------ | :---------------- |
| Roteamento previsível para o usuário final. Todas as chamadas e chats chegam ao Skype for Business ou Teams (mas não a ambos), com base na seleção do administrador.|As conversas de interoperabilidade não têm suporte para o compartilhamento de tela, compartilhamento de arquivos e rich text. Isso pode ser tratado, aproveitando a funcionalidade de Reunir Agora para iniciar uma reunião. |
|Poderá reduzir as chances de um usuário final se confundir, devido a uma determinada funcionalidade está disponível apenas em um cliente. | Antes que os usuários sejam atualizados para o TeamsOnly, eles não têm acesso Teams para atividades comuns executadas em Skype for Business como chat e chamada. Ou seja, nenhum recurso lado a lado.|
|O administrador tem controle sobre o conjunto de recursos disponíveis para os usuários durante a transição de Skype for Business para Teams. Esse controle inclui a capacidade de introduzir recursos de Teams incrementalmente. | |
| Permite que uma organização use o Teams para reuniões, mesmo que ainda não esteja pronta para mudar inteiramente para o modo TeamsOnly.||
|A presença de um determinado usuário é a mesma, conforme visualizada por outros, independentemente do cliente usado.||

## <a name="summary-of-upgrade-methods"></a>Resumo dos métodos de atualização
A tabela a seguir resume os métodos de atualização:


|Recursos sobrepostos (usando o modo de Uso Paralelo)  |Recursos selecionados (usando os modos do Skype for Business)  |
|---------|---------|
|Antes de serem atualizados para o TeamsOnly, os usuários devem executar ambos os clientes simultaneamente, pois os chats e chamadas recebidos podem chegar a qualquer cliente.     | Os chats e chamadas só são fixos em um cliente, com base no modo do destinatário. Usuários não atualizados podem executar ambos os clientes, mas não há sobreposição funcional (chamadas e chats não estão disponíveis no Teams). Os administradores também podem controlar se os usuários agendam reuniões Teams ou Skype for Business.         |
|Permite que os administradores introduzam a funcionalidade sobreposta (chat, reuniões, chamada VOIP) no Skype for Business e no Teams para usuários finais (permitindo funcionalidade lado a lado), bem como novos recursos (Teams e Canais) no Teams.     | Permite que os administradores introduzam a funcionalidade selecionada do Teams para usuários finais (Teams e Canais), sem fornecer a mesma funcionalidade que também existe no Skype for Business.        |
|A interoperabilidade entre o Skype for Business e o Teams não existe enquanto os dois usuários estão no modo de Uso Paralelo. Depois que alguns usuários são atualizados para o TeamsOnly, a conversa de interopção pode ocorrer entre esses usuários e outros usuários que ainda estão no modo Ilhas. No entanto, os usuários de ilhas podem optar por usar Teams e evitar a conversa de interop.      |A interoperabilidade é necessária para a comunicação entre usuários do Skype for Business e do Teams.         |

> [!NOTE]
> Caso não consiga seguir os métodos com suporte para migrar os usuários do Skype for Business Server para o Teams, seria possível fazer a transição dos usuários para o Teams removendo o Skype for Business Server e todos os atributos de usuário relacionados no Active Directory. Depois que os atributos Azure Active Directory usuários tiverem sido limpos dos atributos Skype for Business Server e registros DNS tiverem sido apontados novamente para Microsoft 365 ou Office 365, seria possível licenciar os usuários em Microsoft 365 ou Office 365 atualize-os para Teams. 

> [!IMPORTANT]
> Com a migração de substituição, os dados de contatos e de reuniões não serão migrados do ambiente local para o Microsoft Teams.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Ponto de decisão</td><td><ul> Qual jornada de atualização é adequada aos requisitos de negócios da sua organização?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Próxima etapa</td><td><ul> Identificar seu modelo de implantação atual, usar cenários de caso e considerações-chave para sua organização informará a jornada para Teams que é mais adequada à sua organização.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Ponto de decisão</td><td><ul> Qual cenário de atualização é aplicável à sua organização?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul> Decida a linha do tempo da jornada de atualização da sua organização com base nos requisitos de mensagens, reuniões e chamadas de negócios.<br><br> Decida o trabalho adicional necessário para concluir a jornada de atualização.<br><br></ul></td></tr>
</table>

Depois de escolher a melhor jornada de atualização para sua organização, [execute sua atualização para](./upgrade-to-teams.md)Teams .

## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar conectividade híbrida entre Skype for Business Server e Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps&preserve-view=true)

[Usando o Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)