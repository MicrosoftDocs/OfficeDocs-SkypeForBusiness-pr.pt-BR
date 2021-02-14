---
title: Atualizar para o Teams a partir de uma implantação local do Skype for Business – Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Atualização do Skype for Business para o Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2dc8afc48db6264cef5c5ad959f33dd7e738e116
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515788"
---
# <a name="upgrade-methods-mdash-for-it-administrators"></a>Métodos de atualização &mdash; para administradores de IT

Este artigo descreve os métodos de atualização para migrar para o Teams. Este artigo é o segundo de vários que descrevem conceitos de atualização e implementação para administradores de IT.  

- [Visão geral](upgrade-to-teams-on-prem-overview.md)
- **Métodos de atualização** (este artigo)
- [Ferramentas para gerenciar sua atualização](upgrade-to-teams-on-prem-tools.md)
- [Considerações adicionais para organizações com o Skype for Business local](upgrade-to-teams-on-prem-considerations.md)
- [Implementando sua atualização](upgrade-to-teams-on-prem-implement.md)
- [Considerações sobre A Rede Telefônica Pública Comutado (PSTN)](upgrade-to-teams-on-prem-pstn-considerations.md)

Além disso, os artigos a seguir descrevem conceitos de atualização importantes e comportamentos de coexistência:

