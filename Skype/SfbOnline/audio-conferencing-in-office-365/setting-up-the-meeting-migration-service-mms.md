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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: O Meeting Migration Service (MMS) é um serviço executado em segundo plano e atualiza automaticamente as reuniões do Skype for Business e do Microsoft Teams para usuários. MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.
ms.openlocfilehash: 9223102ef9c264fdafdb9f52ec74d6edb383f987
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47765343"
---
# <a name="using-the-meeting-migration-service-mms"></a>Usando o Meeting Migration Service (MMS)

O MMS (Meeting Migration Service) é um serviço que atualiza as reuniões existentes de um usuário nos seguintes cenários:

- Quando um usuário é migrado do local para a nuvem (seja para o Skype for Business Online ou para o TeamsOnly).
- Quando um administrador faz uma alteração nas configurações de audioconferência do usuário 
- Quando um usuário online é atualizado apenas para o Teams ou quando o modo do usuário no TeamsUpgradePolicy é definido como SfBwithTeamsCollabAndMeetings
- Quando você usa o PowerShell 


Por padrão, o MMS é disparado automaticamente em cada um desses casos, embora os administradores possam desabilitá-lo no nível do locatário. Além disso, os administradores podem usar um cmdlet do PowerShell para disparar manualmente a migração de reunião para um determinado usuário.


**Limitações:** o serviço de migração de reunião não poderá ser usado se qualquer uma das seguintes se aplicar:

- A caixa de correio do usuário está hospedada no Exchange local.
- O usuário está sendo migrado da nuvem para o Skype for Business Server local.

