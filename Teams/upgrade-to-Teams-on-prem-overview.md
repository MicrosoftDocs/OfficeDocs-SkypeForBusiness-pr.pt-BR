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
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cef0a06ceb37cdfff3e9e4952f10397e7ee9b698
ms.sourcegitcommit: 876b576db1fee38c09ab3a0092116212e498eda7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/25/2019
ms.locfileid: "37733081"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Atualize o Skype for Business para o &mdash; Teams para administradores de ti

## <a name="overview"></a>Visão geral

Ao fazer a atualização do Skype for Business para o Teams, algumas organizações exigem uma distribuição progressiva planejada e gerenciada pelos departamentos de ti. Este artigo destina-se principalmente a administradores de ti em organizações grandes locais, mas também pode se aplicar a algumas organizações do Skype for Business online.  Antes de ler este artigo, lembre-se de ler introdução à [atualização do seu Teams](upgrade-start-here.md) e [sobre a estrutura de atualização](upgrade-framework.md).

>[!NOTE]
>Este artigo usa os termos Skype for Business Online, Skype for Business local e Skype for Business.  O último termo refere-se às versões online e local.

Um usuário migrado para o Microsoft Teams não usa mais um cliente Skype for Business, exceto para ingressar em uma reunião hospedada no Skype for Business.  Todos os chats recebidos e chamadas entram no cliente das equipes do usuário, independentemente de o remetente usar o Microsoft Teams ou o Skype for Business. Qualquer reunião nova organizada pelo usuário migrado será agendada como reuniões do teams. Se o usuário tentar usar o cliente Skype for Business, a iniciação de chats e chamadas será bloqueada<sup>1</sup>.  No entanto, o usuário pode (e deve) ainda usar o cliente Skype for Business para ingressar em reuniões para as quais foram convidados.
 
Os administradores gerenciam a transição para o Microsoft Teams usando o conceito de [Mode](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes), que é uma propriedade de [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). Um usuário que foi migrado para o Teams, conforme descrito acima, está no modo "TeamsOnly".  Para uma organização que está migrando para o Microsoft Teams, o objetivo final é mover todos os usuários para o modo TeamsOnly.

Há dois métodos para migrar uma organização existente com o Skype for Business (seja online ou local) para o Microsoft Teams:

- **Método** lado a lado (usando o modo de ilhas): os usuários em uma organização existente do Skype for Business são introduzidos para o Teams, para que eles possam usar os dois clientes lado a lado durante uma fase de transição. Durante esse período, a maioria dos recursos do Microsoft Teams está disponível para eles. O modo dessa configuração é chamado de ilhas, e esse é o modo padrão de qualquer organização existente com o Skype for Business. Depois que a organização estiver pronta, o administrador move os usuários para o modo TeamsOnly.

- **Um método gerenciado** (usando um ou mais dos modos do Skype for Business): o administrador gerencia a transição (do Skype for Business para o Teams) de recursos de chat, chamadas e agendamento de reunião para os usuários de sua organização.  Cada uma dessas funções está disponível no Skype for Business ou no Teams, mas não ambos. Os administradores usam o TeamsUpgradePolicy para controlar quando mudar essa funcionalidade para o Microsoft Teams para seus usuários. Os usuários que ainda não estão no modo TeamsOnly continuam a usar o Skype for Business para chat e chamadas, e os dois conjuntos de usuários podem se comunicar por meio da funcionalidade de interoperabilidade. Os administradores gerenciam a transição migrando progressivamente mais usuários para o modo TeamsOnly.  

Este artigo ajuda você a escolher o método certo para sua organização, descrevendo os dois métodos e apresentando os prós e os contras de cada um deles. 

**Observações:**
<sup>1</sup>os clientes mais antigos do Skype for Business fornecidos antes do 2017 não obedecem ao TeamsUpgradePolicy. Verifique se você está usando o cliente Skype for Business mais recente.


## <a name="side-by-side-method-using-islands-mode"></a>Método lado a lado (usando o modo de ilhas)

Com o método lado a lado, os usuários podem usar o Microsoft Teams e clientes do Skype for Business para chats, chamadas de VoIP e reuniões. Esse estado é conhecido como o modo "ilhas" porque o tráfego de comunicação do Skype for Business e do teams permanece separado (mesmo para o mesmo usuário) e os dois clientes diferentes nunca se comunicam uns com os outros (para os usuários da mesma organização). Por exemplo, suponha que o usuário do destinatário A esteja no modo de ilhas:

- A comunicação iniciada do cliente Skype for Business de outro usuário sempre chegará ao cliente Skype for Business do usuário A.
- A comunicação iniciada do cliente das equipes de outro usuário sempre chegará ao cliente do teams do usuário, *se o outro usuário estiver na mesma organização*. 
- A comunicação iniciada do cliente das equipes de outro usuário sempre chegará ao cliente Skype for Business do usuário A, *se o outro usuário estiver em uma organização federada*.

O modo de ilhas é o modo padrão de TeamsUpgradePolicy para qualquer organização existente que ainda não esteja TeamsOnly. Quando você atribui uma licença do Office 365, as duas equipes e licenças do Skype for Business online são atribuídas por padrão. <sup>2</sup> na verdade, se você não tiver feito nenhuma etapa para alterar a configuração padrão, talvez já tenha um uso significativo do teams em sua organização.  Esse é um dos benefícios de uma abordagem lado a lado. Ele permite uma adoção rápida e orientada pelo usuário final em uma organização.

Para esse método funcionar de forma eficaz, é preciso que todos os usuários executem os dois clientes simultaneamente. Chats recebidos e chamadas de dentro da organização para um usuário no modo de ilhas podem ser divididos no cliente do Skype for Business ou do Teams, e isso não está sob o controle do destinatário. Depende do cliente que o remetente usa para iniciar a comunicação. Se o remetente e o destinatário estiverem em organizações diferentes, as chamadas recebidas e chats para um usuário no modo ilhas sempre chegam no cliente Skype for Business.  

Por exemplo, se um destinatário do modo de ilhas estiver executando o Skype for Business, mas não as equipes e alguém, e alguém do Teams, o destinatário do modo de ilhas não verá a mensagem (mas eventualmente receberá um email informando que perdeu uma mensagem no Teams). Da mesma forma, se um usuário estiver executando o Microsoft Teams, mas não o Skype for Business, e alguém receber o usuário do Skype for Business, o usuário não verá esse chat.  Eles receberão um e-mail dizendo que houve uma mensagem perdida. O comportamento em cada um desses casos é semelhante para fazer chamadas. Se os usuários não executarem ambos os clientes, poderão levar a frustração facilmente.

Quando o usuário A está no modo de ilhas, A presença do usuário A ser vista por outros usuários do Teams e no Skype for Business é independente:

- Outros usuários, ao usar o Teams, verão a presença com base na atividade do usuário A no Teams. 
- Para outros usuários, ao usar o Skype for Business, você verá a presença com base na atividade do usuário A no Skype for Business. 

