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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: O MMS (Serviço de Migração de Reunião) é um serviço executado em segundo plano e atualiza automaticamente Skype for Business e Microsoft Teams para usuários.
ms.openlocfilehash: a7e917a5b579c60ff84c3e1a5e6468a28f75faff
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671637"
---
# <a name="using-the-meeting-migration-service-mms"></a>Usando o Meeting Migration Service (MMS)

O MMS (Serviço de Migração de Reunião) é um serviço que atualiza as reuniões existentes de um usuário nos seguintes cenários:

- Quando um usuário é migrado do local para a nuvem.
- Quando um administrador faz uma alteração nas configurações de audioconferência do usuário
- Quando um usuário online é atualizado somente para Teams ou quando o modo de um usuário no TeamsUpgradePolicy é definido como SfBwithTeamsCollabAndMeetings
- Quando você usa o PowerShell

Por padrão, o MMS é disparado automaticamente em cada um desses casos. Além disso, os administradores podem usar um cmdlet do PowerShell para disparar manualmente a migração de reunião para um determinado usuário.

**Limitações**: o serviço de migração de reunião não poderá ser usado se qualquer uma das seguintes opções se aplicar:

- A caixa de correio do usuário é hospedada Exchange local.
- O usuário está sendo migrado da nuvem para Skype for Business Server local.

## <a name="how-mms-works"></a>Como funciona o MMS

Quando o MMS é disparado para um determinado usuário, uma solicitação de migração para esse usuário é colocada em uma fila. Para evitar qualquer condição de corrida, a solicitação enfileirada não é processada deliberadamente até que pelo menos 90 minutos tenham passado. Depois que o MMS processa a solicitação, ele executa as seguintes tarefas:

