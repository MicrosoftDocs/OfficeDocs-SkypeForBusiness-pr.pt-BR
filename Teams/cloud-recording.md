---
title: Gravação de reuniões na nuvem do Microsoft Teams
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
ms.reviewer: nakulm
search.appverid: MET150
f1.keywords:
- NOCSH
description: Orientação prática para a implantação de recursos de voz na nuvem no Teams para gravar reuniões de equipes e chamadas em grupo para capturar a atividade de compartilhamento de áudio, vídeo e tela.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 40fad38d8c77d8194d2bf24a451fb9438f10c586
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918967"
---
# <a name="teams-cloud-meeting-recording"></a>Gravação de reuniões na nuvem do Microsoft Teams

No Microsoft Teams, os usuários podem gravar reuniões e chamadas de grupo do Teams para capturar atividades de áudio, vídeo e compartilhamento de tela. Há também uma opção para habilitar a transcrição automática nas gravações. Com isso, os usuários podem reproduzir gravações de reunião com legendas ocultas e procurar itens de discussão importantes na transcrição. A gravação ocorre na nuvem e é salva no [Microsoft Stream](https://docs.microsoft.com/stream/), para que os usuários possam compartilhá-la com segurança na organização.

Relacionados: [documentação da solicitação de reunião do usuário final](https://aka.ms/recordmeeting)

>[!Note]
> A mudança do Microsoft Stream para o [Microsoft OneDrive for Business e o Microsoft Office SharePoint Online para gravações de reunião](tmr-meeting-recording-change.md) será uma abordagem em fases. No lançamento você poderá optar por aceitar essa experiência, em novembro você terá que recusar se quiser continuar usando o Stream e, no início de 2021, exigiremos que todos os clientes usem o OneDrive for Business e o Microsoft Office SharePoint Online para gravações de reunião.

> [!NOTE]
> Para obter informações sobre como usar funções em reuniões do Teams e como alterar as funções dos usuários, consulte [funções em uma reunião do teams](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Pré-requisitos para a gravação na nuvem do Teams

Para que as reuniões de um usuário do Team sejam gravadas, o Microsoft Stream deve ser habilitado para o locatário. Além disso, os pré-requisitos a seguir são necessários para o organizador da reunião e para a pessoa que está iniciando a gravação:

- O usuário tem o Office 365 E1, E3, e5, a1, a3, a5, Microsoft 365 Business Premium, Business Standard ou Business<sup>1</sup>
- O usuário consentiu com as diretrizes da empresa, se configurado pelo administrador
- O usuário tem armazenamento suficiente no Microsoft Stream para que as gravações sejam salvas
- O usuário tem a configuração CsTeamsMeetingPolicy-AllowCloudRecording definida como true para gravar reuniões e chamadas em grupo
- O usuário tem a configuração CsTeamsCallingPolicy-AllowCloudRecordingForCalls definida como true para gravar chamadas do 1:1
- O usuário não é um usuário anônimo, convidado ou federado na reunião
- Para habilitar a transcrição para a reunião de um usuário, a política de reunião do teams ao qual ele está atribuído deve ter a configuração-AllowTranscription definida como true.

<sup>1</sup> desde 20 de agosto de 2020, o acesso ao arquivo de gravação da reunião vencerá após 21 dias para os usuários com o a1. Para obter mais informações, consulte [carregar uma gravação de reunião do Microsoft Teams para Stream](https://docs.microsoft.com/stream/portal-upload-teams-meeting-recording).

> [!IMPORTANT] 
> Os usuários não precisarão de uma licença do Microsoft Stream atribuída se você quiser que somente registrem e baixem as gravações. Isso significa que as gravações não são armazenadas no Microsoft Stream, mas, em vez disso, são armazenadas em serviços de mídia assíncronas (AMS) com um limite de 21 dias antes de serem excluídas. Não é algo neste ponto que um administrador pode controlar ou gerenciar o, incluindo a capacidade de excluí-lo.

> [!IMPORTANT]
> Observe também que, para gravações no AMS, a retenção de gravação é afetada pela mensagem de chat em si. Dessa forma, qualquer exclusão da mensagem de chat original de gravação do AMS impedirá que os usuários acessem a gravação. Há dois cenários que podem afetar isso. 1) o usuário exclui manualmente a mensagem de chat-nesse cenário, pois a mensagem original é desativada, os usuários não poderão acessar a gravação e não será possível fazer mais downloads. No entanto, a gravação pode ainda ser mantida dentro dos sistemas internos da Microsoft por um tempo (não excedendo o período original de 21 dias). 2) a mensagem de chat de gravação é excluída pela política de retenção de chat – as gravações do AMS estão diretamente associadas à política de retenção de chat. Assim, embora as gravações no AMS sejam mantidas por padrão por 21 dias antes de serem excluídas, se a mensagem de chat for excluída antes do período de 21 dia, devido a políticas de retenção de mensagens de chat, a gravação também será excluída. Não há nenhuma maneira de recuperar a gravação após isso.

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Configurar a gravação na nuvem do Teams para usuários em sua organização

Esta seção explica como você pode configurar e planejar a gravação de reuniões do Teams.

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>Ativar o Microsoft Stream para usuários na organização

O Microsoft Stream está disponível como parte das assinaturas qualificadas do Microsoft 365 e do Office 365 ou como um serviço autônomo.  Confira [Visão geral de licenciamento Stream](https://docs.microsoft.com/stream/license-overview) para obter mais detalhes.  O Microsoft Stream agora está incluído no Microsoft 365 Business, no Microsoft 365 Business Standard e no Microsoft 365 Business Basic.

Saiba mais sobre como você pode [atribuir licenças a usuários no Microsoft 365 ou no Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) para que os usuários possam acessar o Microsoft Stream. Certifique-se de que o Microsoft Stream não seja bloqueado para os usuários, conforme definido nas [entradas de bloco para o Microsoft Stream](https://docs.microsoft.com/stream/disable-user-organization).

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>Certifique-se de que os usuários tenham permissões de carregamento de vídeo no Microsoft Stream

Por padrão, todas as pessoas da empresa podem criar conteúdo no fluxo, já que o fluxo está habilitado e a licença é atribuída ao usuário. Um administrador de fluxo da Microsoft pode [restringir funcionários para a criação de conteúdo no Stream](https://docs.microsoft.com/stream/restrict-uploaders). Os usuários que estiverem nesta lista restrita não poderão gravar reuniões.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Notifique os funcionários sobre o consentimento das diretrizes da empresa no Microsoft Stream

Se um administrador de Stream da Microsoft [configurou a política de diretrizes da empresa](https://docs.microsoft.com/stream/company-policy-and-consent) e exige que os funcionários aceitem essa política antes de salvar o conteúdo, os usuários devem fazê-lo antes de gravar no Microsoft Teams. Antes de distribuir o recurso de gravação na organização, certifique-se de que os usuários tenham consentido com a política.

### <a name="turn-on-or-turn-off-cloud-recording"></a>Ativar ou desativar a gravação na nuvem

Você pode usar o centro de administração do Microsoft Teams ou o PowerShell para definir uma política de reunião do Teams para controlar a gravação das reuniões do usuário.

No centro de administração do Microsoft Teams, habilite ou desabilite a configuração **Permitir gravação na nuvem** na política de reunião. Para saber mais, confira o artigo [Gerenciar políticas de reunião no Teams](meeting-policies-in-teams.md#allow-cloud-recording).

Usando o PowerShell, você define a configuração AllowCloudRecording no TeamsMeetingPolicy. Para saber mais, confira [New–CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) e [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

Observe que o organizador da reunião e o iniciador de gravação precisam ter permissões de gravação para gravar a reunião. A menos que você tenha atribuído uma política personalizada aos usuários, os usuários obtêm a política global, que tem o AllowCloudRecording habilitado por padrão.

> [!NOTE]
> Para obter mais informações sobre como usar funções do teams para configurar quem tem permissão para gravar uma reunião, consulte [funções em uma reunião do teams](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

Para que um usuário retorne à política global, use o cmdlet a seguir para remover uma atribuição de política específica para um usuário:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Para alterar o valor de AllowCloudRecording na política global, use o seguinte cmdlet:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false
```
</br>
</br>


|                                                                 Cenário                                                                 |                                                                                                                                                                         Etapas                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    Quero que todos os usuários da empresa possam gravar as reuniões                                    |                                                                     <ol><li>Confirme que o CsTeamsMeetingPolicy global tenha AllowCloudRecording = verdadeiro<li>Todos os usuários têm as CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com AllowCloudRecording = verdadeiro </ol>                                                                     |
| Quero que a maioria dos meus usuários consiga gravar as reuniões, mas desabilitar seletivamente usuários específicos que não têm permissão para gravar |        <ol><li>Confirm GlobalCsTeamsMeetingPolicy tem AllowCloudRecording = true<li>A maioria dos usuários têm as CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com AllowCloudRecording = verdadeiro<li>Todos os outros usuários receberam uma das políticas de CsTeamsMeetingPolicy com o AllowCloudRecording = false</ol>         |
|                                                   Eu quero que a gravação seja 100% desabilitada                                                   |                                                                <ol><li>Confirme que o CsTeamsMeetingPolicy global tem AllowCloudRecording = false<li>Todos os usuários receberam CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com AllowCloudRecording = falso                                                                 |
|      Desejo que a gravação seja desativada para a maioria dos usuários, mas habilitar seletivamente usuários específicos que têm permissão para gravar       | <ol><li>Confirme que o CsTeamsMeetingPolicy global tem AllowCloudRecording = false<li>A maioria dos usuários receberam CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com AllowCloudRecording = falso<li>Todos os outros usuários receberam uma das políticas de CsTeamsMeetingPolicy com o AllowCloudRecording = verdadeiro <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>Onde as gravações das reuniões são armazenadas

As gravações de reunião são armazenadas no armazenamento na nuvem do Microsoft Stream. No momento, o recurso de gravação de reunião está desativado para clientes cujos os dados do Teams são armazenados no país se o Stream da Microsoft não estiver disponível na região de residência de dados no país onde os dados são armazenados. O recurso de gravação de reunião pode ser ativado para clientes cujos dados devem ser armazenados no país mesmo que o Microsoft Stream não esteja disponível na região de residência de dados do país. Isso pode ser feito permitindo que gravações sejam armazenadas na região geográfica mais próxima do Microsoft Stream. 

Se os seus dados do Teams estiverem armazenados no país e você preferir armazenar gravações de reunião no país, recomendamos que você desative o recurso e, em seguida, ative-o após a implantação do Microsoft Stream na região de residência de dados no país. Para desativar o recurso para todos os usuários em sua organização, desative a configuração **permitir gravação na nuvem** na política de reunião global do Teams, que está no centro de administração do Microsoft Teams. Se, no entanto, você ainda quiser habilitar as gravações para serem armazenadas na região geográfica mais próxima do Microsoft Stream, ative ambas as **permissões de gravação na nuvem** e permita o armazenamento de **gravação fora da região** antes que essa alteração ocorra.

Para habilitar gravações no-Region na política global, use o seguinte cmdlet:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $true -AllowRecordingStorageOutsideRegion $true

Here's a summary of what happens when you turn on meeting recording when this change takes effect:

|If you turn on meeting recordings...|Meeting recordings are stored... |
|---|---|
|Before Microsoft Stream is available in your in-country data residency region |In the nearest Microsoft Stream region|
|After Microsoft Stream is available in your in-country data residency region |In your in-country data residency region|

For new and existing tenants that haven't yet turned on meeting recording, new recordings are stored in-country after Microsoft Stream is available in the in-country data residency region. However, any tenant that enables meeting recording before Microsoft Stream is available in the in-country data residency region will continue to use the Microsoft Stream storage for existing and new recordings, even after Microsoft Stream is available in the in-country data residency region.

To find the region where your Microsoft Stream data is stored, in Microsoft Stream, click **?** in the upper-right corner, click **About Microsoft Stream**, and then click **Your data is stored in**.  To learn more about the regions where Microsoft Stream stores data, see [Microsoft Stream FAQ](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in).

To learn more about where data is stored across services in Microsoft 365 or Office 365, see [Where is your data located?](https://products.office.com/where-is-your-data-located?rtc=1)

### Turn on or turn off recording transcription

This setting controls whether captions and transcription features are available during playback of meeting recordings. If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording. The person who started the recording needs this setting turned on so that the recording also includes transcription.

> [!NOTE]
> That transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting. They are stored together with the meeting recordings in Microsoft Stream cloud storage.

You can use the Microsoft Teams admin center or PowerShell to set a Teams meeting policy to control whether the recording initiator gets a choice to transcribe the meeting recording.

In the Microsoft Teams admin center, turn on or turn off the **Allow transcription** setting in the meeting policy. To learn more, see [Manage meeting policies in Teams](meeting-policies-in-teams.md#allow-transcription).

Using PowerShell, you configure the AllowTranscription setting in TeamsMeetingPolicy. To learn more, see [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) and [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

Unless you have assigned a custom policy to the users, users get the Global policy, which has AllowTranscription disabled by default.

For a user to fall back to Global policy, use the following cmdlet to remove a specific policy assignment for a user:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Para alterar o valor de AllowCloudRecording na política global, use o seguinte cmdlet:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false
```
</br>
</br>

|Cenário|Etapas |
|---|---|
|Quero que todos os usuários da empresa possam transcrever ao iniciar a gravação de uma reunião |<ol><li>Confirme que CsTeamsMeetingPolicy global tem AllowTranscription = verdadeiro <li>Todos os usuários têm as CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com AllowCloudTranscription = verdadeiro. </ol>|
|Quero que a maioria dos meus usuários consiga transcrever as gravações da reunião, mas desabilite seletivamente usuários específicos que não têm permissão para transcrever |<ol><li>Confirme que CsTeamsMeetingPolicy global tem AllowTranscription = verdadeiro <li>A maioria dos usuários tem CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com o AllowTranscription = verdadeiro <li>Todos os outros usuários receberam uma das políticas de CsTeamsMeetingPolicy com o AllowTranscription = false </ol>|
|Quero que a transcrição da gravação seja 100% desabilitada |<ol><li>Confirme que o CsTeamsMeetingPolicy global tem AllowTranscription = false <li>Todos os usuários receberam CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com o AllowTranscription = falso </ol>|
|Quero que as transcrição seja desabilitada para a maioria dos usuários, mas permitida seletivamente para usuários específicos que tenham permissão para transcrever |<ol><li>Confirme que o CsTeamsMeetingPolicy global tem AllowCloudRecording = false <li>A maioria dos usuários receberam CsTeamsMeetingPolicy globais ou uma das políticas de CsTeamsMeetingPolicy com AllowCloudRecording = falso <li>Todos os outros usuários receberam uma das políticas de CsTeamsMeetingPolicy com o AllowCloudRecording = verdadeiro </ol>|
|||

### <a name="planning-for-storage"></a>Planejar o armazenamento

O tamanho de uma gravação de 1 hora é de 400 MB. Verifique se você entendeu a capacidade necessária para arquivos gravados e se tem armazenamento suficiente disponível no Microsoft Stream.  Leia a [visão geral de licenciamento do Microsoft Stream](https://docs.microsoft.com/stream/license-overview) para compreender o armazenamento base incluído na assinatura e como comprar armazenamento adicional.

## <a name="manage-meeting-recordings"></a>Gerenciar gravações de reunião

As gravações de reunião são consideradas conteúdo de propriedade do locatário. Se o proprietário da gravação sair da empresa, o administrador poderá abrir a URL do vídeo de gravação no Microsoft Stream no modo de administração. O administrador pode excluir a gravação, atualizar todos os metadados de gravação ou alterar as permissões do vídeo de gravação. Saiba mais sobre os [recursos de administração do Stream](https://docs.microsoft.com/stream/manage-content-permissions).

> [!NOTE]
> Confira [gerenciar dados do usuário no Microsoft Stream](https://docs.microsoft.com/stream/managing-user-data) e [permissões e privacidade no Microsoft Stream](https://docs.microsoft.com/stream/portal-permissions) para obter mais informações sobre como gerenciar gravações e acesso de usuários.

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Conformidade e descoberta eletrônica para gravações de reunião

As gravações de reunião são armazenadas no Microsoft Stream, que é o Microsoft 365 e o Office 365 de acordo com a camada-C. Para oferecer suporte a solicitações de Descoberta eletrônica para administradores de conformidade que estejam interessados em gravações de reuniões ou chamadas para o Microsoft Streams, a mensagem de gravação concluída estará disponível na funcionalidade de pesquisa de conteúdo de conformidade do Microsoft Teams. Os administradores de conformidade podem procurar a palavra-chave "gravação" na linha do assunto do item na visualização de pesquisa de conteúdo de conformidade e descobrir as gravações da reunião e de chamadas na organização. Um pré-requisito para exibir todas as gravações é que eles precisarão ser configurados no Microsoft Stream com acesso de administrador. Saiba mais sobre [atribuir permissões de administrador no Stream](https://docs.microsoft.com/stream/assign-administrator-user-role).

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