Nessas situações, os usuários finais podem usar a Ferramenta de Migração [de](https://www.microsoft.com/download/details.aspx?id=51659) Reunião para migrar suas próprias reuniões.

## <a name="how-mms-works"></a>Como o MMS funciona

Quando o MMS é disparado para um determinado usuário, uma solicitação de migração para esse usuário é colocada em uma fila. Para evitar quaisquer condições de corrida, a solicitação enluada não é processada deliberadamente até que pelo menos 90 minutos tenham passado. Depois que o MMS processa a solicitação, ele executa as seguintes tarefas:

1. Ele pesquisa a caixa de correio do usuário para todas as reuniões existentes organizadas por esse usuário e agendadas no futuro.
2. Com base nas informações encontradas na caixa de correio do usuário, ela atualiza ou agenda novas reuniões no Teams ou no Skype for Business Online para esse usuário, dependendo do cenário exato.
3. Na mensagem de email, ela substitui o bloco de reunião online nos detalhes da reunião.
4. Ele envia a versão atualizada dessa reunião para todos os destinatários da reunião em nome do organizador da reunião. Os convidados da reunião receberão uma atualização de reunião com coordenadas de reunião atualizadas em seus emails. 

    ![O bloco de reuniões que são atualizadas pelo MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

A partir do momento em que o MMS é disparado, normalmente leva cerca de 2 horas até que as reuniões do usuário sejam migradas. No entanto, se o usuário tiver um grande número de reuniões, pode demorar mais. Se o MMS encontrar um erro migrando uma ou mais reuniões para o usuário, ele repetirá periodicamente até 9 vezes no intervalo de 24 horas.

**Observações:**

- O MMS substitui todo o bloco de informações da reunião online durante a migração da reunião. Portanto, se o usuário editou esse bloco, essas alterações serão substituídas. O conteúdo dos detalhes da reunião que estiver fora do bloco de informações da reunião online não será afetado. Isso significa que todos os arquivos anexados ao convite da reunião ainda serão incluídos. 
- Somente as reuniões do Skype for Business ou do Microsoft Teams que foram agendadas clicando no botão Adicionar reunião do **Skype** no Outlook na Web ou usando o complemento Reunião do Skype para Outlook são migradas. Se um usuário copia e colar as informações da reunião online do Skype de uma reunião para uma nova reunião, essa nova reunião não será atualizada porque não há nenhuma reunião no serviço original.
- O conteúdo da reunião que foi criado ou anexado à reunião (whiteboards, votações e assim por diante) não será retido depois que o MMS é executado. Se os organizadores da reunião tiverem anexado algum conteúdo às reuniões antecipadamente, será necessário recriar esse conteúdo após a execução do MMS.
- O link para as notas da reunião compartilhada no item do calendário e na reunião do Skype também serão sobrescritos. Observe que as anotações reais da reunião armazenadas no OneNote ainda estarão lá; é apenas o link para as anotações compartilhadas que é substituído.
- Reuniões com mais de 250 participantes (incluindo o organizador) não serão migradas.
- Alguns caracteres UNICODE no corpo do convite podem ser atualizados incorretamente para um dos seguintes caracteres especiais: ï, ?, 1/2, .

## <a name="triggering-mms-for-a-user"></a>Acionando o MMS para um usuário

Esta seção descreve o que acontece quando o MMS é disparado em cada um dos seguintes casos:

- Quando um usuário é migrado do local para a nuvem
- Quando um administrador faz uma alteração nas configurações de audioconferência do usuário 
- Quando o modo do usuário no TeamsUpgradePolicy está definido como TeamsOnly ou SfBWithTeamsCollabAndMeetings (usando o Powershell ou o Portal de Administração do Teams)
- Quando você usa o cmdlet do PowerShell, Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Atualizando reuniões quando você move um usuário local para a nuvem

Esse é o cenário mais comum em que o MMS ajuda a criar uma transição mais suave para os usuários. Sem a migração de reuniões, as reuniões existentes organizadas por um usuário no Skype for Business Server local não funcionariam mais quando o usuário fosse movido online. Portanto, quando você usa as ferramentas de administração local (ou o Painel de Controle de Administração) para mover um usuário para a nuvem, as reuniões existentes são movidas automaticamente para a nuvem da `Move-CsUser` seguinte forma:

- Se a mudança for especificada, as reuniões serão migradas diretamente para o Teams e o usuário estará no modo `MoveToTeams` `Move-CsUser` TeamsOnly. O uso dessa opção requer o Skype for Business Server 2015 com CU8 ou posterior. Esses usuários ainda podem ingressar em qualquer reunião do Skype for Business para a que possam ser convidados, usando o cliente Skype for Business ou o Aplicativo de Reunião do Skype.
- Caso contrário, as reuniões serão migradas para o Skype for Business Online.

Em ambos os casos, se o usuário recebeu uma licença de Audioconferência antes de ser movido para a nuvem, as reuniões serão criadas com coordenadas discadas. Se você mover um usuário do local para a nuvem e pretende que esse usuário use a Audioconferência, recomendamos que primeiro atribua a audioconferência antes de mover o usuário para que apenas uma migração de reunião seja disparada.


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Atualizando reuniões quando as configurações de audioconferência de um usuário mudam

Nos casos a seguir, o MMS atualizará as reuniões existentes do Skype for Business e do Microsoft Teams para adicionar, remover ou modificar coordenadas de discagem:

- Quando você atribui ou remove uma licença de serviço de Audioconferência da Microsoft a um usuário e esse usuário não está habilitado para um provedor de serviços de audioconferência de terceiros.
- Quando você altera o provedor de audioconferência de um usuário de qualquer outro provedor para a Microsoft, desde que o usuário recebe uma licença de Audioconferência da Microsoft. Para obter mais informações, consulte [Atribuir a Microsoft como provedor de serviços de audioconferência.](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider) Observe também que o suporte para provedores de audioconferência de terceiros [ACP] está agendado para o fim da vida útil em 1º de abril de 2019, conforme anunciado [anteriormente.](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers)
- Quando você habilita ou desabilita a audioconferência de um usuário.
- Quando você altera ou redefine a ID de conferência de um usuário configurado para usar reuniões públicas.
- Quando você move o usuário para uma nova ponte de audioconferência.
- Quando um número de telefone de uma ponte de audioconferência não é atribuído. Esse é um cenário complexo que requer etapas adicionais. Para obter mais informações, [consulte Alterar os números de telefone em sua ponte de audioconferência.](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)

Nem todas as alterações nas configurações de audioconferência de um usuário acionam o MMS. Em particular, as duas alterações a seguir não resultarão na atualização das reuniões pelo MMS:

- Quando você altera o endereço SIP do organizador da reunião (o nome de usuário ou o domínio SIP)
- Quando você altera a URL da reunião da sua organização usando o `Update-CsTenantMeetingUrl` comando.


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Atualizando reuniões ao atribuir o TeamsUpgradePolicy

Por padrão, a migração de reunião é disparada automaticamente quando um usuário é concedido uma instância `TeamsUpgradePolicy` de com `mode=TeamsOnly` ou `mode= SfBWithTeamsCollabAndMeetings` . Se você não quiser migrar reuniões ao conceder um desses modos, especifique (se estiver usando o PowerShell) ou desmarque a caixa para migrar reuniões ao definir o modo de coexistência do usuário (se estiver usando o portal de administração do `MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy` Teams).

Observe também o seguinte:

- A migração de reunião só é revogada quando você `TeamsUpgradePolicy` concede a um usuário específico. Se você conceder com ou sem locatário, a migração de `TeamsUpgradePolicy` `mode=TeamsOnly` reunião não será `mode=SfBWithTeamsCollabAndMeetings` revogada. 
- Um usuário só poderá ser concedido ao modo TeamsOnly se o usuário estiver online. Os usuários que estão no local devem ser movidos usando `Move-CsUser` conforme descrito anteriormente.
- Conceder um modo diferente do TeamsOnly ou SfBWithTeamsCollabAndMeetings não converte reuniões existentes do Teams em reuniões do Skype for Business.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Disparar Migração de Reunião manualmente por meio do cmdlet do PowerShell

Além das migrações automáticas de reunião, os administradores podem disparar manualmente a migração de reunião para um usuário executando o `Start-CsExMeetingMigration` cmdlet. Esse cmdlet enfileira uma solicitação de migração para o usuário especificado.  Além do parâmetro necessário, são necessários dois parâmetros opcionais e, que permitem especificar como `Identity` `SourceMeetingType` `TargetMeetingType` migrar reuniões:

**TargetMeetingType:**

- O `TargetMeetingType Current` uso especifica que as reuniões do Skype for Business permanecem reuniões do Skype for Business e as reuniões do Teams permanecem reuniões do Teams. No entanto, as coordenadas de audioconferência podem ser alteradas e qualquer reunião local do Skype for Business seria migrada para o Skype for Business Online. Esse é o valor padrão para TargetMeetingType.
- O uso especifica que qualquer reunião existente deve ser migrada para o Teams, independentemente de a reunião estar hospedada no Skype for Business online ou local e independentemente de qualquer atualização de audioconferência ser `TargetMeetingType Teams` necessária. 

**SourceMeetingType:**
- O `SourceMeetingType SfB` uso indica que somente reuniões do Skype for Business (locais ou online) devem ser atualizadas.
- O `SourceMeetingType Teams` uso indica que somente as reuniões do Teams devem ser atualizadas.
- O `SourceMeetingType All` uso indica que as reuniões do Skype for Business e as reuniões do Teams devem ser atualizadas. Esse é o valor padrão para SourceMeetingType.
    

O exemplo a seguir mostra como iniciar a migração de reunião para usuários ashaw@contoso.com para que todas as reuniões sejam migradas para o Teams:

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>Gerenciando o MMS

Usando o Windows PowerShell, você pode verificar o status das migrações em andamento, acionar manualmente a migração de reunião e desabilitar completamente a migração. 

### <a name="check-the-status-of-meeting-migrations"></a>Verificar o status das migrações de reunião

Use o `Get-CsMeetingMigrationStatus` cmdlet para verificar o status das migrações de reunião. Veja a seguir alguns exemplos.

- Para obter um status de resumo de todas as migrações de MMS, execute o seguinte comando que fornece uma exibição tabular de todos os estados de migração:

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- Para obter detalhes completos de todas as migrações dentro de um período específico, use os `StartTime` `EndTime` parâmetros e os parâmetros. Por exemplo, o comando a seguir retornará detalhes completos sobre todas as migrações que ocorreram de 1º de outubro de 2018 a 8 de outubro de 2018.

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- Para verificar o status da migração de um usuário específico, use o `Identity` parâmetro. Por exemplo, o comando a seguir retornará o status do usuário ashaw@contoso.com:

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
Se você vir migrações que falharam, tome medidas para resolver esses problemas assim que possível, uma vez que as pessoas não poderão discar para as reuniões organizadas por esses usuários até que você os resolva. Se `Get-CsMeetingMigrationStatus` mostrar qualquer migração em um estado com falha, execute estas etapas:
 
1. Determine quais usuários serão afetados. Execute o seguinte comando para obter a lista de usuários afetados e o erro específico que foi relatado:

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. Para cada usuário afetado, execute a Ferramenta de Migração de Reunião para migrar manualmente suas reuniões.

3. Se a migração com a ferramenta de migração de reuniões também não funcionar, você terá duas opções:

    - Fazer os usuários criarem novas reuniões do Skype.
    - [Contatar o suporte](https://go.microsoft.com/fwlink/p/?LinkID=518322).


### <a name="enabling-and-disabling-mms"></a>Habilitando e desabilitando o MMS

O MMS é habilitado por padrão para todas as organizações, mas pode ser desabilitado da seguinte forma:

- Desabilitar totalmente para o locatário. 
- Desabilitar somente para alterações relacionadas à audioconferência. Nesse caso, o MMS ainda será executado quando um usuário for migrado do local para a nuvem ou quando você conceder o modo TeamsOnly ou o modo SfBWithTeamsCollabAndMeetings em `TeamsUpgradePolicy` .

Por exemplo, talvez você queira migrar manualmente todas as reuniões ou desabilitar temporariamente o MMS enquanto faz alterações substanciais nas configurações de audioconferência da sua organização

Para ver se o MMS está habilitado para sua organização, execute o seguinte comando. O MMS está habilitado se o `MeetingMigrationEnabled` parâmetro for `$true` .
```PowerShell
Get-CsTenantMigrationConfiguration
```
Para habilitar ou desabilitar totalmente o MMS, use o `Set-CsTenantMigrationConfiguration` comando. Por exemplo, para desabilitar o MMS, execute o seguinte comando:

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
Se o MMS estiver habilitado na organização e você quiser verificar se ele está habilitado para atualizações de audioconferência, verifique o valor do parâmetro na saída `AutomaticallyMigrateUserMeetings` de `Get-CsOnlineDialInConferencingTenantSettings` . Para habilitar ou desabilitar o MMS para audioconferência, `Set-CsOnlineDialInConferencingTenantSettings` use. Por exemplo, para desabilitar o MMS para audioconferência, execute o seguinte comando:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar Audioconferência no Microsoft 365 ou no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Mover os usuários entre um ambiente local e a nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