1. Ele pesquisa na caixa de correio desse usuário todas as reuniões existentes organizadas por esse usuário e agendadas no futuro.
2. Com base nas informações encontradas na caixa de correio do usuário, ele atualiza ou agenda novas reuniões no Teams para esse usuário, dependendo do cenário exato.
3. Na mensagem de email, ele substitui o bloco de reunião online nos detalhes da reunião.
4. Ele envia a versão atualizada dessa reunião para todos os destinatários da reunião em nome do organizador da reunião. Os convidados da reunião receberão uma atualização de reunião com coordenadas de reunião atualizadas em seus emails.

    ![O bloco de reunião que é atualizado pelo MMS.](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

A partir do momento em que o MMS é disparado, normalmente leva cerca de 2 horas até que as reuniões do usuário sejam migradas. No entanto, se o usuário tiver um grande número de reuniões, poderá levar mais tempo. Se o MMS encontrar um erro ao migrar uma ou mais reuniões para o usuário, ele tentará periodicamente até 9 vezes durante o período de 24 horas.

**Observações**:

- O MMS substitui todo o bloco de informações da reunião online durante a migração da reunião. Portanto, se o usuário editou esse bloco, essas alterações serão substituídas. O conteúdo dos detalhes da reunião que estiver fora do bloco de informações da reunião online não será afetado. Isso significa que todos os arquivos anexados ao convite da reunião ainda serão incluídos.
- Somente as reuniões Skype for Business ou Microsoft Teams que foram agendadas clicando no botão Adicionar reunião do Skype  no Outlook na Web ou usando o suplemento Reunião do Skype para Outlook são migradas. Se um usuário copiar e colar as Skype de reunião online de uma reunião para uma nova reunião, essa nova reunião não será atualizada, pois não há nenhuma reunião no serviço original.
- O conteúdo da reunião que foi criado ou anexado à reunião (quadros de comunicações, votações e assim por diante) não será retido após a execução do MMS. Se os organizadores da reunião tiverem anexado algum conteúdo às reuniões antecipadamente, será necessário recriar esse conteúdo após a execução do MMS.
- O link para as notas da reunião compartilhada no item do calendário e na reunião do Skype também serão sobrescritos. Observe que as anotações de reunião reais armazenadas OneNote ainda estarão lá; é apenas o link para as anotações compartilhadas que é substituído.
- Reuniões com mais de 250 participantes (incluindo o organizador) não serão migradas.
- Alguns caracteres UNICODE no corpo do convite podem estar atualizados incorretamente para um dos seguintes caracteres especiais: ï, *, 1/2, .

## <a name="triggering-mms-for-a-user"></a>Disparando MMS para um usuário

Esta seção descreve o que acontece quando o MMS é disparado em cada um dos seguintes casos:

- Quando um usuário é migrado do local para a nuvem
- Quando um administrador faz uma alteração nas configurações de audioconferência do usuário
- Quando o modo do usuário no TeamsUpgradePolicy é definido como TeamsOnly ou SfBWithTeamsCollabAndMeetings (usando o Powershell ou o portal Teams Administração)
- Quando você usa o cmdlet do PowerShell, Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Atualizando reuniões quando você move um usuário local para a nuvem

Esse é o cenário mais comum em que o MMS ajuda a criar uma transição mais suave para seus usuários. Sem a migração de reunião, as reuniões existentes organizadas por um usuário no Skype for Business Server local não funcionariam mais quando o usuário fosse movido online. Portanto, quando você usa as ferramentas de administração local (`Move-CsUser`ou o Administração Painel de Controle) para mover um usuário para a nuvem, as reuniões existentes são movidas automaticamente para a nuvem e convertidas no TeamsOnly.

Se o usuário tiver sido atribuído a uma Audioconferência antes de ser movido para a nuvem, as reuniões serão criadas com coordenadas discadas. Se você mover um usuário do local para a nuvem e pretende que esse usuário use o Audioconferência, recomendamos que primeiro atribua a audioconferência antes de mover o usuário para que apenas uma migração de reunião seja disparada.

### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Atualizando reuniões quando as configurações de audioconferência de um usuário são alteradas

Nos casos a seguir, o MMS atualizará as Skype for Business e Microsoft Teams existentes para adicionar, remover ou modificar coordenadas discadas:

- Quando você atribui ou remove uma licença de serviço do Microsoft Audioconferência a um usuário e esse usuário não está habilitado para um provedor de serviços de audioconferência de terceiros.
- Quando você altera o provedor de audioconferência de um usuário de qualquer outro provedor para a Microsoft, desde que o usuário seja atribuído a uma licença do Microsoft Audioconferência. Para obter mais informações, consulte [Atribuir a Microsoft como o provedor de audioconferência](./assign-microsoft-as-the-audio-conferencing-provider.md). Observe também que o suporte para provedores de audioconferência de terceiros [ACP] está agendado para o fim da vida útil em 1º de abril de 2019, conforme anunciado [anteriormente](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md).
- Quando você habilita ou desabilita a audioconferência para um usuário.
- Quando você altera ou redefine a ID de conferência de um usuário configurado para usar reuniões públicas.
- Quando você move o usuário para uma nova ponte de audioconferência.
- Quando um número de telefone de uma ponte de audioconferência não é atribuído. Esse é um cenário complexo que requer etapas adicionais. Para obter mais informações, [consulte Alterar os números de telefone em sua ponte de audioconferência](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

Nem todas as alterações nas configurações de audioconferência de um usuário disparam MMS. Em particular, as duas alterações a seguir não resultarão na atualização das reuniões pelo MMS:

- Quando você altera o endereço SIP do organizador da reunião (o nome de usuário ou o domínio SIP)
- Quando você altera a URL da reunião da sua organização usando o `Update-CsTenantMeetingUrl` comando.

### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Atualizando reuniões ao atribuir TeamsUpgradePolicy

Por padrão, a migração de reunião é disparada automaticamente quando um usuário recebe uma instância com `TeamsUpgradePolicy` ou `mode= SfBWithTeamsCollabAndMeetings``mode=TeamsOnly` . Se você não quiser migrar reuniões ao conceder qualquer um desses modos, `MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy` especifique em (se estiver usando o PowerShell) ou desmarque a caixa para migrar reuniões ao definir o modo de coexistência do usuário (se estiver usando o portal de administração do Teams).

Observe também o seguinte:

- A migração de reunião só é invocada quando você concede `TeamsUpgradePolicy` para um usuário específico. Se você conceder com `TeamsUpgradePolicy` ou `mode=SfBWithTeamsCollabAndMeetings` `mode=TeamsOnly` *em todo* o locatário, a migração de reunião não será invocada.
- Um usuário só poderá receber o modo TeamsOnly se o usuário estiver hospedado online. Os usuários hospedados no local devem ser movidos usando-se `Move-CsUser` conforme descrito anteriormente.
- Conceder um modo diferente de TeamsOnly ou SfBWithTeamsCollabAndMeetings não converte reuniões Teams existentes em reuniões Skype for Business reuniões.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Disparar a migração de reunião manualmente por meio do cmdlet do PowerShell

Além das migrações automáticas de reunião, os administradores podem disparar manualmente a migração de reunião para um usuário executando o cmdlet `Start-CsExMeetingMigration`. Esse cmdlet enfileira uma solicitação de migração para o usuário especificado.  Além do parâmetro necessário `Identity` , ele usa dois parâmetros opcionais e `SourceMeetingType` `TargetMeetingType`, que permitem que você especifique como migrar reuniões:

**TargetMeetingType:**

- O `TargetMeetingType Current` uso especifica que Skype for Business reuniões permanecem Skype for Business reuniões e Teams reuniões permanecem Teams reuniões. No entanto, as coordenadas de audioconferência podem ser alteradas e qualquer reunião local Skype for Business reuniões seria migrada para o Skype for Business Online. Esse é o valor padrão para TargetMeetingType.
- O `TargetMeetingType Teams` uso especifica que qualquer reunião existente deve ser migrada para o Teams, independentemente de a reunião estar hospedada no Skype for Business online ou localmente e independentemente de qualquer atualização de audioconferência ser necessária.

**SourceMeetingType:**

- O `SourceMeetingType SfB` uso indica que somente Skype for Business reuniões (locais ou online) devem ser atualizadas.
- O `SourceMeetingType Teams` uso indica que apenas Teams reuniões devem ser atualizadas.
- Usar `SourceMeetingType All` indica que as reuniões Skype for Business e Teams reuniões devem ser atualizadas. Esse é o valor padrão para SourceMeetingType.

O exemplo a seguir mostra como iniciar a migração de reunião para usuários ashaw@contoso.com para que todas as reuniões sejam migradas para Teams:

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```

## <a name="managing-mms"></a>Gerenciando o MMS

Usando Windows PowerShell, você pode verificar o status das migrações em andamento, disparar manualmente a migração de reunião e desabilitar completamente a migração.

### <a name="check-the-status-of-meeting-migrations"></a>Verificar o status das migrações de reunião

Use o `Get-CsMeetingMigrationStatus` cmdlet para verificar o status das migrações de reunião. Abaixo estão alguns exemplos.

- Para obter um status de resumo de todas as migrações de MMS, execute o seguinte comando, que fornece uma exibição tabular de todos os estados de migração:

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed        2
    Succeeded   131
    ```

- Para obter detalhes completos de todas as migrações em um período de tempo específico, use os parâmetros `StartTime` `EndTime` e os parâmetros. Por exemplo, o comando a seguir retornará detalhes completos sobre todas as migrações que ocorreram de 1º de outubro de 2018 a 8 de outubro de 2018.

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```

- Para verificar o status da migração de um usuário específico, use o `Identity` parâmetro. Por exemplo, o comando a seguir retornará o status do usuário ashaw@contoso.com:

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```

Se você vir as migrações que falharam, execute uma ação para resolver esses problemas o mais rápido possível, pois as pessoas não poderão discar para as reuniões organizadas por esses usuários até que você os resolva. Se `Get-CsMeetingMigrationStatus` mostrar qualquer migração em um estado de falha, execute estas etapas:

1. Determine quais usuários são afetados. Execute o seguinte comando para obter a lista de usuários afetados e o erro específico que foi relatado:

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```

2. Para cada usuário afetado, examine o valor da propriedade LastMessage para determinar por que a migração de reunião falhou e qual ação corretiva deve ser tomada. Depois que a ação corretiva for executada, dispare novamente a migração de reunião para os usuários afetados, `Start-CsExMeetingMigration` usando o cmldet do PowerShell, conforme descrito acima.

3. Se a migração ainda não funcionar, você terá duas opções:

    - Fazer os usuários criarem novas reuniões do Skype.
    - [Contatar o suporte](/microsoft-365/Admin/contact-support-for-business-products).

O `Get-CsMeetingMigrationStatus` cmdlet pode ser usado para recuperar o status das migrações que foram disparadas nos últimos 150 dias. Registros para migrações com mais de 150 dias são limpos do sistema.

### <a name="enabling-and-disabling-mms"></a>Habilitando e desabilitando o MMS

O MMS é habilitado por padrão para todas as organizações, mas pode ser desabilitado da seguinte maneira:

- Desabilite totalmente para o locatário.
- Desabilite somente para alterações relacionadas à audioconferência. Nesse caso, o MMS ainda será executado quando um usuário for migrado do local para a nuvem ou quando você conceder o modo TeamsOnly ou o modo SfBWithTeamsCollabAndMeetings em `TeamsUpgradePolicy`.

Por exemplo, talvez você queira migrar manualmente todas as reuniões ou desabilitar temporariamente o MMS enquanto faz alterações substanciais nas configurações de audioconferência da sua organização

Para ver se o MMS está habilitado para sua organização, execute o comando a seguir. O MMS será habilitado se o `MeetingMigrationEnabled` parâmetro for `$true`.

```PowerShell
Get-CsTenantMigrationConfiguration
```

Se o MMS estiver habilitado na organização e você quiser verificar se ele está habilitado para atualizações de audioconferência, `AutomaticallyMigrateUserMeetings` verifique o valor do parâmetro na saída de `Get-CsOnlineDialInConferencingTenantSettings`. Para habilitar ou desabilitar o MMS para audioconferência, use `Set-CsOnlineDialInConferencingTenantSettings`. Por exemplo, para desabilitar o MMS para audioconferência, execute o seguinte comando:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Tópicos relacionados

[Experimente ou compre Audioconferência no Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Mover os usuários entre um ambiente local e a nuvem](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)
