---
title: Usando o serviço de migração de reunião (MMS)
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Serviço de migração (MMS) de reunião é um serviço executado em segundo plano e que é atualizado automaticamente Skype para reuniões de negócios e Teams da Microsoft para usuários. MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.
ms.openlocfilehash: 9a133cb2a91e50ad21b263009f8f2c64cd3d8ccb
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835115"
---
# <a name="using-the-meeting-migration-service-mms"></a>Usando o serviço de migração de reunião (MMS)

O serviço de migração de reunião (MMS) é um serviço que atualiza reuniões existentes de um usuário nos seguintes cenários:

- Quando um usuário é migrado do local para a nuvem (se Skype para Business Online ou TeamsOnly).
- Quando um administrador faz uma alteração para configurações de serviços de audioconferência do usuário 
- Quando um usuário online é atualizado ou quando o modo de um usuário no TeamsUpgradePolicy estiver definido como SfBwithTeamsCollabAndMeetings às equipes somente
- Quando você usar o PowerShell 


Por padrão, MMS é acionado automaticamente em cada um desses casos, embora os administradores podem desabilitá-lo no nível do locatário. Além disso, os administradores podem usar um cmdlet do PowerShell para disparar manualmente a migração de reunião para um determinado usuário.


**Limitações**: A reunião não pode ser usado o serviço de migração se qualquer uma das seguintes se aplicar:

- Caixa de correio do usuário está hospedada no Exchange local.
- O usuário está sendo migrado da nuvem para Skype para Business Server local.