- [Coexistência do Teams e do Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistência - Referência](migration-interop-guidance-for-teams-with-skype.md)
- [Experiência e conformidade do cliente do Teams a modos de coexistência](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="upgrade-methods"></a>Métodos de atualização

Há dois métodos para atualizar uma organização existente com o Skype for Business (online ou local) para o Teams: método de sobreposição de recursos e o método selecionar recursos. Este artigo ajuda você a escolher o método certo para sua organização, descrevendo os dois métodos e apresentando os prós e contras de cada um. 

- [Método de recursos sobrepostos (usando o modo de Uso Paralelo)](#overlapping-capabilities-method-using-islands-mode)

   Os usuários em uma organização existente do Skype for Business são introduzidos ao Teams para que possam usar ambos os clientes durante uma fase de transição. Durante esse período, quase todas as funcionalidades do Teams estarão disponíveis para eles. O modo para essa configuração é referenciado como Uso Paralelo, e esse é o modo padrão para qualquer organização existente com o Skype for Business. Quando a organização estiver pronta, o administrador move os usuários para o modo TeamsOnly.

- [Método de seleção de recursos (usando um ou mais dos modos do Skype for Business)](#select-capabilities-method-using-skype-for-business-modes)

   O administrador gerencia a transição (do Skype for Business para o Teams) das funcionalidades de agendamento de chat, chamadas e reuniões para os usuários em sua organização.  Cada uma dessas funções está disponível no Skype for Business ou no Teams, mas não em ambas. Os administradores usam o TeamsUpgradePolicy para controlar quando mudar essa funcionalidade para o Teams dos seus usuários. Os usuários que ainda não estão no modo TeamsOnly continuarão a usar o Skype for Business para chats e chamadas, e os dois conjuntos de usuários poderão se comunicar por meio da funcionalidade de interoperabilidade. Os administradores gerenciam a transição migrando progressivamente mais usuários para o modo TeamsOnly.  

Depois de entender e escolher o método de atualização, você poderá saber mais sobre as ferramentas para gerenciar a atualização da sua organização [para o Teams.](upgrade-to-teams-on-prem-tools.md)

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Método de recursos sobrepostos (usando o modo de Uso Paralelo)

Com o método de recursos sobrepostos, os usuários podem usar os clientes do Teams e do Skype for Business para chats, chamadas VoIP e reuniões. Esse estado é chamado de modo "Ilhas", pois o tráfego de comunicação do Skype for Business e do Teams permanece separado (mesmo para o mesmo usuário) e os dois clientes diferentes nunca se comunicam entre si (para usuários dentro da mesma organização). Por exemplo, suponha que o usuário A do destinatário está no modo Ilhas:

- A comunicação iniciada pelo cliente do Skype for Business de outro usuário sempre chegará ao cliente do Skype for Business do Usuário A.

- As comunicações iniciadas a partir do cliente teams de outro usuário sempre entrarão no cliente do Teams do Usuário A, se o outro usuário *estiver na mesma organização.* 

- As comunicações iniciadas a partir do cliente teams de outro usuário sempre entrarão no cliente Skype for Business do Usuário A, se o outro usuário estiver em *uma organização federada.*

O modo Ilhas é o modo padrão do TeamsUpgradePolicy para qualquer organização existente que ainda não tenha atualizado para o TeamsOnly. Quando você atribui uma licença do Microsoft 365 ou do Office 365, as licenças do Teams e do Skype for Business Online são atribuídas por padrão. (Isso é verdadeiro mesmo se o usuário estiver instalado no Skype for Business Server. Se o usuário está no local ou online, deixe a licença do Skype for Business Online habilitada, pois ela é necessária para a funcionalidade completa do Teams. Na verdade, se você não tiver tomado nenhuma medida para alterar a configuração padrão, talvez já tenha um uso significativo do Teams em sua organização.  Esse é um dos benefícios da abordagem de recursos sobrepostos. Ele permite a adoção rápida e controlada pelo usuário final em uma organização.

Para que esse método funcione de forma eficaz, ele exige que todos os usuários executem os dois clientes simultaneamente. Os chats e chamadas recebidos de dentro da organização para um usuário no modo de Uso Paralelo podem chegar ao cliente do Skype for Business ou do Teams, mas isso não está sob o controle do destinatário. Se o remetente e o destinatário estão na mesma organização, depende do cliente que o remetente usa para iniciar a comunicação. Se o remetente e o destinatário estiverem em organizações diferentes, chamadas e chats recebidos para um usuário no modo de Uso Paralelo sempre chegam ao cliente do Skype for Business.  

Por exemplo, se um destinatário do modo Ilhas estiver executando o Skype for Business, mas não o Teams, e alguém na mesma organização o enviar pelo Teams, o destinatário do modo Ilhas não verá a mensagem (mas eventualmente receberá um email dizendo que perdeu uma mensagem no Teams). Da mesma forma, se um usuário estiver executando o Teams, mas não o Skype for Business, e alguém enviar mensagens a esse usuário pelo Skype for Business, o usuário não verá esse chat.  Eles receberão um email dizendo que houve uma mensagem perdida. O comportamento em cada um desses casos é semelhante para chamadas. Se os usuários não executarem ambos clientes, isso poderá terminar facilmente em frustração.

Quando o Usuário A está no modo Ilhas, a presença do Usuário A, como visto por outros usuários no Teams e no Skype for Business, é independente:

- Ao usar o Teams, os outros usuários verão a presença com base na atividade do Usuário A no Teams. 
- Ao usar o Skype for Business, os outros usuários verão a presença com base na atividade do Usuário A no Skype for Business. 

Isso significa que outros usuários podem ver estados diferentes de presença para o Usuário A, dependendo do cliente usado. Para obter mais informações, consulte [Presença.](upgrade-to-teams-on-prem-coexistence.md#presence)

Quando estiver pronto para atualizar os usuários para o modo TeamsOnly, você poderá atualizar os usuários individualmente ou atualizar o locatário inteiro de uma só vez usando a política de todo o locatário. Assim que um usuário é atualizado para o modo TeamsOnly, ele recebe todos os chats e chamadas recebidos no Teams. (Observe que a migração de reuniões do Skype for Business para reuniões do Teams só é disparada ao aplicar o TeamsUpgradePolicy a usuários individuais, não por locatário. Consulte [a Migração de](upgrade-to-teams-on-prem-tools.md#meeting-migration) Reunião para obter detalhes.)

No entanto, os destinatários não atualizados para o modo de Uso Paralelo poderão continuar recebendo chats e chamadas de um usuário do TeamsOnly nos clientes do Skype for Business ou do Teams.  Isso ocorre porque o cliente do Teams mantém threads de conversas separadas para comunicações de Teams para Teams e de Teams para Skype for Business, mesmo que seja para o mesmo usuário.  (Consulte [Conversas do Teams - Interop versus threads nativos](upgrade-to-teams-on-prem-coexistence.md#teams-conversations---interop-versus-native-threads).)  Por exemplo, suponha que o Usuário das Ilhas A use o Teams para enviar uma mensagem para o usuário B do TeamsOnly. Quando o usuário B responder a esse chat, a comunicação será ressarte no cliente do Teams do Usuário A. Agora, suponha que o Usuário A use o cliente Skype for Business para enviar uma mensagem ao usuário do TeamsOnly B. O usuário B receberá o chat no Teams, mas esta será uma conversa separada no cliente Do Usuário B do Teams em comparação com a outra conversa. Se o Usuário B responder a essa conversa com o Usuário A, ela será ressada no cliente Skype for Business do Usuário A. 

A tabela a seguir resume a experiência do Teams no modo de Uso Paralelo e no modo TeamsOnly:  

| Experiência do Teams | No modo de Uso Paralelo | No modo TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Chats e chamadas recebidos no:|  Teams ou Skype for Business | Teams |
| Chamadas PSTN recebidas em: | Skype for Business <br>(Não há suporte para o uso da funcionalidade PSTN no Teams no modo de Uso Paralelo.)    | Teams |   
 |Presença  | A presença no Skype for Business e no Teams é independente. Os usuários podem ver estados diferentes para o mesmo usuário de Uso Paralelo, dependendo do cliente usado. | A presença se baseia unicamente nas atividades do usuário no Teams. Todos os outros usuários, independentemente de qual cliente usam, veem essa presença. | 
 | Agendamento de Reunião   | Por padrão, os usuários podem agendar reuniões no Teams ou no Skype for Business. Eles verão ambos os suplementos no Outlook. |   Os usuários só agendam reuniões no Teams. Somente o suplemento do Teams está disponível no Outlook. | 

A tabela a seguir resume os prós e os contras de usar o método de recursos sobrepostos para migrar sua organização para o Teams.

| Prós     |       Contras |
| :------------------ | :---------------- |
| Permite a adoção rápida dentro de uma organização.| Potencial para confusão do usuário final porque existem dois clientes com funcionalidade semelhante, mas interfaces de usuário diferentes. Além disso, eles não têm controle sobre em qual cliente chegarão os chats/chamadas recebidos. |
| Permite que os usuários aprendam e se familiarizem com o Teams enquanto ainda têm acesso total ao Skype for Business. | Potencial para insatisfação do usuário final devido a mensagens perdidas se o usuário não estiver executando os dois clientes. Os usuários podem reclamação de que não estão recebendo mensagens.|
| Esforço administrativo mínimo para começar a usar o Teams. | Pode ser um desafio sair do modo "Sair das Ilhas" e ir para o modo TeamsOnly se nem todos na organização estão usando o Teams, especialmente se nem todos os usuários estão ativos no Teams. Por exemplo, depois que um subconjunto de usuários for atualizado para o modo TeamsOnly, esses usuários só enviarão no Teams. Para o restante da população no modo Ilhas, essas mensagens sempre serão enviadas para o Teams. Mas se parte dessa população não estiver executando o Teams, eles perceberão essas mensagens como perdidas. |
|  | Ao usar o Teams, os usuários que têm uma conta local no Skype for Business Server não têm suporte interop ou federação.  Isso pode gerar confusão se você tiver uma combinação de usuários de Ilhas, alguns que estão instalados no Skype for Business Online e outros no Skype for Business local.   |

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Método de recursos selecionados (usando os modos do Skype for Business)

Algumas organizações podem preferir fornecer aos usuários finais uma experiência mais simples e previsível à medida que suas transições da organização do Skype for Business para o Teams. Neste modelo, os administradores de IT usam um dos modos do Skype for Business no TeamsUpgradePolicy para designar explicitamente quais usuários permanecem no Skype for Business antes de migrar para o modo TeamsOnly. À medida que eles estão prontos para transferir os usuários selecionados para o modo TeamsOnly, o administrador atualiza o modo para esses usuários para o TeamsOnly. À medida que a implantação avança, cada vez mais usuários são transitivos do Skype for Business para o modo TeamsOnly.  Durante a transição:

- Os usuários que ainda estão no Skype for Business recebem todos os chats e chamadas recebidos no cliente do Skype for Business, independentemente da comunicação ter sido originada de outro cliente do Teams do usuário ou do Skype for Business. Além disso, para esses usuários do Skype for Business, as funcionalidades de chamada e chat no cliente do Teams são desabilitadas para ajudar a evitar confusão do usuário final e para garantir o roteamento adequado. 

- Os usuários no modo TeamsOnly recebem todos os chats de entrada e chamadas em seu cliente do Teams, independentemente de onde a comunicação se originou: Teams, Skype for Business ou qualquer tipo de usuário federado. 

Ao contrário do método Islands, no método de seleção de recursos, os usuários do Skype for Business e os usuários do TeamsOnly podem se comunicar uns com os outros. A comunicação entre um usuário do Skype for Business e um usuário do Teams é conhecida como interoperabilidade ou "interop”. A comunicação interop é possível individualmente para chats e chamadas entre um usuário no Skype for Business e outro usuário no Teams; no entanto, algumas funcionalidades avançadas podem não estar disponíveis. (Consulte [Interoperabilidade](upgrade-to-teams-on-prem-coexistence.md#interoperability).) Além disso, os usuários convidados sempre podem ingressar em uma reunião do Skype for Business ou do Teams, no entanto, eles devem usar um cliente que corresponda ao tipo de reunião. Para mais informações, confira [Reuniões](upgrade-to-teams-on-prem-coexistence.md#meetings).

Como os usuários em uma transição de recursos selecionados normalmente não estão no modo Ilhas, a presença de um usuário é consistente independentemente de qual cliente é usado pelo outro usuário. Se o usuário estiver em um dos modos do Skype for Business, todos os outros usuários verão a presença com base na atividade desse usuário no Skype for Business. Da mesma forma, se um usuário estiver no modo TeamsOnly, todos os outros usuários verão a presença com base na atividade desse usuário no Teams. Para obter detalhes, confira [Presença](upgrade-to-teams-on-prem-coexistence.md#presence).

Para uma organização que ainda não começou a usar o Teams, o administrador deve alterar o modo de locatário para o SfbWithTeamsCollab. (Para as organizações que já têm algum uso do Teams, o administrador deve "ajudar" os usuários que já estão ativos no Teams para garantir que essa alteração não se aplique a eles. Para obter detalhes, consulte Um método de seleção de recursos para uma organização que já está usando [o Teams no modo Ilhas.)](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Quando o modo muda de Islands para SfbWithTeamsCollab, um usuário que nunca usou o Teams não verá diferença em como eles usam o Skype for Business. No entanto, se esse usuário começasse a usar o Teams, ele estaria exposto apenas a funcionalidades como Arquivos, Teams e Canal. O agendamento de chats, chamadas e reuniões não estaria disponível no Teams, pois o administrador (por enquanto) designou o Skype for Business como o cliente desejado para essas funções.  

Observação: quando o Usuário A muda de Ilhas para um dos modos do Skype for Business, o cliente do Teams de qualquer outro usuário que se comunica com o Usuário A precisa saber que o modo do Usuário A mudou para que ele possa encaminhar a comunicação para o cliente apropriado para o Usuário A.  Para os usuários que já estabeleceram chats nativos do Teams para Teams com o Usuário A, pode levar até 36 horas para que os clientes do Teams desses outros usuários tenham em conta a mudança de modo das Ilhas para qualquer modo do Skype for Business.   Por outro lado, as alterações de um usuário existente para o modo TeamsOnly são descobertas por outros clientes dentro de 2 horas.

Quando os administradores estiverem prontos, eles poderão mudar o agendamento de chats, chamadas e reuniões de um determinado usuário para o Teams de uma só vez, atualizando o modo do usuário para TeamsOnly.  

Como alternativa, o administrador poderá primeiro mudar apenas o agendamento de reuniões para o Teams, deixando as funções de chats e chamadas no Skype for Business usando o modo SfBWithTeamsCollabAndMeetings. Esse modo permite que as organizações transiem para o Teams para reuniões, se os usuários ainda não estão prontos para migrar para o modo TeamsOnly (geralmente porque pode ser necessário mais tempo para migrar a funcionalidade PSTN existente). Esse cenário de transição é conhecido como [Primeiro Reuniões](meetings-first.md).

A tabela a seguir resume os prós e os contras do uso dos modos do Skype for Business como uma etapa de transição para o modo TeamsOnly.


| Prós     |       Contras |
| :------------------ | :---------------- |
| Roteamento previsível para o usuário final.  Todas as chamadas e chats chegam ao Skype for Business ou Teams (mas não a ambos), com base na seleção do administrador.  | As conversas de interoperabilidade não têm suporte para o compartilhamento de tela, compartilhamento de arquivos e rich text.  Isso pode ser trabalhado com reuniões sob demanda, mas isso não é tão simples.  |
| Elimine a confusão do usuário final porque uma determinada funcionalidade só está disponível em um cliente.  | Os usuários não podem experimentar os dois clientes lado a lado para o mesmo conjunto de funcionalidades. Isso pode ser especialmente um fator se os usuários perceberem a mudança do Skype for Business para o Teams como uma mudança de paradigma principal. |
| Permite a introdução incremental do Teams.  |  | |
| O administrador tem controle total da transição do Skype for Business para o Teams. |  | | 
| Permite que uma organização use o Teams para reuniões, mesmo que ainda não esteja pronta para mudar inteiramente para o modo TeamsOnly. |  | |
| A presença de um determinado usuário é a mesma, conforme visualizada por outros, independentemente do cliente usado.  |  | |

## <a name="summary-of-upgrade-methods"></a>Resumo dos métodos de atualização

A tabela a seguir resume os métodos de atualização:

| Recursos sobrepostos (usando o modo de Uso Paralelo)     |      Selecionar recursos (usando os modos do Skype for Business) |
| :------------------ | :---------------- |
| Antes de serem atualizados para o TeamsOnly, os usuários devem executar ambos os clientes simultaneamente, pois os chats e chamadas recebidos podem chegar a qualquer cliente.   | Chats e chamadas só se chegarão a um cliente, com base no modo do destinatário. Usuários não atualizados podem executar ambos os clientes, mas não há sobreposição funcional (chamadas e chats não estão disponíveis no Teams).  Os administradores também podem controlar se os usuários agendam reuniões no Teams ou no Skype for Business.   |
| Os usuários podem usar o Skype for Business e o Teams lado a lado para ter a mesma funcionalidade.   | Permite que os administradores apresentem novas funcionalidades do Teams para usuários finais (Teams e Canais), sem fornecer a mesma funcionalidade que também existe no Skype for Business.   |
|A interoperabilidade entre o Skype for Business e o Teams não existe enquanto os dois usuários estão no modo de Uso Paralelo. Depois que alguns usuários são atualizados para o TeamsOnly, a conversa interop pode ocorrer entre esses usuários e outros usuários que ainda estão no modo Ilhas. No entanto, o usuário das Ilhas poderia optar por usar o Teams e evitar a conversa interop. | A interoperabilidade é necessária para a comunicação entre usuários do Skype for Business e do Teams.   |


## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

