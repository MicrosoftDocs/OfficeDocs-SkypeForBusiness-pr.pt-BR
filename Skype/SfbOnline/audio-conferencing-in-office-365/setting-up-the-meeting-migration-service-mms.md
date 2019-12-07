---
title: Usando o Meeting Migration Service (MMS)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: O serviço de migração de reunião (MMS) é um serviço executado em segundo plano e atualiza automaticamente as reuniões do Skype for Business e do Microsoft Teams para usuários. MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.
ms.openlocfilehash: 91fcc1b95e107f36a55516e7f459eb8fae581bbe
ms.sourcegitcommit: 0f2024740e03af303efc62e7f54aa918a61ca51b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2019
ms.locfileid: "39890525"
---
# <a name="using-the-meeting-migration-service-mms"></a>Usando o Meeting Migration Service (MMS)

O serviço de migração de reunião (MMS) é o serviço que atualiza as reuniões existentes de um usuário nos seguintes cenários:

- Quando um usuário é migrado do local para a nuvem (seja para Skype for Business online ou TeamsOnly).
- Quando um administrador faz uma alteração nas configurações de audioconferência de áudio do usuário 
- Quando um usuário online é atualizado somente para equipes ou quando o modo de um usuário no TeamsUpgradePolicy é definido como SfBwithTeamsCollabAndMeetings
- Quando você usa o PowerShell 


Por padrão, o MMS é disparado automaticamente em cada um desses casos, embora os administradores possam desabilitá-lo no nível do locatário. Além disso, os administradores podem usar um cmdlet do PowerShell para disparar manualmente a migração de reunião para um determinado usuário.


**Limitações**: o serviço de migração de reunião não poderá ser usado se qualquer uma das seguintes opções se aplicar:

- A caixa de correio do usuário é hospedada no Exchange local.
- O usuário está sendo migrado da nuvem para o Skype for Business Server no local.