Isso significa que outros usuários podem ver Estados de presença diferentes para o usuário A, dependendo de qual cliente ele usa. Para obter mais detalhes, consulte [presença](#presence).

Quando estiver pronto para atualizar os usuários para o modo TeamsOnly, você pode atualizar os usuários individualmente ou pode atualizar o locatário inteiro de uma só vez usando a política<sup>3</sup>de todo o locatário. Depois que um usuário é atualizado para o modo TeamsOnly, ele recebe todos os chats e chamadas recebidos no Teams. 

No entanto, os destinatários sem atualização no modo de ilhas podem continuar a receber chats e chamadas de um usuário do TeamsOnly em seus clientes do Skype for Business ou do teams.  Isso ocorre porque o cliente do teams mantém threads de conversa separados para comunicação entre equipes e equipes para Skype para empresas, mesmo para o mesmo usuário.  (Consulte [conversas de equipes – interoperabilidade versus threads nativos](#teams-conversations---interop-versus-native-threads).)  Por exemplo, assuma ilhas o usuário A usa equipes para a mensagem TeamsOnly o usuário B. Quando o usuário B responder a esse chat, a comunicação será esterrada no cliente do teams do usuário A. Agora, suponha que o usuário A Use o cliente Skype for Business para enviar mensagens de TeamsOnly para o usuário B. o usuário B receberá o chat no Microsoft Teams, mas isso será uma conversa separada no cliente do teams do usuário B em comparação com a outra conversa. Se o usuário B responder a essa conversa com o usuário A, ele chegará ao cliente Skype for Business do usuário A. 

A tabela a seguir resume a experiência do teams para o modo de ilhas e o modo TeamsOnly:  

| Experiência do teams | No modo de ilhas | No modo TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Chats recebidos e chamadas recebidas em:|  Teams ou Skype for Business | Teams |
| Chamadas PSTN recebidas em: | Skype for Business <br>(Não há suporte para o uso da funcionalidade PSTN em Teams no modo de ilhas.)    | Teams |   
 |Presença  | A presença no Skype for Business e no Teams é independente. Os usuários podem ver Estados diferentes para o mesmo usuário ilhas, dependendo de qual cliente ele usa. | A presença baseia-se apenas na atividade do usuário no Teams. Todos os outros usuários, independentemente de qual cliente usa, veja essa presença. | 
 | Agendamento de reunião   | Os usuários podem agendar reuniões em qualquer um dos grupos ou no Skype for Business. Eles verão ambos os suplementos no Outlook. |   Os usuários agendam somente reuniões no Teams. Somente o suplemento Teams está disponível no Outlook. | 

A tabela a seguir resume os prós e os contras de usar o método lado a lado para migrar sua organização para o Teams.

| Profissionais ti     |       Desvantagens |
| :------------------ | :---------------- |
| Permite a adoção rápida dentro de uma organização.| Potencial para confusão pelo usuário final porque há dois clientes com funcionalidade semelhante, mas interfaces do usuário diferentes. Além disso, eles não têm controle sobre qual cliente os chats/chamadas de entrada chegam. |
| Permite que os usuários aprendam e se familiarizem com o Microsoft Teams e ainda tenham acesso completo ao Skype for Business. | Potencial para insatisfação do usuário final devido a mensagens perdidas se o usuário não estiver executando ambos os clientes. Os usuários podem reclamar que não estão recebendo mensagens.|
| Esforço de administração mínima para começar a usar o Microsoft Teams. | Pode ser um desafio para "sair do modo de ilhas" e mudar para o modo TeamsOnly, se nem todos na organização estiverem usando o Microsoft Teams, especialmente se nem todos os usuários estiverem ativos no Teams. Por exemplo, quando um subconjunto de usuários for atualizado para o modo TeamsOnly, esses usuários só serão enviados para o Microsoft Teams. Para o restante da população no modo ilhas, essas mensagens sempre serão exibidas no Microsoft Teams. Mas se parte dessa população não estiver em execução no Microsoft Teams, ele perceberá essas mensagens como perdida. |
|  | Ao usar o Microsoft Teams, os usuários que têm uma conta local no Skype for Business Server não têm suporte à interoperabilidade ou Federação.  Isso pode potencialmente criar confusão se você tiver uma combinação de usuários de ilhas, alguns que são hospedados no Skype for Business Online e alguns no Skype for Business local.   |

**Informa**

<sup>2</sup> Isso é verdadeiro mesmo que o usuário seja hospedado no Skype for Business Server. Não importa se o usuário está hospedado no local ou online, deixe a licença do Skype for Business online habilitada, pois ela é necessária no momento para a funcionalidade completa do teams.

<sup>3</sup> Observe que a migração de reuniões do Skype for Business para reuniões de equipe é disparada somente ao aplicar TeamsUpgradePolicy a usuários individuais, e não a cada locatário. Consulte [migração de reunião](#meeting-migration) para obter detalhes. 



## <a name="managed-transition-method-using-skype-for-business-modes"></a>Método de transição gerenciado (usando os modos Skype for Business)

Algumas organizações podem optar por oferecer aos usuários finais uma experiência mais simples e mais previsível à medida que sua organização faz a transição do Skype for Business para o Teams. Nesse modelo, os administradores de ti usam um dos modos do Skype for Business no TeamsUpgradePolicy para designar explicitamente quais usuários permanecem no Skype for Business antes de migrar para o modo TeamsOnly. Como estão prontos para alternar os usuários selecionados para o modo TeamsOnly, o administrador atualiza o modo para os usuários TeamsOnly.  À medida que a implantação progride, mais e mais usuários são movidos do Skype for Business para o modo TeamsOnly.  Durante esta transição:

- Os usuários que ainda estão no Skype for Business recebem todos os chats e chamadas recebidos no cliente Skype for Business, independentemente de se a comunicação se originou das equipes do outro usuário ou do cliente Skype for Business. Além disso, para esses usuários do Skype for Business, a funcionalidade de chamadas e de chat no cliente do teams é desativada para evitar a confusão do usuário final e garantir o roteamento adequado. 

- Os usuários no modo TeamsOnly recebem todos os chats e chamadas de entrada no cliente das equipes, independentemente de onde a comunicação se originou de: Teams, Skype for Business ou qualquer tipo de usuário federado. 

Ao contrário do método ilhas, no método de transição gerenciado, os usuários do Skype for Business e os usuários do TeamsOnly podem se comunicar uns com os outros. A comunicação entre um usuário do usuário do Skype for Business e do teams é conhecida como interoperabilidade ou "interoperabilidade". (Consulte [interoperabilidade](#interoperability).) A comunicação de interoperabilidade é possível em uma base de um-para-um para chats e chamadas entre um usuário no Skype for Business e outro usuário no Teams. Além disso, os usuários convidados sempre podem participar de uma reunião do Skype for Business ou do Teams, mas devem usar um cliente que corresponda ao tipo de reunião. Para obter mais informações, consulte [reuniões](#meetings).

Como os usuários em uma transição gerenciada geralmente não estão no modo de ilhas, a presença de um usuário é consistente independentemente do cliente usado pelo outro usuário. Se o usuário estiver em um dos modos do Skype for Business, todos os outros usuários verão a presença com base na atividade do usuário no Skype for Business. Da mesma forma, se um usuário estiver no modo TeamsOnly, todos os outros usuários verão presença com base na atividade do usuário no Microsoft Teams. Para obter detalhes, consulte [presença](#presence).

Para uma organização que ainda não começou a usar o Teams, o administrador deve alterar o modo de todos os locatários de ilhas para SfbWithTeamsCollab. (Para organizações que já têm alguns usos de equipes, o administrador deve "avô" os usuários já ativos no Teams para garantir que essa alteração não se aplique a ele. Para obter detalhes, consulte [uma atualização gerenciada para uma organização que já está usando equipes no modo ilhas](#a-managed-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode).)

Quando o modo muda de ilhas para SfbWithTeamsCollab, um usuário que nunca usou o Teams não verá nenhuma diferença em como usar o Skype for Business. No entanto, caso o usuário comece a usar o Microsoft Teams, eles só serão expostos a funcionalidades como o Teams & Channel e os arquivos. O chat, as chamadas e o agendamento de reuniões não estarão disponíveis no Teams, pois o administrador já tinha o Skype for Business designado (por enquanto), como o cliente desejado para essas funções.  

Observação: quando o usuário altera de ilhas para um dos modos do Skype for Business, o cliente de equipes de qualquer outro usuário que se comunica com o usuário A precisa saber que o modo de um usuário foi alterado para que ele possa encaminhar a comunicação ao cliente apropriado para o usuário A.  Para qualquer usuário que já tenha estabelecido chats nativos entre equipes e chats com o usuário A, pode levar até 36 horas para que os clientes de equipes de outros usuários estejam cientes da mudança de modo das ilhas para qualquer modo do Skype for Business.   Por outro lado, as alterações de um usuário existente no modo TeamsOnly são descobertas por outros clientes dentro de 2 horas.

Quando os administradores estiverem prontos, poderão deslocar o chat, as chamadas e o agendamento de reuniões para um determinado usuário ao Teams ao mesmo tempo atualizando o modo do usuário para TeamsOnly.  

Como alternativa, o administrador pode primeiro deslocar somente o agendamento da reunião para o Microsoft Teams, enquanto deixa as funções de chat e chamadas no Skype for Business usando o modo SfBWithTeamsCollabAndMeetings. Esse modo permite que as organizações façam a transição para o Microsoft Teams para reuniões--se os usuários ainda não estiverem prontos para serem movidos para o modo TeamsOnly (geralmente porque mais tempo pode ser necessário para migrar a funcionalidade PSTN existente). Esse cenário de transição é conhecido como [reuniões primeiro](meetings-first.md).


A tabela a seguir resume os prós e os contras do uso dos modos Skype for Business como uma etapa de transição em direção ao modo TeamsOnly.


| Profissionais ti     |       Desvantagens |
| :------------------ | :---------------- |
| Roteamento previsível para o usuário final.  Todas as chamadas e chats se esterram no Skype for Business ou nas equipes (mas não em ambos), com base na seleção de administradores.  | As conversas de interoperabilidade não têm suporte para Rich Text, compartilhamento de arquivos e compartilhamento de tela.  Isso pode ser trabalhado com reuniões sob demanda, mas isso não é tão fácil.  |
| Eliminar a confusão do usuário final porque uma determinada funcionalidade está disponível apenas em um cliente.  | Os usuários não podem experimentar os dois clientes lado a lado para o mesmo conjunto de funcionalidades. Isso pode ser especialmente um fator se os usuários percebem a mudança do Skype for Business para o Teams como uma mudança de paradigma importante. |
| Permite a introdução incremental do teams.  |  | |
| O administrador tem controle total sobre a transição do Skype for Business para o Teams. |  | | 
| Permite que uma organização Use equipes para reuniões, mesmo se ainda não estiver pronta para se mover completamente para o modo TeamsOnly. |  | |
| A presença de um determinado usuário visto por outras pessoas é a mesma, independentemente do cliente usado.  |  | |

## <a name="summary-of-upgrade-methods"></a>Resumo dos métodos de atualização

A tabela a seguir resume os métodos de atualização:

| Lado a lado (usando o modo de ilhas)     |      Gerenciado (usando os modos Skype for Business) |
| :------------------ | :---------------- |
| Antes de ser atualizada para o TeamsOnly, os usuários devem executar os dois clientes simultaneamente, já que chats recebidos e chamadas podem chegar em qualquer um dos clientes.   | Chats e chamadas só se esterram em um cliente, com base no modo do destinatário. Os usuários não atualizados podem executar ambos os clientes, mas não há sobreposição funcional (chamadas e chats não estão disponíveis no Teams).  Os administradores também podem controlar se os usuários agendam reuniões no Microsoft Teams ou no Skype for Business.   |
| Os usuários podem usar o Skype for Business e o Teams lado a lado para a mesma funcionalidade.   | Permite que os administradores introduzam novas funcionalidades líquidas do teams para usuários finais (equipes e canais), sem fornecer a mesma funcionalidade que também existe no Skype for Business.   |
|A interoperabilidade entre o Skype for Business e o Teams não existe enquanto ambos os usuários estiverem no modo de ilhas. Depois que alguns usuários forem atualizados para o TeamsOnly, a conversa de interoperabilidade poderá ocorrer entre esses usuários e outros usuários no modo de ilhas. No entanto, o usuário ilhas pode optar por usar o Microsoft Teams e evitar a conversa Interop. | A interoperabilidade é necessária para a comunicação entre os usuários do Skype for Business e do teams.   |

## <a name="tools-for-managing-the-upgrade"></a>Ferramentas para gerenciar a atualização

Para qualquer um dos métodos descritos acima, os administradores gerenciam a transição para TeamsOnly usando [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), que controla o modo de coexistência de um usuário. Para obter mais informações sobre cada um dos modos, consulte [modos de coexistência](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes).


Se o administrador executar uma transição gerenciada usando os modos Skype for Business ou apenas as atualizações para o modo TeamsOnly da configuração de ilhas padrão, TeamsUpgradePolicy é a principal ferramenta.  Como qualquer outra política do Microsoft Teams, o TeamsUpgradePolicy pode ser atribuído diretamente a um usuário, e também pode ser definido como o padrão de todo o locatário. Qualquer atribuição para um usuário tem precedência sobre a configuração padrão do locatário.  Ele pode ser gerenciado no console de administração do Teams e no PowerShell.

Os administradores podem atribuir qualquer modo de TeamsUpgradePolicy aos usuários se o usuário estiver hospedado no Skype for Business online ou no local, exceto se o modo TeamsOnly só puder ser atribuído a um usuário que já esteja hospedado no Skype for Business online. <sup>4</sup>  

Os usuários com contas do Skype for Business hospedadas no local [devem ser movidos online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (para o Skype for Business online ou direto para o Microsoft Teams) usando o conjunto de ferramentas de CsUser no Skype for Business local. Esses usuários podem ser movidos para o TeamsOnly nas etapas 1 ou 2:

-   1 etapa: Especifique a opção-MoveToTeams em move-CsUser. Isso requer o Skype for Business Server 2019 ou o Skype for Business Server 2015 com o CU8.

-   2 etapas: após executar move-CsUser, conceda o modo TeamsOnly ao usuário usando TeamsUpgradePolicy.

Ao contrário de outras políticas, não é possível criar novas instâncias de TeamsUpgradePolicy no Office 365. Todas as instâncias existentes são incorporadas ao serviço.  (Observe que Mode é uma propriedade dentro de TeamsUpgradePolicy, em vez do nome de uma instância de política.) Em alguns--mas não em todos os casos, o nome da instância da política é o mesmo que o modo. Em particular, para atribuir o modo TeamsOnly a um usuário, você concederá a instância "UpgradeToTeams" de TeamsUpgradePolicy a esse usuário. Para ver uma lista de todos os casos, você pode executar o seguinte comando:

```
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Para atualizar um usuário online para o modo TeamsOnly, atribua a instância "UpgradeToTeams": 

```
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Para atualizar um usuário local do Skype for Business para o modo TeamsOnly, use move-CsUser no conjunto de ferramentas local:

```
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

Para alterar o modo de todos os usuários no locatário, exceto aqueles que têm uma concessão explícita por usuário (que tem precedência), execute o seguinte comando:

```
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Se você tiver usuários com contas do Skype for Business no local, não deverá atribuir o modo TeamsOnly no nível do locatário, a menos que você explicitamente atribua outro modo para todos os usuários com contas do Skype for Business local.

**Observações:**
<sup>4</sup> isso ocorre porque a interoperabilidade com os usuários e a Federação do Skype for Business só é possível se o usuário estiver hospedado no Skype for Business online.

### <a name="using-notifications-in-skype-for-business-clients"></a>Usar notificações nos clientes Skype for Business

Os administradores têm a opção de fornecer notificações de usuário final no cliente Skype for Business para informar aos usuários que eles logo serão atualizados para o Microsoft Teams, conforme mostrado no diagrama a seguir. Por exemplo, uma semana antes de o administrador planejar a atualização de um grupo de usuários para o modo TeamsOnly, o administrador pode querer ativar essas notificações para esse grupo de usuários. Essas notificações são habilitadas usando uma instância de TeamsUpgradePolicy com NotifySfbUsers = true.  Para todos os modos diferentes de TeamsOnly, há, na verdade, duas instâncias por modo, correspondentes aos dois valores de NotifySfbUsers.  Para todos os modos diferentes de TeamsOnly, há, na verdade, duas instâncias por modo, correspondentes aos dois valores de NotifySfbUsers. 

![Diagrama mostrando notificações](media/teams-upgrade-sfb-with-notifications.png)

Se seus usuários estiverem hospedados no Skype for Business Online, basta atribuir a instância de política que tenha o mesmo modo que o usuário, mas com NotifySfbUsers = verdadeiro. 

Se seus usuários estiverem hospedados no Skype for Business Server no local, você precisará usar o conjunto de ferramentas local e será necessário o Skype for Business Server 2019 ou o CU8 para o Skype for Business Server 2015. Na janela do PowerShell local, crie uma nova instância de TeamsUpgradePolicy com NotifySfbUsers = verdadeiro:

```
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Em seguida, usando a mesma janela do PowerShell local, atribua essa nova política aos usuários desejados:

```
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```


### <a name="meeting-migration"></a>Migração de reunião

Quando um usuário é migrado para o modo TeamsOnly, por padrão, suas reuniões do Skype for Business existentes que eles organizadas serão convertidas para o Microsoft Teams. Opcionalmente, você pode desativar o comportamento padrão ao atribuir o modo TeamsOnly a um usuário. Ao mover usuários do local, as reuniões devem ser migradas para a nuvem para que funcionem com a conta de usuário online, mas se você não especificar-MoveToTeams, as reuniões serão migradas como reuniões do Skype for Business, em vez de serem convertidas para o Microsoft Teams. 

Ao atribuir o modo TeamsOnly no nível do locatário, a migração da reunião não é disparada para nenhum usuário. Se quiser atribuir o modo TeamsOnly no nível do locatário e migrar reuniões, você pode usar o PowerShell para obter uma lista de usuários no locatário (por exemplo, usar Get-CsOnlineUser com os filtros necessários) e fazer um loop por cada um desses usuários para disparar a reunião migração usando Start-CsExMeetingMigration. Para obter detalhes, consulte [usando o serviço de migração de reunião (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).


### <a name="additional-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Considerações adicionais sobre organizações com o Skype for Business Server no local

- Configurar o Skype for Business híbrido é um pré-requisito para migrar para o modo TeamsOnly. Embora seja possível usar o Teams no modo de ilhas sem híbrido, a transição para o modo TeamsOnly não pode ser feita até que o usuário seja movido do Skype for Business local para o Skype for Business online (usando [move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)). Para obter mais informações, consulte [configurar conectividade híbrida](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).

- Os usuários do teams que têm uma conta local do Skype for Business (ou seja, eles ainda não foram movidos para a nuvem usando move-CsUser) não podem interoperar com nenhum usuário do Skype for Business, nem podem federar usuários externos. Essa funcionalidade só estará disponível quando os usuários forem movidos para a nuvem (no modo de ilhas ou como usuários do TeamsOnly). 

- Se você tiver usuários com contas do Skype for Business no local, não deverá atribuir o modo TeamsOnly no nível do locatário, a menos que você explicitamente atribua outro modo para todos os usuários com contas do Skype for Business local. 

- Você deve garantir que seus usuários sejam sincronizados corretamente com o Azure AD com os atributos corretos do Skype for Business. Esses atributos são todos os prefixos com "msRTCSIP-". Se os usuários não forem sincronizados corretamente para o Azure AD, as ferramentas de gerenciamento do Teams não poderão gerenciar esses usuários. Para obter mais informações, consulte [Configurar o Azure ad Connect para Teams e o Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Quando um usuário é movido do local para a nuvem, as reuniões organizadas por esse usuário são migradas para o Skype for Business online ou para o Teams, dependendo se a opção-MoveToTeams está ou não especificada.

- Se quiser exibir notificações no cliente Skype for Business para usuários locais, você deve usar o TeamsUpgradePolicy no conjunto de ferramentas local. Somente o parâmetro NotifySfbUsers é relevante para usuários locais.  Os usuários locais recebem o modo das instâncias online do TeamsUpgradePolicy. Consulte as anotações em [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). 

>[!NOTE]
> Todos os novos locatários criados após 3 de setembro de 2019 são criados como locatários do TeamsOnly sem a capacidade de downgrade dos administradores. Organizações com o Skype for Business Server no local que nunca tinha uma assinatura do Office 365 antes de 3 de setembro de 2019, o precisará entrar em contato com o suporte da Microsoft para fazer o downgrade do locatário, assim que ele adquirir uma assinatura com o Office 365. 


## <a name="perform-the-upgrade-for-your-organization"></a>Executar a atualização para a sua organização

Esta seção descreve as seguintes opções de atualização:

- Atualização lado a lado (usando o modo de ilhas)
- Uma atualização gerenciada para uma organização que ainda não começou a usar o Teams
- Uma atualização gerenciada para uma organização que já está usando equipes no modo de ilhas

### <a name="side-by-side-upgrade-using-islands-mode"></a>Atualização lado a lado (usando o modo de ilhas)

Para a opção de atualização lado a lado:

- Considere esta opção se você pode fazer uma atualização rápida para a sua organização geral.  Como há um risco potencial de confusão com a execução de ambos os clientes, é melhor se você pode minimizar esse período de tempo. Você deve garantir que os usuários saibam que executar os dois clientes.

- Essa opção é o modelo de caixa de saída e não requer ação do administrador para começar a usar o Microsoft Teams, exceto para atribuir a licença do Office 365. Se seus usuários já têm o Skype for Business Online, você pode já estar nesse modelo.

- Pode ser um desafio ficar por fora do modo lado a lado e de passar para TeamsOnly. Como os usuários atualizados só se comunicam via Teams, qualquer outro usuário na organização que se comunique com esse usuário deve estar usando o Microsoft Teams.  Se você tiver usuários que não começaram a usar o Teams, eles serão expostos a mensagens ausentes. Além disso, eles não verão os usuários do TeamsOnly online no Skype for Business. Algumas organizações optam por fazer uma atualização em todo o locatário usando a política global do locatário para evitar isso, no entanto, isso exige espera até que todos os usuários estejam prontos para serem atualizados.


### <a name="a-managed-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Uma atualização gerenciada para uma organização que ainda não começou a usar o Teams

Se a sua organização ainda não tem usuários ativos no Teams, a primeira etapa é definir a política padrão de todo o locatário do TeamsUpgradePolicy para um dos modos do Skype for Business, por exemplo, SfbWithTeamsCollab.  Os usuários que ainda não começaram a usar o Teams não notarão diferença no comportamento. No entanto, definir essa política no nível do locatário torna possível iniciar a atualização dos usuários para o modo TeamsOnly e garante que os usuários atualizados ainda possam se comunicar com usuários não atualizados.  Depois de identificar os usuários piloto, você pode atualizá-los para o TeamsOnly.  Se eles estiverem locais, use move-CsUser. Se estiverem online, basta atribuí-los ao modo TeamsOnly usando TeamsUpgradePolicy.  Por padrão, todas as reuniões do Skype for Business agendadas por esses usuários serão migradas para o Microsoft Teams.

Veja a seguir os comandos principais:

1. Defina o padrão do locatário-Wide para mode SfbWithTeamsCollab da seguinte maneira:

   ```
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Atualize o usuário para TeamsOnly da seguinte maneira:

   - Se o usuário já estiver online:

     ```
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - Se o usuário estiver no local:

     ```
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

Observações
 
- Em vez de definir a política de todo o locatário como SfbWithTeamsCollab, você pode defini-la como SfbWithTeamsCollabAndMeetings. Isso faz com que todos os usuários agendem todas as novas reuniões no Teams.
- Move-CsUser é um cmdlet nas ferramentas locais. A opção MoveToTeams requer o Skype for Business Server 2019 ou o Skype for Business Server 2015 com o CU8. Se estiver usando uma versão anterior, você pode primeiro mover o usuário para o Skype for Business Online e, em seguida, conceder o modo TeamsOnly a esse usuário.
- Por padrão, as reuniões do Skype for Business são migradas para o Microsoft Teams durante a atualização para o modo TeamsOnly ou ao atribuir o modo de SfbWithTeamsCollabAndMeetings.  

O diagrama a seguir mostra as fases conceituais da atualização gerenciada para uma organização sem o uso anterior do teams. A altura das barras representa o número de usuários. Durante qualquer fase da atualização, todos os usuários podem se comunicar uns com os outros.  Os usuários do Skype for Business se comunicam com usuários do TeamsOnly usando a interoperabilidade e vice-versa.

![Diagrama mostrando a atualização gerenciada sem uso anterior do teams](media/teams-upgrade-1.png)


### <a name="a-managed-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Uma atualização gerenciada para uma organização que já está usando equipes no modo de ilhas

Se alguns usuários da sua organização estiverem usando ativamente o Microsoft Teams no modo de ilhas, provavelmente não deseja remover a funcionalidade de usuários existentes. Portanto, uma etapa adicional é necessária antes de alterar a política de todo o locatário. A solução é "avô" esses usuários existentes do Microsoft Teams no modo de ilhas, antes de definir a política de todo o locatário como SfbWithTeamsCollab.  Depois de fazer isso, você poderá prosseguir com a implantação da maneira acima, no entanto, terá dois grupos de usuários que estão indo para o TeamsOnly: os usuários que estavam ativos no Teams estarão no modo de ilhas e os usuários restantes estarão no modo SfbWithTeamsCollab. Você pode mover progressivamente esses usuários para o modo TeamsOnly.

1. Encontre os usuários ativos no Teams da seguinte maneira:

   1. No portal de administração do Office 365, na navegação à esquerda, vá para relatórios e use o uso. 
   2. Na lista suspensa "selecionar um relatório", escolha Microsoft Teams e, em seguida, atividade do usuário. Isso fornecerá uma tabela exportável de usuários que já estão ativos no Teams. 
   3. Clique em exportar, abrir Excel e filtrar para mostrar somente os usuários que estão ativos no Teams.

2. Para cada usuário do Active Teams encontrado na etapa 1, atribua o modo de ilhas no PowerShell no PowerShell remoto. Isso permite que você vá para a próxima etapa e assegure-se de que não altere a experiência do usuário.  

   ```
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. Defina a política de todo o locatário como SfbWithTeamsCollab:

   ```
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. Atualizar os usuários selecionados para o modo TeamsOnly. Você pode optar por atualizar os usuários no modo de ilhas ou no modo SfbWithTeamsCollab, embora você queira priorizar a atualização dos usuários no modo ilhas primeiro para minimizar o potencial de confusão que podem surgir quando os usuários estiverem no modo de ilhas.   

   Para usuários hospedados no Skype for Business Online:  

   ```
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   Para os usuários hospedados no Skype for Business Server no local:  

   ```
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

O diagrama abaixo mostra as fases conceituais de uma transição gerenciada na qual há usuários de ilhas ativas no início. A altura das barras representa o número de usuários. Durante qualquer fase da atualização, todos os usuários podem se comunicar uns com os outros.  Os usuários do Skype for Business se comunicam com usuários do TeamsOnly usando a interoperabilidade e vice-versa.


![Diagrama mostrando a atualização gerenciada com usuários ativos no modo de ilhas](media/teams-upgrade-2.png)

   

## <a name="considerations-for-pstn-calling"></a>Considerações sobre chamadas PSTN

Se a funcionalidade de chamada PSTN estiver envolvida, haverá quatro cenários possíveis ao se mover para o modo TeamsOnly:

- *Um usuário no Skype for Business Online, com um plano de chamadas da Microsoft*. Após a atualização, este usuário continuará a ter um plano de chamadas da Microsoft.

- *Um usuário do Skype for Business Online, com funcionalidade de voz local* via Skype for Business local ou Cloud Connector Edition. A atualização do usuário para o Teams precisa ser coordenada com a migração do usuário para o roteamento direto para garantir que o usuário do TeamsOnly tenha funcionalidade PSTN.

- *Um usuário do Skype for Business no local com o Enterprise Voice, que será movido para online e mantendo a conectividade PSTN local*.  Migrar este usuário para o Teams requer mover a conta do Skype for Business no local para a nuvem e coordenar essa movimentação com a migração do usuário para o roteamento direto. 

- *Um usuário do Skype for Business no local com o Enterprise Voice*, que se moverá para online e usando um plano de chamadas da Microsoft.  Migrar este usuário para o Teams requer mover a conta do Skype for Business no local para a nuvem e coordenar essa movimentação com uma a porta do número de telefone do usuário para um plano de chamadas da Microsoft ou B) atribuir um novo número de assinante de regiões disponíveis.

Este artigo fornece apenas uma visão geral de alto nível.  Para obter mais informações, consulte planos de roteamento e [chamada](calling-plan-landing-page.md)do [sistema de telefonia direto](direct-routing-landing-page.md) . Além disso, observe que o uso do sistema telefônico com Teams só tem suporte quando o usuário está no modo TeamsOnly.  Se o usuário estiver no modo de ilhas, o sistema telefônico só será compatível com o Skype for Business. 

### <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Do Skype for Business online com planos de chamadas da Microsoft 

Este é o cenário de atualização mais simples que envolve voz. 

1. Certifique-se de que os usuários receberam uma licença do teams. Por padrão, quando você atribui uma licença do Office 365, o Teams é habilitado, portanto, a menos que você tenha desabilitado anteriormente a licença do Teams, nenhuma ação deve ser necessária.

2.  Se os usuários já tiverem um plano de chamadas da Microsoft com um número de telefone, a única alteração necessária será atribuir o modo de TeamsOnly do usuário no TeamsUpgradePolicy.  Antes de atribuir o modo de TeamsOnly, as chamadas PSTN de entrada serão feitas no cliente Skype for Business do usuário. Após a atualização para o modo TeamsOnly, as chamadas PSTN de entrada serão enterradas no cliente do teams do usuário.  

### <a name="from-skype-for-business-online-with-on-premises-voice"></a>Do Skype for Business online com voz local

Nesse cenário, o usuário já está no Skype for Business Online, mas a conectividade PSTN é local, usando o Skype for Business Server no modo híbrido ou na edição do conector do Cloud. Migrar esses usuários para o modo TeamsOnly com funcionalidade PSTN significa habilitá-los para roteamento direto, no qual os troncos PSTN se conectam diretamente ao serviço de roteamento direto na nuvem, via SBC (controlador de borda de sessão local).

As etapas básicas estão listadas abaixo.  As etapas 1-4 são listadas na sequência sugerida, mas elas podem ser feitas em qualquer ordem. A chave é que todas elas devem ser concluídas antes da etapa 5.

1. Se você estiver definindo a política de todos os locatários como um dos modos do Skype for Business, não se esqueça de descrever todos os usuários de ilhas existentes, atribuindo explicitamente o modo de ilhas de ilhas, conforme descrito anteriormente.

2. Configure seu locatário para roteamento direto. Consulte o [Resumo da configuração por locatário do roteamento direto](#summary-of-per-tenant-configuration-of-direct-routing).

3. Se desejar, configure várias políticas de equipe para esses usuários (por exemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Isso pode ser feito a qualquer momento, mas se você quiser garantir que os usuários tenham a configuração correta quando forem atualizados, é melhor fazer isso antes de o usuário ser atualizado para o modo TeamsOnly.

4. Preparar os usuários selecionados para a migração de voz: 
   - Se necessário, atribua a licença do teams.  Pressupondo que o usuário já esteja funcional na voz local do Skype for Business Online, o usuário já tem o plano 2 do Skype for Business e também o Microsoft Phone System. Deixe ambos os planos habilitados, incluindo a licença do Skype for Business online plano 2.  
   - Atribua o OnlineVoiceRoutingPolicy desejado. 

5. Atualize o usuário: essas etapas devem ser coordenadas. 

   - No Office 365, atualize o usuário para o modo TeamsOnly (Grant-CsTeamsUpgradePolicy).
   - No SBC, configure o roteamento de voz para permitir chamadas recebidas enviando chamadas para roteamento direto em vez de para o servidor de mediação local.


### <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>No Skype for Business Server local, com o Enterprise Voice, para roteamento direto

Nesse cenário, o usuário ainda é hospedado no Skype for Business local, e a conectividade PSTN também é local. Migrar esses usuários para o modo TeamsOnly com funcionalidade PSTN significa habilitá-los para roteamento direto e, em seguida, mover o usuário para a nuvem. 
 
As etapas básicas estão listadas abaixo.  As etapas 1-5 são listadas na sequência sugerida, mas elas podem ser feitas em qualquer ordem. A chave é que todas elas devem ser concluídas antes da etapa 6.

1. Se você estiver definindo a política de todos os locatários como um dos modos do Skype for Business, não deixe de apresentar os usuários de ilhas existentes atribuindo explicitamente o modo de ilhas de ilhas, conforme descrito anteriormente.

2. Se você ainda não fez isso, [Configure a organização para o Skype for Business híbrido](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Configure seu locatário para roteamento direto. Consulte o [Resumo da configuração por locatário do roteamento direto](#summary-of-per-tenant-configuration-of-direct-routing).

4. Se desejar, configure várias políticas de equipe para esses usuários (por exemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Isso pode ser feito a qualquer momento, mas se você quiser garantir que os usuários tenham a configuração correta quando forem atualizados, é melhor fazer isso antes de o usuário ser atualizado para o TeamsOnly.

5. Atribua as licenças do Office 365, se necessário.  O usuário deve ter o plano 2 do teams online e do Skype for Business Online, bem como o sistema telefônico. Se o Skype for Business online plano 2 estiver desabilitado, habilite-o novamente.  

6. Atualize o usuário: essas etapas devem ser coordenadas. 

   - Usando as ferramentas locais do Skype for Business, execute move-CsUser com a opção-MoveToTeams. Se você estiver usando uma versão do Skype for Business Server que não seja compatível com a opção MoveToTeams, primeiro execute move-CsUser e, em seguida, atribua o modo TeamsOnly no PowerShell remoto do locatário ou no console de administração do teams.

   - No SBC, configure o roteamento de voz para permitir chamadas recebidas enviando chamadas para roteamento direto em vez de para o servidor de mediação local. 

   - No Office 365: atribua o OnlineVoiceRoutingPolicy relevante para habilitar as chamadas feitas. 


### <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>No Skype for Business Server local, com o Enterprise Voice, para o plano de chamadas da Microsoft

Nesse cenário, o usuário ainda é hospedado no Skype for Business local, e a conectividade PSTN também é local. Migrar esses usuários para o modo TeamsOnly com funcionalidade PSTN significa mover o usuário para a nuvem e fazer a portabilidade do número da transportadora antiga para um plano de chamadas da Microsoft ou atribuir um novo número ao usuário. 

As etapas básicas estão listadas abaixo.As etapas 1-5 são listadas na sequência sugerida, mas elas podem ser feitas em qualquer ordem. A chave é que todas elas devem ser concluídas antes da etapa 6. 

1. Se você estiver definindo a política de todos os locatários como um dos modos do Skype for Business, não deixe de apresentar os usuários de ilhas existentes atribuindo explicitamente o modo de ilhas de ilhas, conforme descrito anteriormente. 

2. Se você ainda não fez isso, [Configure a organização para o Skype for Business híbrido](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity). 

3. Se desejar, configure várias políticas de equipe para esses usuários (por exemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Isso pode ser feito a qualquer momento, mas se você quiser garantir que os usuários tenham a configuração correta quando forem atualizados, é melhor fazer isso antes de o usuário ser atualizado para o TeamsOnly. 

4. Atribua as licenças do Office 365, se necessário.O usuário deve ter o plano 2 do teams online e do Skype for Business Online, bem como o sistema telefônico. Se o Skype for Business online plano 2 estiver desabilitado, habilite-o novamente.  

5. Obter números de telefone para seus usuários. (Para obter detalhes, consulte [gerenciar números de telefone para sua organização](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).)

   - Se você for reutilizar os números, envie uma solicitação de portabilidade para a sua operadora.  
   - Você também pode adquirir novos números diretamente da Microsoft. 

6. Atualize o usuário. Usando as ferramentas locais do Skype for Business, execute move-CsUser com a opção-MoveToTeams.  

    - Se estiver transportando números para a Microsoft, você deve coordenar o intervalo dessa operação para ocorrer quando a porta ocorrer. 

    - Se você estiver usando novos números da Microsoft, será necessário alterar o LineUri para o usuário.Isso deve ser feito nas ferramentas locais e depois sincronizado com a nuvem por meio do Azure AD Connect. Você deve cronometrar a operação move-CsUser para ser simultânea quando o Azure AD Connect sincroniza a alteração. 

### <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Resumo da configuração por locatário do roteamento direto 

1. Verifique se o seu controlador de borda de sessão (SBC) é compatível com o roteamento direto analisando [esta lista](direct-routing-border-controllers.md). Você também deve certificar-se de que tem a versão correta do firmware.  

2. Emparelhar seu SBC local com o serviço de roteamento Direct Teams. Para obter detalhes, consulte [emparelhar o SBC com o serviço de roteamento direto do sistema telefônico](direct-routing-configure.md#pair-the-sbc-to-the-direct-routing-service-of-phone-system). 

3. Essa configuração é essencialmente um espelho da configuração local. A configuração online consiste em: 
   - OnlineVoiceRoutingPolicy (com base no VoiceRoutingPolicy local, com a migração de usuários do Skype for Business Online e com base em VoicePolicy se migrar usuários do local com o Enterprise Voice).
   - Objetos OnlinePSTNUsage (com base no uso de PSTN local). 
   - Objetos OnlineVoiceRoute (baseados em VoiceRoutes locais). 

Para obter mais informações, consulte [Configurar o roteamento direto](direct-routing-configure.md). 

### <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Gerenciar a propriedade EnterpriseVoiceEnabled durante a migração 

Seja usando o roteamento direto ou um plano de chamadas da Microsoft, um usuário deve ter EnterpriseVoiceEnabled = true no Azure AD para que o usuário tenha a funcionalidade PSTN.  EnterpriseVoiceEnabled ("EV-Enabled") é uma propriedade (não uma política) que existe em um diretório local e na nuvem. O valor na nuvem é o que importa para o Teams.  A lógica exata para a maneira como o habilitado para EV é definida como true depende do seguinte cenário: 

- Se o usuário for compatível com EV no local Skype for Business Server e uma licença do sistema de telefonia for atribuída ao usuário antes de passar o usuário para a nuvem com move-CsUser, o usuário online será provisionado com EV-Enabled = true. 

- Se um usuário existente do TeamsOnly ou do Skype for Business Online for atribuído a uma licença do sistema de telefonia, o EV-Enabled não será definido como true por padrão.  Esse também será o caso se um usuário local for movido para a nuvem antes de atribuir a licença do sistema telefônico. Em ambos os casos, o administrador deve especificar o seguinte cmdlet: 

  ```
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="coexistence-of-teams-with-skype-for-business"></a>Coexistência de equipes com o Skype for Business

Esta seção resume o comportamento que pode ser experiente ao executar o cliente do Microsoft Teams e do Skype for Business na mesma organização, independentemente do modo de exibição e do método de atualização usado:

- [Reuniões](#meetings)
- [Interoperabilidade](#interoperability)
- [Conversas de equipes – interoperabilidade versus threads nativos](#teams-conversations---interop-versus-native-threads)
- [Presença](#presence)
- [Federação](#federation)
- [Contatos](#contacts)

### <a name="meetings"></a>Reuniões

Seja qual for o seu modo, os usuários sempre podem ingressar em qualquer tipo de reunião ao qual sejam convidados, seja o Skype for Business ou Teams.  No entanto, os usuários devem ingressar na reunião com um cliente correspondente que corresponda ao tipo de reunião:

- Se a reunião for uma reunião do Teams, todos os participantes (sejam TeamsOnly, Ilhas ou usuários do Skype for Business) usarão o cliente do teams para ingressar na reunião. Se o Microsoft Teams não estiver instalado, o usuário será encaminhado à Web, durante a tentativa de ingressar em uma reunião.

- Se a reunião for uma reunião do Skype for Business, todos os participantes (sejam TeamsOnly, Ilhas ou usuários do Skype for Business) usarão o cliente Skype for Business para ingressar na reunião. Se o cliente Skype for Business não estiver instalado, o usuário será direcionado à Web para participar pelo aplicativo de reunião do Skype.

Ao organizar reuniões, o tipo de reunião que é agendado baseia-se no modo do organizador, como mostrado na tabela a seguir:

| Modo do organizador    |      Comportamento |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Todas as reuniões agendadas no Teams. O suplemento Skype for Business não está disponível no Outlook. | 
| SfbWithTeamsCollab, SfbOnly   | Todas as reuniões agendadas no Skype for Business. O suplemento de equipe não está disponível no Outlook. | 
| McDonald |     As reuniões podem ser agendadas no Skype for Business ou no Teams. Os dois suplementos estão disponíveis no Outlook. | 


### <a name="interoperability"></a>Interoperabilidade

O Teams é compatível com a interoperabilidade ("interoperabilidade") com o Skype for Business em determinados cenários. A comunicação por interoperabilidade se refere a um chat ou uma chamada entre um usuário do Skype for Business e um usuário do teams.  A comunicação de interoperabilidade só é possível entre dois usuários; Não há suporte para chats/chamadas de vários participantes ou para adicionar outros usuários.

Um chat ou chamada interoperabilidade entre dois usuários é criado quando cada uma das seguintes opções é verdadeira:

- Um usuário está usando o Microsoft Teams e o outro está usando o Skype for Business.

- O modo do destinatário da comunicação inicial não é as ilhas (caso contrário, a comunicação se esterraria no mesmo cliente) se ambos os usuários estiverem na mesma organização. Em cenários federados, o usuário de envio está usando o Teams e o destinatário não está no modo TeamsOnly. 

- O usuário do teams também não tem uma conta do Skype for Business hospedada no local. 

Na comunicação de interoperabilidade, o chat somente é de texto sem formatação. Além disso, o compartilhamento de arquivos e o compartilhamento não são possíveis *no chat de interoperabilidade*. No entanto, os usuários em uma conversa de interoperabilidade podem facilmente alcançar arquivos e/ou compartilhamento criando uma reunião sob demanda de dentro do chat de interoperabilidade, conforme descrito abaixo:

- Se o usuário do teams tentar compartilhar a tela, uma reunião de equipes sob demanda será criada automaticamente e um link de convite para essa reunião será enviado ao cliente do usuário do Skype for Business. Ao clicar no link, o usuário do Skype for Business abrirá o Teams e ingressará na reunião. Os dois usuários estão agora em uma reunião do Teams e podem compartilhar conforme necessário.

- Se o usuário do Skype for Business estiver usando um cliente do 2018 ou posterior e tentar compartilhar qualquer conteúdo, uma reunião do Skype for Business por demanda será criada automaticamente e um link de convite para essa reunião será enviado ao cliente do usuário da equipe. Ao clicar no link, o usuário do teams tentará ingressar na reunião do Skype for Business. Se o usuário do teams tiver o cliente Skype for Business instalado, ele será aberto e o usuário será solicitado a entrar (se ainda não tiver entrado).  Se o usuário do Teams não tiver o cliente Skype for Business instalado, o usuário será solicitado a usar a versão da Web. Depois que os dois usuários estiverem conectados, eles estão em uma reunião do Skype for Business e podem compartilhar conforme necessário.

### <a name="teams-conversations---interop-versus-native-threads"></a>Conversas de equipes – interoperabilidade versus threads nativos

Como as comunicações de interoperabilidade não são compatíveis com todos os recursos da conversa de equipes nativas, o cliente das equipes mantém threads de conversa separados para comunicações entre equipes e equipes para Skype para empresas. Essas conversas são renderizadas de forma diferente na interface do usuário: os threads de interoperabilidade podem ser diferenciados de um thread regular de equipes nativas por:

- Falta de controles para Rich Text, arquivo/compartilhamento, incapacidade de adicionar usuários.
- Uma modificação no ícone do usuário de destino, mostrando um "S" para o Skype for Business.

Essas diferenças são mostradas nas seguintes capturas de tela:

Uma conversa entre equipes nativas com o teste G3 do usuário

![Diagrama mostrando uma conversa de equipes nativas para equipes](media/teams-upgrade-native-thread.png)

Uma conversa de interoperabilidade com o mesmo teste G3 do usuário

![Diagrama mostrando uma conversa entre equipes de interoperabilidade para equipes](media/teams-upgrade-interop-thread.png)

Após a criação de um thread de conversa, o tipo nunca muda. Uma vez criado, um thread de interoperabilidade no Teams sempre direcionará para o cliente Skype for Business do usuário de destino. Um thread nativo sempre direcionará para o cliente das equipes do usuário de destino.  Se o modo de um usuário do destinatário for alterado, os threads existentes do usuário não funcionarão mais e uma nota será exibida nesse chat com um link para iniciar uma nova conversa nativa, como mostra a captura de tela a seguir. Para obter mais detalhes, consulte [chats e chamadas de threads](coexistence-chat-calls-presence.md#chats-and-calls-from-pre-existing-threads)preexistentes.


![Diagrama mostrando um chat com usuário atualizado do Skype for Business](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Presença

A presença de um determinado usuário baseia-se na atividade do usuário no serviço por meio do cliente. A presença é publicada para que outros usuários vejam.  O Skype for Business e o Teams são serviços separados com clientes separados, portanto, cada serviço tem seu próprio estado de presença para um usuário.   Também há sincronização entre os serviços de presença no Teams e no Skype for Business online.  Isso permite que um serviço publique a presença do usuário a partir do outro serviço, se necessário. 

O comportamento de publicação de presença é baseado no modo do usuário. Há três casos básicos:

- Se um usuário estiver no modo TeamsOnly, todos os outros usuários verão a presença do teams para esse usuário, independentemente do cliente usado.

- Se um usuário estiver em qualquer um dos modos do Skype for Business, todos os outros usuários verão a presença do Skype for Business para esse usuário, independentemente do cliente usado.

- Se um usuário estiver no modo de ilhas, a presença publicada no Skype for Business e nas equipes será independente, portanto, a presença mostrada para os usuários dentro da mesma organização dependerá do cliente do outro usuário. Os usuários de organizações federadas verão a presença desse usuário com base em suas atividades do Skype for Business, pois o tráfego federado para um usuário do modo de ilhas de ilhas chega no Skype for Business.

Por exemplo, suponha que o usuário A esteja no modo de ilhas. Se o usuário A estiver ativo no Teams, mas não estiver conectado ao Skype for Business, outros usuários veriam o usuário A como ativo do cliente de suas equipes, mas no cliente do Skype for Business, eles verão o usuário A como offline. Isso ocorre por design, pois o usuário A não pode ser acessado se não estiver executando o cliente. 

Para obter mais informações, consulte [presença](coexistence-chat-calls-presence.md#presence).

### <a name="federation"></a>Federação

A Federação do teams para outro usuário usando o Skype for Business exige que o usuário do teams seja hospedado online no Skype for Business. O TeamsUpgradePolicy rege o roteamento para chats e chamadas federados e de entrada. O comportamento de roteamento federado é o mesmo dos cenários do mesmo locatário, exceto no modo de ilhas. Quando os destinatários estão no modo de ilhas:

- Chats e chamadas iniciadas do teams Land no Skype for Business se o destinatário estiver em um locatário federado.
- Chats e chamadas iniciadas do teams Land nas equipes se o destinatário estiver no mesmo locatário.
- Chats e chamadas iniciados pelo Skype for Business sempre se esterram no Skype for Business.

Um chat federado entre um usuário do Teams e um Skype for Business é um thread de interoperabilidade, portanto Rich Text e compartilhamento não são possíveis. A interface do usuário expõe chats federados de maneira semelhante aos mesmos threads de interoperabilidade do locatário, exceto que há uma observação indicando que o usuário é externo.

Quando o Microsoft Teams introduziu a Federação, um chat federado entre dois usuários do teams era também um thread de interoperabilidade, mas no futuro, a Federação de equipes nativas será introduzida, que fornece funcionalidade completa para conversas entre os usuários que estão no modo TeamsOnly. . 

Para obter mais detalhes, consulte [Roteamento federado para novos chats ou chamadas](coexistence-chat-calls-presence.md#federated-routing-for-new-chats-or-calls).

### <a name="contacts"></a>Contatos

O Teams e o Skype for Business têm listas separadas de contatos. Isso significa que adições de contato, remoção e modificações feitas em um sistema não são sincronizadas com o outro sistema. No entanto, os contatos do Skype for Business são copiados automaticamente para o Microsoft Teams quando ocorrem dois eventos específicos: 

- Para qualquer usuário do Skype for Business Online, na primeira vez que fizer logon no Microsoft Teams, os contatos do Skype for Business serão copiados para o Microsoft Teams.  Esse comportamento não está disponível para usuários com uma conta local no Skype for Business Server.  

- Depois que um usuário for atualizado para o TeamsOnly (por meio da atribuição de TeamsUpgradePolicy ou via move-CsUser-MoveToTeams), da próxima vez que um usuário fizer logon no Microsoft Teams, os contatos existentes no Skype for Business serão mesclados com contatos existentes já presentes no Microsoft Teams. Esse comportamento ocorre se a conta do Skype for Business do usuário for hospedada no local ou online. 

Em ambos os casos, a transferência de contatos do Skype for Business para o Microsoft Teams é assíncrona, por isso pode ser um número de minutos para que os contatos sejam exibidos no Microsoft Teams. Os dois eventos acima são o que aciona a cópia.  

## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar a conectividade híbrida entre o Skype for Business Server e o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar o serviço de migração de reunião (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

