---
title: Atualize para o Teams a partir de uma implantação local do Skype for Business-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Atualização do Skype for Business para o Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80a7071cf6adbfa423e4c0fa12ac21a5bc777268
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940615"
---
# <a name="upgrade-methods-mdash-for-it-administrators"></a>Métodos &mdash; de atualização para administradores de ti

Este artigo descreve os métodos de atualização para migrar para o Microsoft Teams. Este artigo é o segundo de vários que descreve os conceitos de atualização e a implementação para administradores de ti.  

- [Visão geral](upgrade-to-teams-on-prem-overview.md)
- **Métodos de atualização** (este artigo)
- [Ferramentas para gerenciar a atualização](upgrade-to-teams-on-prem-tools.md)
- [Considerações adicionais sobre organizações com o Skype for Business no local](upgrade-to-teams-on-prem-considerations.md)
- [Implementando a atualização](upgrade-to-teams-on-prem-implement.md)
- [Considerações sobre PSTN (rede telefônica pública comutada)](upgrade-to-teams-on-prem-pstn-considerations.md)

Além disso, os seguintes artigos descrevem conceitos importantes de atualização e comportamentos de coexistência:

- [Coexistência de Teams e Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistência-referência](migration-interop-guidance-for-teams-with-skype.md)
- [Experiência e conformidade do cliente do Teams a modos de coexistência](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="upgrade-methods"></a>Métodos de atualização

Há dois métodos para atualizar uma organização existente com o Skype for Business (seja online ou local) para o Microsoft Teams: método de recursos sobrepostos e o método selecionar funcionalidades.  Este artigo ajuda você a escolher o método certo para sua organização, descrevendo os dois métodos e apresentando os prós e os contras de cada um deles. 

- [Método de recursos sobrepostos (usando o modo de Uso Paralelo)](#overlapping-capabilities-method-using-islands-mode)

   Os usuários de uma organização existente do Skype for Business são apresentados às equipes para que possam usar os dois clientes durante uma fase de transição. Durante esse período, quase todas as funcionalidades do Teams estarão disponíveis para eles. O modo para essa configuração é referenciado como Uso Paralelo, e esse é o modo padrão para qualquer organização existente com o Skype for Business. Depois que a organização estiver pronta, o administrador moverá os usuários para o modo TeamsOnly.

- [Selecionar método de funcionalidades (usando um ou mais dos modos do Skype for Business)](#select-capabilities-method-using-skype-for-business-modes)

   O administrador gerencia a transição (do Skype for Business para o Teams) de recursos de chat, chamadas e agendamento de reunião para os usuários de sua organização.  Cada uma dessas funções está disponível no Skype for Business ou no Teams, mas não em ambas. Os administradores usam o TeamsUpgradePolicy para controlar quando mudar essa funcionalidade para o Teams dos seus usuários. Os usuários que ainda não estão no modo TeamsOnly continuarão a usar o Skype for Business para chats e chamadas, e os dois conjuntos de usuários poderão se comunicar por meio da funcionalidade de interoperabilidade. Os administradores gerenciam a transição migrando progressivamente mais usuários para o modo TeamsOnly.  

Depois de compreender e escolher o método de atualização, você pode saber mais sobre as [ferramentas para gerenciar a atualização da sua organização para o Microsoft Teams](upgrade-to-teams-on-prem-tools.md).

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Método de recursos sobrepostos (usando o modo de Uso Paralelo)

Com o método de recursos sobrepostos, os usuários podem usar os clientes do Teams e do Skype for Business para chats, chamadas VoIP e reuniões. Esse estado é conhecido como o modo "ilhas" porque o tráfego de comunicação do Skype for Business e do teams permanece separado (mesmo para o mesmo usuário) e os dois clientes diferentes nunca se comunicam uns com os outros (para os usuários da mesma organização). Por exemplo, suponha que o usuário do destinatário A esteja no modo de ilhas:

- A comunicação iniciada pelo cliente do Skype for Business de outro usuário sempre chegará ao cliente do Skype for Business do Usuário A.

- A comunicação iniciada do cliente das equipes de outro usuário sempre chegará ao cliente do teams do usuário, *se o outro usuário estiver na mesma organização*. 

- A comunicação iniciada do cliente das equipes de outro usuário sempre chegará ao cliente Skype for Business do usuário A, *se o outro usuário estiver em uma organização federada*.

O modo de ilhas é o modo padrão de TeamsUpgradePolicy para qualquer organização existente que ainda não tenha atualizado para TeamsOnly. Quando você atribui uma licença do Microsoft 365 ou do Office 365, as duas equipes e licenças do Skype for Business online são atribuídas por padrão. (Isso é verdadeiro mesmo se o usuário estiver em um local no Skype for Business Server. Não importa se o usuário está hospedado no local ou online, deixe a licença do Skype for Business online habilitada, pois ela é necessária no momento para a funcionalidade completa do teams. Na verdade, se você não tiver feito nenhuma etapa para alterar a configuração padrão, talvez já tenha um uso significativo do teams em sua organização.  Esse é um dos benefícios da abordagem de recursos sobrepostos. Ele permite uma adoção rápida e orientada pelo usuário final em uma organização.

Para esse método funcionar de forma eficaz, é preciso que todos os usuários executem os dois clientes simultaneamente. Os chats e chamadas recebidos de dentro da organização para um usuário no modo de Uso Paralelo podem chegar ao cliente do Skype for Business ou do Teams, mas isso não está sob o controle do destinatário. Se o remetente e o destinatário estiverem na mesma organização, dependerá do cliente que o remetente usa para iniciar a comunicação. Se o remetente e o destinatário estiverem em organizações diferentes, chamadas e chats recebidos para um usuário no modo de Uso Paralelo sempre chegam ao cliente do Skype for Business.  

Por exemplo, se um destinatário do modo de ilhas estiver executando o Skype for Business, mas não as equipes e alguém na mesma organização as mensagens do Teams, o destinatário do modo de ilhas não verá a mensagem (mas eles eventualmente receberão um email informando que perderam uma mensagem no Teams). Da mesma forma, se um usuário estiver executando o Teams, mas não o Skype for Business, e alguém enviar mensagens a esse usuário pelo Skype for Business, o usuário não verá esse chat.  Eles receberão um e-mail dizendo que houve uma mensagem perdida. O comportamento em cada um desses casos é semelhante para chamadas. Se os usuários não executarem ambos clientes, isso poderá terminar facilmente em frustração.

Quando o usuário A está no modo de ilhas, A presença do usuário A ser vista por outros usuários do Teams e no Skype for Business é independente:

- Ao usar o Teams, os outros usuários verão a presença com base na atividade do Usuário A no Teams. 
- Ao usar o Skype for Business, os outros usuários verão a presença com base na atividade do Usuário A no Skype for Business. 

Isso significa que outros usuários podem ver estados diferentes de presença para o Usuário A, dependendo do cliente usado. Para saber mais, confira [Presença](upgrade-to-teams-on-prem-coexistence.md#presence).

Quando estiver pronto para atualizar os usuários para o modo TeamsOnly, você pode atualizar os usuários individualmente ou pode atualizar o locatário inteiro de uma só vez usando a política de todo o locatário. Assim que um usuário é atualizado para o modo TeamsOnly, ele recebe todos os chats e chamadas recebidos no Teams. (Observe que a migração de reuniões do Skype for Business para reuniões de equipe é disparada somente ao aplicar TeamsUpgradePolicy a usuários individuais, e não a cada locatário. Consulte [migração de reunião](upgrade-to-teams-on-prem-tools.md#meeting-migration) para obter detalhes.)

No entanto, os destinatários não atualizados para o modo de Uso Paralelo poderão continuar recebendo chats e chamadas de um usuário do TeamsOnly nos clientes do Skype for Business ou do Teams.  Isso ocorre porque o cliente do Teams mantém threads de conversas separadas para comunicações de Teams para Teams e de Teams para Skype for Business, mesmo que seja para o mesmo usuário.  (Consulte [conversas de equipes – interoperabilidade versus threads nativos](upgrade-to-teams-on-prem-coexistence.md#teams-conversations---interop-versus-native-threads).)  Por exemplo, assuma ilhas o usuário A usa equipes para a mensagem TeamsOnly o usuário B. Quando o usuário B responder a esse chat, a comunicação será esterrada no cliente do teams do usuário A. Agora, suponha que o usuário A Use o cliente Skype for Business para enviar mensagens de TeamsOnly para o usuário B. o usuário B receberá o chat no Microsoft Teams, mas isso será uma conversa separada no cliente do teams do usuário B em comparação com a outra conversa. Se o usuário B responder a essa conversa com o usuário A, ele chegará ao cliente Skype for Business do usuário A. 

A tabela a seguir resume a experiência do Teams no modo de Uso Paralelo e no modo TeamsOnly:  

| Experiência do Teams | No modo de Uso Paralelo | No modo TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Chats e chamadas recebidos no:|  Teams ou Skype for Business | Teams |
| Chamadas PSTN recebidas em: | Skype for Business <br>(Não há suporte para o uso da funcionalidade PSTN no Teams no modo de Uso Paralelo.)    | Teams |   
 |Presença  | A presença no Skype for Business e no Teams é independente. Os usuários podem ver estados diferentes para o mesmo usuário de Uso Paralelo, dependendo do cliente usado. | A presença se baseia unicamente nas atividades do usuário no Teams. Todos os outros usuários, independentemente de qual cliente usam, veem essa presença. | 
 | Agendamento de Reunião   | Por padrão, os usuários podem agendar reuniões em qualquer um dos grupos ou no Skype for Business. Eles verão ambos os suplementos no Outlook. |   Os usuários só agendam reuniões no Teams. Somente o suplemento do Teams está disponível no Outlook. | 

A tabela a seguir resume os prós e os contras de usar o método de recursos sobrepostos para migrar sua organização para o Teams.

| Prós     |       Contras |
| :------------------ | :---------------- |
| Permite a adoção rápida dentro de uma organização.| Potencial para confundir o usuário final, porque há dois clientes com funcionalidade semelhante, mas interfaces de usuário diferentes. Além disso, eles não têm controle sobre em qual cliente chegarão os chats/chamadas recebidos. |
| Permite que os usuários aprendam e se familiarizem com o Teams enquanto ainda têm acesso total ao Skype for Business. | Potencial de insatisfação do usuário final devido a mensagens perdidas, caso o usuário não esteja executando ambos os clientes. Os usuários podem reclamar que não estão recebendo mensagens.|
| Esforço administrativo mínimo para começar a usar o Teams. | Pode ser um desafio para "sair do modo de ilhas" e mudar para o modo TeamsOnly, se nem todos na organização estiverem usando o Microsoft Teams, especialmente se nem todos os usuários estiverem ativos no Teams. Por exemplo, quando um subconjunto de usuários for atualizado para o modo TeamsOnly, esses usuários só serão enviados para o Microsoft Teams. Para o restante da população no modo ilhas, essas mensagens sempre serão exibidas no Microsoft Teams. Mas se parte dessa população não estiver em execução no Microsoft Teams, ele perceberá essas mensagens como perdida. |
|  | Ao usar o Microsoft Teams, os usuários que têm uma conta local no Skype for Business Server não têm suporte à interoperabilidade ou Federação.  Isso pode potencialmente criar confusão se você tiver uma combinação de usuários de ilhas, alguns que são hospedados no Skype for Business Online e alguns no Skype for Business local.   |

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Método de recursos selecionados (usando os modos do Skype for Business)

Algumas organizações podem optar por oferecer aos usuários finais uma experiência mais simples e mais previsível à medida que sua organização faz a transição do Skype for Business para o Teams. Nesse modelo, os administradores de ti usam um dos modos do Skype for Business no TeamsUpgradePolicy para designar explicitamente quais usuários permanecem no Skype for Business antes de migrar para o modo TeamsOnly. Como estão prontos para alternar os usuários selecionados para o modo TeamsOnly, o administrador atualiza o modo para os usuários TeamsOnly. À medida que a implantação progride, mais e mais usuários são movidos do Skype for Business para o modo TeamsOnly.  Durante a transição:

- Os usuários que ainda estão no Skype for Business recebem todos os chats e chamadas recebidos no cliente do Skype for Business, independentemente da comunicação ter sido originada de outro cliente do Teams do usuário ou do Skype for Business. Além disso, para esses usuários do Skype for Business, a funcionalidade de chamadas e de chat no cliente do teams é desativada para evitar a confusão do usuário final e garantir o roteamento adequado. 

- Os usuários no modo TeamsOnly recebem todos os chats e chamadas de entrada no cliente das equipes, independentemente de onde a comunicação se originou de: Teams, Skype for Business ou qualquer tipo de usuário federado. 

Ao contrário do método ilhas, no método selecionar funcionalidades, os usuários do Skype for Business e os usuários do TeamsOnly podem se comunicar uns com os outros. A comunicação entre um usuário do Skype for Business e um usuário do Teams é conhecida como interoperabilidade ou "interop”. A comunicação de interoperabilidade é possível em uma base de um-para-um para chats e chamadas entre um usuário no Skype for Business e outro usuário no Teams; no entanto, alguns recursos avançados podem não estar disponíveis. (Consulte [interoperabilidade](upgrade-to-teams-on-prem-coexistence.md#interoperability).) Além disso, os usuários convidados sempre podem participar de uma reunião do Skype for Business ou do Teams, mas devem usar um cliente que corresponda ao tipo de reunião. Para mais informações, confira [Reuniões](upgrade-to-teams-on-prem-coexistence.md#meetings).

Como os usuários em uma transição de recursos selecionados geralmente não estão no modo de ilhas, a presença de um usuário é consistente independentemente do cliente usado pelo outro usuário. Se o usuário estiver em um dos modos do Skype for Business, todos os outros usuários verão a presença com base na atividade desse usuário no Skype for Business. Da mesma forma, se um usuário estiver no modo TeamsOnly, todos os outros usuários verão a presença com base na atividade desse usuário no Teams. Para obter detalhes, confira [Presença](upgrade-to-teams-on-prem-coexistence.md#presence).

Para uma organização que ainda não começou a usar o Teams, o administrador deve alterar o modo de todos os locatários de ilhas para SfbWithTeamsCollab. (Para organizações que já têm alguns usos de equipes, o administrador deve "avô" os usuários já ativos no Teams para garantir que essa alteração não se aplique a ele. Para obter detalhes, consulte [um método selecionar recursos para uma organização que já está usando o Teams no modo ilhas](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode).)

Quando o modo muda de ilhas para SfbWithTeamsCollab, um usuário que nunca usou o Teams não verá nenhuma diferença em como usar o Skype for Business. No entanto, se esse usuário começasse a usar o Teams, ele estaria exposto apenas a funcionalidades como Arquivos, Teams e Canal. O agendamento de chats, chamadas e reuniões não estaria disponível no Teams, pois o administrador (por enquanto) designou o Skype for Business como o cliente desejado para essas funções.  

Observação: quando o usuário altera de ilhas para um dos modos do Skype for Business, o cliente de equipes de qualquer outro usuário que se comunica com o usuário A precisa saber que o modo de um usuário foi alterado para que ele possa encaminhar a comunicação ao cliente apropriado para o usuário A.  Para qualquer usuário que já tenha estabelecido chats nativos entre equipes e chats com o usuário A, pode levar até 36 horas para que os clientes de equipes de outros usuários estejam cientes da mudança de modo das ilhas para qualquer modo do Skype for Business.   Por outro lado, as alterações de um usuário existente no modo TeamsOnly são descobertas por outros clientes dentro de 2 horas.

Quando os administradores estiverem prontos, eles poderão mudar o agendamento de chats, chamadas e reuniões de um determinado usuário para o Teams de uma só vez, atualizando o modo do usuário para TeamsOnly.  

Como alternativa, o administrador poderá primeiro mudar apenas o agendamento de reuniões para o Teams, deixando as funções de chats e chamadas no Skype for Business usando o modo SfBWithTeamsCollabAndMeetings. Esse modo permite que as organizações façam a transição para o Microsoft Teams para reuniões--se os usuários ainda não estiverem prontos para serem movidos para o modo TeamsOnly (geralmente porque mais tempo pode ser necessário para migrar a funcionalidade PSTN existente). Esse cenário de transição é conhecido como [Primeiro Reuniões](meetings-first.md).

A tabela a seguir resume os prós e os contras do uso dos modos do Skype for Business como uma etapa de transição para o modo TeamsOnly.


| Prós     |       Contras |
| :------------------ | :---------------- |
| Roteamento previsível para o usuário final.  Todas as chamadas e chats chegam ao Skype for Business ou Teams (mas não a ambos), com base na seleção do administrador.  | As conversas de interoperabilidade não têm suporte para o compartilhamento de tela, compartilhamento de arquivos e rich text.  Isso pode ser trabalhado com reuniões sob demanda, mas isso não é tão fácil.  |
| Eliminar a confusão do usuário final porque uma determinada funcionalidade está disponível apenas em um cliente.  | Os usuários não podem experimentar os dois clientes lado a lado para o mesmo conjunto de funcionalidades. Isso pode ser especialmente um fator se os usuários percebem a mudança do Skype for Business para o Teams como uma mudança de paradigma importante. |
| Permite a introdução incremental do teams.  |  | |
| O administrador tem controle total sobre a transição do Skype for Business para o Teams. |  | | 
| Permite que uma organização use o Teams para reuniões, mesmo que ainda não esteja pronta para mudar inteiramente para o modo TeamsOnly. |  | |
| A presença de um determinado usuário é a mesma, conforme visualizada por outros, independentemente do cliente usado.  |  | |

## <a name="summary-of-upgrade-methods"></a>Resumo dos métodos de atualização

A tabela a seguir resume os métodos de atualização:

| Recursos sobrepostos (usando o modo de Uso Paralelo)     |      Selecionar recursos (usando os modos Skype for Business) |
| :------------------ | :---------------- |
| Antes de serem atualizados para o TeamsOnly, os usuários devem executar ambos os clientes simultaneamente, pois os chats e chamadas recebidos podem chegar a qualquer cliente.   | Chats e chamadas só se chegarão a um cliente, com base no modo do destinatário. Usuários não atualizados podem executar ambos os clientes, mas não há sobreposição funcional (chamadas e chats não estão disponíveis no Teams).  Os administradores também podem controlar se os usuários agendam reuniões no Microsoft Teams ou no Skype for Business.   |
| Os usuários podem usar o Skype for Business e o Teams lado a lado para a mesma funcionalidade.   | Permite que os administradores introduzam novas funcionalidades líquidas do teams para usuários finais (equipes e canais), sem fornecer a mesma funcionalidade que também existe no Skype for Business.   |
|A interoperabilidade entre o Skype for Business e o Teams não existe enquanto os dois usuários estão no modo de Uso Paralelo. Depois que alguns usuários forem atualizados para o TeamsOnly, a conversa de interoperabilidade poderá ocorrer entre esses usuários e outros usuários no modo de ilhas. No entanto, o usuário ilhas pode optar por usar o Microsoft Teams e evitar a conversa Interop. | A interoperabilidade é necessária para a comunicação entre usuários do Skype for Business e do Teams.   |


## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