Nesses casos, os usuários finais pode usar a [Ferramenta de migração de reunião](https://www.microsoft.com/en-us/download/details.aspx?id=51659) para migrar seus próprios reuniões em vez disso.

## <a name="how-mms-works"></a>Funcionamento do MMS

Quando o MMS é disparado para um determinado usuário, uma solicitação de migração para o usuário é colocada em uma fila. Para evitar qualquer condição de corrida, a solicitação na fila deliberadamente não é processada até que passou pelo menos de 90 minutos. Depois que o MMS processa a solicitação, ele executa as seguintes tarefas:

1. Ele pesquisa de caixa de correio desse usuário para todas as suas reuniões organizadas pelo usuário e agendada no futuro.
2. Com base nas informações encontradas na caixa de correio do usuário, ele ou atualiza ou agenda novas reuniões em equipes ou Skype para Business Online para esse usuário, dependendo do cenário exato.
3. Na mensagem de email, ele substitui o bloco de reunião online nos detalhes da reunião.
4. Ele envia a versão atualizada dessa reunião para todos os destinatários de reunião em nome do organizador da reunião. Os convidados da reunião, você receberá uma atualização de reunião com as coordenadas de reunião atualizadas em seus emails. 

    ![O bloco de reuniões que são atualizadas pelo MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

Desde o momento em que é disparado MMS, que geralmente leva cerca de 2 horas até que as reuniões do usuário são migrados. No entanto, se o usuário tiver um grande número de reuniões, pode levar mais tempo. Se MMS encontra um erro migrando de uma ou mais reuniões para o usuário, ele tentará periodicamente até 9 vezes sobre o período de 24 horas.

**Observações**:

- O MMS substitui todo o bloco de informações da reunião online durante a migração da reunião. Portanto, se o usuário editou esse bloco, essas alterações serão substituídas. O conteúdo dos detalhes da reunião que estiver fora do bloco de informações da reunião online não será afetado.
- Somente o Skype para reuniões de negócios ou Teams da Microsoft que foram agendadas clicando no botão **Adicionar Skype reunião** no Outlook na Web, ou usando o suplemento de reunião Skype para Outlook são migradas. Se um usuário copia e cola as informações de reunião online do Skype de uma reunião para uma nova reunião, essa nova reunião não será atualizado como não há nenhuma reunião no serviço original.
- Conteúdo que foi criado ou anexado à solicitação de reunião (quadros de comunicações, votações e assim por diante) da reunião não será mantida após a execução do MMS. Se os organizadores da reunião tiverem anexado algum conteúdo às reuniões antecipadamente, será necessário recriar esse conteúdo após a execução do MMS.
- O link para as notas da reunião compartilhada no item do calendário e na reunião do Skype também serão sobrescritos. Observe que as notas de reunião real armazenadas no OneNote ainda ser lá; é somente o link para as anotações compartilhadas que será substituído.
- Reuniões com mais de 250 participantes (incluindo o organizador) não serão migradas.
- Alguns caracteres UNICODE no corpo do convite podem ser atualizados incorretamente como um dos seguintes caracteres especiais: ï, ¿, ½,.

## <a name="triggering-mms-for-a-user"></a>Disparando MMS para um usuário

Esta seção descreve o que acontece quando MMS é disparado em cada um dos seguintes casos:

- Quando um usuário é migrado do local para a nuvem
- Quando um administrador faz uma alteração para configurações de serviços de audioconferência do usuário 
- Quando o modo do usuário no TeamsUpgradePolicy estiver definido como TeamsOnly ou SfBWithTeamsCollabAndMeetings (usando o Powershell ou do Portal de administração de equipes)
- Quando você usa o cmdlet do PowerShell, Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Atualizando reuniões quando você mover um usuário local para a nuvem

Esse é o cenário mais comum onde o MMS ajuda a criar uma transição mais suave para seus usuários. Sem migração de reunião, existentes reuniões organizadas por um usuário no Skype para Business Server local não é mais funcionaria depois que o usuário é movido online. Portanto, quando você usar as ferramentas de administração de local (tanto `Move-CsUser` ou do painel de controle do Admin) para mover um usuário para a nuvem, reuniões existentes são movidas automaticamente para a nuvem da seguinte maneira:

- Se o `MoveToTeams` alternar no `Move-CsUser` for especificado, reuniões são migrados diretamente para as equipes e o usuário estará no modo de TeamsOnly. Uso desta opção requer Skype para Business Server com CU8 ou posterior. Esses usuários ainda poderão ingressar qualquer Skype para reunião de negócios, que eles podem ser convidados, usando o Skype para o cliente de negócios ou o aplicativo de reunião do Skype.
- Caso contrário, reuniões são migradas para Skype para negócios Online.

Em ambos os casos, se o usuário tenha sido atribuído uma licença de conferência de áudio antes que está sendo movido para a nuvem, as reuniões serão criadas com as coordenadas de discagem. Se você mover um usuário no local para a nuvem e você pretende que esse usuário utilize a conferência de áudio, é recomendável que você atribua primeiro na audioconferência antes de mover o usuário para que a migração de reunião somente 1 é disparada.


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Atualizando reuniões quando alteram as configurações de serviços de audioconferência do usuário

Nos seguintes casos, MMS atualizará Skype existente para reuniões de negócios e Teams da Microsoft para adicionar, remover ou modificar as coordenadas de discagem:

- Quando você atribuir ou remove uma licença de serviço de conferência de áudio da Microsoft para um usuário e que o usuário não está habilitado para um provedor de serviços de audioconferência de terceiros.
- Quando você alterar o provedor de serviços de audioconferência de um usuário de qualquer outro provedor para fornecido pela Microsoft, o usuário é atribuído a uma licença de conferência de áudio da Microsoft. Para obter mais informações, consulte [Microsoft atribuir como um provedor de serviços de audioconferência](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider). Observe também que suporte para provedores de serviços de audioconferência de terceiros [ACP] está programado para o fim da vida útil em 1 de abril de 2019, como [anunciado anteriormente](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers).
- Quando você habilitar ou desabilitar os serviços de audioconferência para um usuário.
- Quando você alterar ou reiniciar o ID de conferência para um usuário configurado para usar as reuniões públicas.
- Quando você move o usuário para uma nova ponte de conferência de áudio.
- Quando um número de telefone de uma ponte de conferência de áudio é não atribuído. Esse é um cenário complexo que requer etapas adicionais. Para obter mais informações, consulte [alterar os números de telefone na sua ponte de conferência de áudio](https://docs.microsoft.com/en-us/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

Nem todas as alterações nas configurações de conferência de áudio de um usuário disparam MMS. Em particular, as duas alterações a seguir não resultarão na atualização das reuniões pelo MMS:

- Quando você altera o endereço SIP do organizador da reunião (o nome de usuário ou o domínio SIP)
- Quando você altera sua organização da reunião usando o URL do `Update-CsTenantMeetingUrl` comando.


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Atualizando reuniões ao atribuir TeamsUpgradePolicy

Por padrão, migração de reunião é acionada automaticamente quando um usuário recebe uma instância de `TeamsUpgradePolicy` com `mode=TeamsOnly` ou `mode= SfBWithTeamsCollabAndMeetings`. Se você não deseja migrar reuniões quando a concessão de ambos os modos, em seguida, especifique `MigrateMeetingsToTeams $false` na `Grant-CsTeamsUpgradePolicy` (se estiver usando o PowerShell) ou desmarque a caixa para migrar reuniões quando a definição de modo de coexistência de um usuário (se estiver usando o portal de administração de equipes).

Também observe o seguinte:

- Migração de reunião é invocada apenas quando você concede `TeamsUpgradePolicy` para um usuário específico. Se você conceder `TeamsUpgradePolicy` com `mode=TeamsOnly` ou `mode=SfBWithTeamsCollabAndMeetings` em uma base de *todo o locatário* , migração da reunião não é invocada.
- Um usuário só pode ser concedido TeamsOnly modo se o usuário está hospedado online. Usuários que estão hospedados no local que devem ser movidos usando `Move-CsUser` conforme descrito anteriormente.
- Conceder um modo diferente TeamsOnly ou SfBWithTeamsCollabAndMeetings não converter reuniões existentes de equipes Skype para reuniões de negócios.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Migração de reunião de gatilho manualmente por meio do cmdlet do PowerShell

Além das migrações de reunião automáticos, admins pode disparar manualmente a migração de reunião para um usuário executando o cmdlet `Start-CsExMeetingMigration`. Este cmdlet enfileira uma solicitação de migração para o usuário especificado.  Além das required `Identity` parâmetro, que leva dois parâmetros opcionais, `SourceMeetingType` e `TargetMeetingType`, que permitem que você especifique como migrar reuniões:

**TargetMeetingType:**

- Usando `TargetMeetingType Current` Especifica que Skype para reuniões de negócios permanecem Skype para reuniões de negócios e reuniões de equipes permanecem reuniões de equipes. No entanto audioconferência coordena pode ser alterado e Skype qualquer local para reuniões de negócios seria migrado para Skype para negócios Online. Este é o valor padrão para TargetMeetingType.
- Usando `TargetMeetingType Teams` Especifica que qualquer reunião existente deve ser migrado para equipes, independentemente se a reunião está hospedada no Skype para negócios online ou local e independentemente se quaisquer atualizações de serviços de audioconferência são necessárias. 

**SourceMeetingType:**
- Usando `SourceMeetingType SfB` indica que Skype apenas para reuniões de negócios (se local ou online) devem ser atualizados.
- Usando `SourceMeetingType Teams` indica que as reuniões de equipes só deverá ser atualizadas.
- Usando `SourceMeetingType All` indica que os dois Skyep para reuniões de negócios e reuniões de equipes deve ser atualizado. Este é o valor padrão para SourceMeetingType.
    

O exemplo a seguir mostra como iniciar a migração de reunião para o usuário ashaw@contoso.com para que todas as reuniões são migradas para as equipes:

```
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>Gerenciando o MMS

Usando o Windows PowerShell, você pode verificar o status das migrações em andamento, manualmente disparar a migração de reunião e desabilitar a migração totalmente. 

### <a name="check-the-status-of-meeting-migrations"></a>Verificar o status de migrações de reunião

Você usa o `Get-CsMeetingMigrationStatus` cmdlet para verificar o status de migrações de reunião. Abaixo estão alguns exemplos.

- Para obter um status de resumo de todas as migrações do MMS, execute o seguinte comando que fornece uma exibição tabular de todos os estados de migração:

    ```
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- Para obter detalhes completos de todas as migrações dentro de um período de tempo específico, use o `StartTime` e `EndTime` parâmetros. Por exemplo, o comando a seguir retornará detalhes completos sobre todas as migrações que ocorreu a partir de 1 de outubro de 2018 para 8 de outubro de 2018.

    ```
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- Para verificar o status da migração para um usuário específico, use o `Identity` parâmetro. Por exemplo, o comando a seguir retornará o status de ashaw@contoso.com o usuário:

    ```
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
Se você vir qualquer migrações que falharam, execute a ação para resolver esses problemas assim que possível, desde que as pessoas não conseguirá dial-in para as reuniões organizadas por esses usuários até que você resolvê-los. Se `Get-CsMeetingMigrationStatus` mostra qualquer migrações em estado falho, execute estas etapas:
 
1. Determine quais usuários são afetados. Execute o seguinte comando para obter a lista de usuários afetados e o erro específico que foi relatado:

    ```
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table Identity, LastMessage
    ```
2. Para cada usuário afetado, execute a ferramenta de migração de reunião para migrar manualmente suas reuniões.

3. Se a migração com a ferramenta de migração de reuniões também não funcionar, você terá duas opções:

    - Fazer os usuários criarem novas reuniões do Skype.
    - [Contatar o suporte](https://go.microsoft.com/fwlink/p/?LinkID=518322).


### <a name="enabling-and-disabling-mms"></a>Habilitando e desabilitando o MMS

MMS é habilitado por padrão para todas as organizações, mas pode ser desativado da seguinte maneira:

- Desabilite inteiramente para o inquilino. 
- Desabilite apenas para as alterações relacionadas a conferências de áudio. Nesse caso, MMS ainda será executado quando um usuário é migrado do local para a nuvem ou quando você concede o modo de TeamsOnly ou SfBWithTeamsCollabAndMeetings em `TeamsUpgradePolicy`.

Por exemplo, você talvez queira migrar todas as reuniões manualmente ou desabilitar temporariamente MMS enquanto faz alterações substanciais as configurações de serviços de audioconferência para sua organização

Para ver se MMS está habilitado para sua organização, execute o seguinte comando. MMS estará habilitado se o `MeetingMigrationEnabled` parâmetro é `$true`.
```
Get-CsTenantMigrationConfiguration
```
Para habilitar ou desabilitar MMS totalmente, use o `Set-CsTenantMigrationConfiguration` comando. Por exemplo, para desabilitar MMS, execute o seguinte comando:

```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
Se MMS estiver habilitado na organização e você deseja verificar se ele está habilitado para atualizações de conferência de áudio, verifique o valor do `AutomaticallyMigrateUserMeetings` parâmetro na saída do `Get-CsOnlineDialInConferencingTenantSettings`. Para habilitar ou desabilitar MMS para conferência de áudio, use `Set-CsOnlineDialInConferencingTenantSettings`. Por exemplo, para desativar MMS para conferência de áudio, execute o seguinte comando:

```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Mover usuários entre locais e em nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