Nessas situações, os usuários finais podem usar a [ferramenta de migração de reunião](https://www.microsoft.com/en-us/download/details.aspx?id=51659) para migrar suas próprias reuniões em vez disso.

## <a name="how-mms-works"></a>Como o MMS funciona

Quando o MMS é acionado para um determinado usuário, uma solicitação de migração desse usuário é colocada em uma fila. Para evitar qualquer condição de corrida, a solicitação enfileirada não é processada, até que pelo menos 90 minutos tenha sido eliminado. Depois que o MMS processar a solicitação, ele executará as seguintes tarefas:

1. Ele pesquisa a caixa de correio do usuário em busca de todas as reuniões existentes organizadas por esse usuário e agendadas no futuro.
2. Com base nas informações encontradas na caixa de correio do usuário, ela atualiza ou agenda novas reuniões em qualquer um dos Teams ou no Skype for Business online para esse usuário, dependendo do cenário exato.
3. Na mensagem de email, ele substitui o bloco de reunião online nos detalhes da reunião.
4. Ele envia a versão atualizada dessa reunião para todos os destinatários da reunião em nome do organizador da reunião. Os convidados da reunião receberão uma atualização de reunião com as coordenadas de reunião atualizadas em seus emails. 

    ![O bloco de reuniões que são atualizadas pelo MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

Do tempo em que o MMS é disparado, geralmente leva cerca de 2 horas até que as reuniões do usuário sejam migradas. No entanto, se o usuário tiver um grande número de reuniões, pode demorar mais. Se o MMS encontrar um erro ao migrar uma ou mais reuniões para o usuário, ele tentará periodicamente até 9 vezes ao longo do intervalo de 24 horas.

**Observações**:

- O MMS substitui todo o bloco de informações da reunião online durante a migração da reunião. Portanto, se o usuário editou esse bloco, essas alterações serão substituídas. O conteúdo dos detalhes da reunião que estiver fora do bloco de informações da reunião online não será afetado.
- Somente as reuniões do Skype for Business ou do Microsoft Teams agendadas clicando no botão **Adicionar reunião do Skype** no Outlook na Web ou usando o suplemento de reunião do Skype para Outlook são migrados. Se um usuário copiar e colar as informações da reunião online do Skype de uma reunião para uma nova reunião, essa nova reunião não será atualizada, pois não há reunião no serviço original.
- O conteúdo da reunião criado ou associado à reunião (quadros de comunicações, Polls e assim por diante) não será mantido após a execução do MMS. Se os organizadores da reunião tiverem anexado algum conteúdo às reuniões antecipadamente, será necessário recriar esse conteúdo após a execução do MMS.
- O link para as notas da reunião compartilhada no item do calendário e na reunião do Skype também serão sobrescritos. Observe que as anotações da reunião real armazenadas no OneNote ainda estarão lá; Só é o link para as anotações compartilhadas que são sobrescritas.
- Reuniões com mais de 250 participantes (incluindo o organizador) não serão migradas.
- Alguns caracteres UNICODE no corpo do convite podem ser atualizados incorretamente para um dos seguintes caracteres especiais: ï, 1/2,.

## <a name="triggering-mms-for-a-user"></a>Disparando o MMS para um usuário

Esta seção descreve o que acontece quando o MMS é acionado em cada um dos seguintes casos:

- Quando um usuário é migrado do local para a nuvem
- Quando um administrador faz uma alteração nas configurações de audioconferência de áudio do usuário 
- Quando o modo do usuário no TeamsUpgradePolicy é definido como TeamsOnly ou SfBWithTeamsCollabAndMeetings (usando o PowerShell ou o portal de administração do Teams)
- Quando você usa o cmdlet do PowerShell, Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Atualizando reuniões ao mover um usuário local para a nuvem

Esse é o cenário mais comum em que o MMS ajuda a criar uma transição mais suave para seus usuários. Sem a migração de reuniões, as reuniões existentes organizadas por um usuário no Skype for Business Server local não funcionariam mais quando o usuário foi movido online. Portanto, quando você usa as ferramentas de administração local ( `Move-CsUser` ou o painel de controle de administração) para mover um usuário para a nuvem, as reuniões existentes são automaticamente movidas para a nuvem da seguinte maneira:

- Se a `MoveToTeams` opção entrada `Move-CsUser` for especificada, as reuniões serão migradas diretamente para o Microsoft Teams e o usuário estará no modo TeamsOnly. O uso dessa opção requer o Skype for Business Server 2015 com CU8 ou posterior. Esses usuários ainda podem participar de uma reunião do Skype for Business no qual possam ser convidados, usando o cliente Skype for Business ou o aplicativo de reunião do Skype.
- Caso contrário, as reuniões são migradas para o Skype for Business online.

Em ambos os casos, se o usuário tiver recebido uma licença de audioconferência antes de ser movida para a nuvem, as reuniões serão criadas com as coordenadas de discagem. Se você mover um usuário do local para a nuvem e quiser que ele use a videoconferência, recomendamos que primeiro atribua a conferência de áudio antes de mover o usuário para que somente uma migração de reunião seja disparada.


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Atualizando reuniões quando as configurações de audioconferência de áudio de um usuário mudam

Nos casos a seguir, o MMS atualizará as reuniões existentes do Skype for Business e do Microsoft Teams para adicionar, remover ou modificar as coordenadas de discagem:

- Ao atribuir ou remover uma licença do serviço Microsoft Audio Conferencing para um usuário e esse usuário não está habilitado para um provedor de serviços de audioconferência de terceiros.
- Quando você altera o provedor de serviços de audioconferência de um usuário de qualquer outro provedor para a Microsoft, contanto que o usuário receba uma licença de conferência de áudio da Microsoft. Para obter mais informações, consulte [atribuir a Microsoft como o provedor de áudio de audioconferência](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider). Observe também que o suporte para provedores de serviços de audioconferência de terceiros [ACP] está agendado para o fim da vida em 1º de abril de 2019, como [anunciado anteriormente](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers).
- Quando você habilita ou desabilita a conferência de áudio para um usuário.
- Ao alterar ou redefinir a ID de conferência de um usuário configurado para usar reuniões públicas.
- Ao mover o usuário para uma nova ponte de audioconferência.
- Quando um número de telefone de uma ponte de audioconferência é desatribuído. Esse é um cenário complexo que requer etapas adicionais. Para obter mais informações, consulte [alterar os números de telefone na ponte de videoconferência](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

Nem todas as alterações nas configurações de audioconferência de áudio de um usuário são disparadas em MMS. Em particular, as duas alterações a seguir não resultarão na atualização das reuniões pelo MMS:

- Quando você altera o endereço SIP do organizador da reunião (o nome de usuário ou o domínio SIP)
- Quando você altera a URL da reunião da sua organização `Update-CsTenantMeetingUrl` usando o comando.


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Atualizando reuniões ao atribuir TeamsUpgradePolicy

Por padrão, a migração de reunião é disparada automaticamente quando um usuário recebe `TeamsUpgradePolicy` uma `mode=TeamsOnly` instância `mode= SfBWithTeamsCollabAndMeetings`de with ou. Se você não quiser migrar reuniões ao conceder um desses modos, especifique `MigrateMeetingsToTeams $false` in `Grant-CsTeamsUpgradePolicy` (se estiver usando o PowerShell) ou desmarque a caixa para migrar reuniões ao definir o modo de coexistência de um usuário (se estiver usando o portal de administração do Teams).

Observe também o seguinte:

- A migração de reunião é invocada somente `TeamsUpgradePolicy` quando você concede a um usuário específico. Se você conceder `TeamsUpgradePolicy` com `mode=TeamsOnly` ou `mode=SfBWithTeamsCollabAndMeetings` com base em um *locatário* , a migração de reunião não será invocada.
- Só é possível conceder um usuário no modo TeamsOnly se o usuário estiver hospedado online. Os usuários hospedados no local devem ser movidos usando `Move-CsUser` conforme descrito anteriormente.
- A concessão de um modo diferente de TeamsOnly ou SfBWithTeamsCollabAndMeetings não converte reuniões de equipes existentes em reuniões do Skype for Business.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Disparar a migração de reunião manualmente por meio do cmdlet do PowerShell

Além das migrações automáticas de reunião, os administradores podem disparar manualmente a migração de reunião para um usuário `Start-CsExMeetingMigration`executando o cmdlet. Esse cmdlet enfileira uma solicitação de migração para o usuário especificado.  Além do parâmetro obrigatório `Identity` , ele aceita dois parâmetros opcionais `SourceMeetingType` e `TargetMeetingType`, que permitem que você especifique como migrar reuniões:

**TargetMeetingType:**

- Usando `TargetMeetingType Current` especifica que as reuniões do Skype for Business permanecem reuniões do Skype for Business e as reuniões da equipe permanecem em reuniões do teams. Contudo, as coordenadas de videoconferência podem ser alteradas e todas as reuniões do Skype for Business locais serão migradas para o Skype for Business online. Esse é o valor padrão para TargetMeetingType.
- Usar `TargetMeetingType Teams` especifica que qualquer reunião existente deve ser migrada para o Microsoft Teams, independentemente de a reunião estar hospedada no Skype for Business online ou no local, e independentemente de serem necessárias qualquer atualização de audioconferência. 

**SourceMeetingType:**
- Usar `SourceMeetingType SfB` indica que somente as reuniões do Skype for Business (sejam locais ou online) devem ser atualizadas.
- Usar `SourceMeetingType Teams` indica que apenas reuniões de equipes devem ser atualizadas.
- Usar `SourceMeetingType All` indica que as reuniões do Skype for Business e as reuniões de equipes devem ser atualizadas. Esse é o valor padrão para SourceMeetingType.
    

O exemplo a seguir mostra como iniciar a migração de reunião para o usuário ashaw@contoso.com para que todas as reuniões sejam migradas para o Teams:

```
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>Gerenciando o MMS

Usando o Windows PowerShell, você pode verificar o status de migrações em andamento, disparar manualmente a migração de reuniões e desabilitar a migração completamente. 

### <a name="check-the-status-of-meeting-migrations"></a>Verificar o status das migrações de reunião

Use o `Get-CsMeetingMigrationStatus` cmdlet para verificar o status das migrações de reuniões. Veja a seguir alguns exemplos.

- Para obter um status de Resumo de todas as migrações de MMS, execute o seguinte comando que fornece uma exibição tabular de todos os Estados de migração:

    ```
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- Para obter detalhes completos de todas as migrações dentro de um período de tempo específico `StartTime` , `EndTime` use os parâmetros e. Por exemplo, o comando a seguir retornará detalhes completos sobre todas as migrações ocorridas a partir de 1 ° de outubro de 2018 para 8 de outubro de 2018.

    ```
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- Para verificar o status de migração para um usuário específico, use o `Identity` parâmetro. Por exemplo, o comando a seguir retornará o status para o usuário ashaw@contoso.com:

    ```
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
Se você vir todas as migrações que falharam, tome medidas para resolver esses problemas o mais rápido possível, uma vez que as pessoas não poderão discar para as reuniões organizadas por esses usuários até você resolvê-los. Se `Get-CsMeetingMigrationStatus` o mostrar migrações em um estado de falha, execute estas etapas:
 
1. Determine quais usuários são afetados. Execute o seguinte comando para obter a lista de usuários afetados e o erro específico que foi relatado:

    ```
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. Para cada usuário afetado, execute a ferramenta de migração de reunião para migrar manualmente suas reuniões.

3. Se a migração com a ferramenta de migração de reuniões também não funcionar, você terá duas opções:

    - Fazer os usuários criarem novas reuniões do Skype.
    - [Contatar o suporte](https://go.microsoft.com/fwlink/p/?LinkID=518322).


### <a name="enabling-and-disabling-mms"></a>Habilitando e desabilitando o MMS

O MMS é habilitado por padrão para todas as organizações, mas pode ser desabilitado da seguinte maneira:

- Desabilite completamente para o locatário. 
- Desabilitar somente para alterações relacionadas à videoconferência. Nesse caso, o MMS ainda será executado quando um usuário for migrado do local para a nuvem ou quando você conceder o modo TeamsOnly ou o modo SfBWithTeamsCollabAndMeetings `TeamsUpgradePolicy`.

Por exemplo, você pode optar por migrar manualmente todas as reuniões ou desabilitar o MMS temporariamente enquanto faz alterações substanciais nas configurações de audioconferência da sua organização

Para ver se o MMS está habilitado para sua organização, execute o seguinte comando. O MMS estará habilitado se `MeetingMigrationEnabled` o parâmetro `$true`for.
```
Get-CsTenantMigrationConfiguration
```
Para habilitar ou desabilitar o MMS completamente, use `Set-CsTenantMigrationConfiguration` o comando. Por exemplo, para desabilitar o MMS, execute o seguinte comando:

```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
Se o MMS estiver habilitado na organização e você quiser verificar se ele está habilitado para atualizações de audioconferência, verifique o valor do `AutomaticallyMigrateUserMeetings` parâmetro na saída de. `Get-CsOnlineDialInConferencingTenantSettings` Para habilitar ou desabilitar o MMS para a videoconferência, `Set-CsOnlineDialInConferencingTenantSettings`use. Por exemplo, para desabilitar o MMS para a videoconferência, execute o seguinte comando:

```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Mover os usuários entre um ambiente local e a nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
